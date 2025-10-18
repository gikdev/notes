# Main.ts

```ts title="main.ts"
import { NestFactory } from "@nestjs/core"
import { AppModule } from "./app.module"
import { INestApplication, ValidationPipe } from "@nestjs/common"

class Main {
  private APP_PORT = 3000

  async bootstrap() {
    const app = await NestFactory.create(AppModule)

    // Do stuff...
    this.setupValidation(app)
    app.enableVersioning()
    this.enableCors(app)
    app.setGlobalPrefix("api")

    await app.listen(this.APP_PORT)

    this.showUrls()
  }

  private setupValidation(app: INestApplication) {
    app.useGlobalPipes(
      new ValidationPipe({
        whitelist: true,
        forbidNonWhitelisted: true,
        transform: true,
      })
    )
  }

  private enableCors(app: INestApplication) {
    app.enableCors({
      origin: "*",
      methods: "GET,HEAD,PUT,PATCH,POST,DELETE",
      credentials: true,
    })
  }

  private showUrls() {
    console.log("App running:")
    console.log(`  - Server:  http://localhost:${this.APP_PORT}/api`)
    // console.log(`  - Scalar:  http://localhost:${this.APP_PORT}/docs/scalar`)
  }
}

new Main().bootstrap()
```
