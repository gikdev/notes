# NestJS Features: API Docs

- Install deps

```sh
npm i @nestjs/swagger @scalar/nestjs-api-reference
```

- Add this to `main.ts#Main`

```ts
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

```ts
this.enableCors(app)
this.setupDocs(app) // like this
this.setupGlobalPrefix(app)
```

- Enable auto documentation (`nest-cli.json`)

```json
// ...
"compilerOptions": {
  "plugins": ["@nestjs/swagger"],
  // Add 👆🏻
  // ... 
}
```