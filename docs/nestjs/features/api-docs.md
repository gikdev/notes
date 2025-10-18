# API Docs

Add API docs!

- Install deps

```sh
npm i @nestjs/swagger @scalar/nestjs-api-reference
```

- Add:

```ts title="main.ts#Main"
private setupDocs(app: INestApplication) {
  const config = new DocumentBuilder()
    .setTitle("App API")
    .addServer(`http://localhost:${this.APP_PORT}/api`)
    .setVersion("1.0")
    // .addBearerAuth(
    //   {
    //     type: "http",
    //     scheme: "bearer",
    //     bearerFormat: "JWT",
    //     name: "JWT",
    //     description: "Enter JWT token",
    //     in: "header",
    //   },
    //   "bearer", // 🔑 This name matches @ApiBearerAuth() in controller
    // )
    .build()

  const doc = SwaggerModule.createDocument(app, config)

  SwaggerModule.setup("docs/swagger", app, doc, {
    jsonDocumentUrl: "docs/json",
    yamlDocumentUrl: "docs/yaml",
  })

  app.use(
    "/docs/scalar",
    apiReference({
      content: doc,
      // authentication: {
      //   preferredSecurityScheme: "bearer",
      // },
      theme: "deepSpace",
      layout: "modern",
      defaultHttpClient: {
        targetKey: "js",
        clientKey: "fetch",
      },
    }),
  )
}
```

then call it in `main.ts#Main.bootstrap()`

```ts title="main.ts#Main.bootstrap()"
this.enableCors(app)
// here 👇🏻
this.setupDocs(app) // like this
// ⚠️ be careful about the order!
this.setupGlobalPrefix(app)
```

- Enable auto documentation

```json title="nest-cli.json"
// ...
"compilerOptions": {
  "plugins": ["@nestjs/swagger"],
  // Add 👆🏻
  // ... 
}
```