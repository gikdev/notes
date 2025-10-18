# Prisma ORM

- Install

```sh
npm i -D prisma
```

- Add script:

```json title="package.json"
{
  "prisma": "prisma"
}
```

- Then run to initialize the project

```sh
npm run prisma init
```

- Change client config if you need to

```prisma
generator client {
  provider = "prisma-client-js"
  output   = "../generated/prisma"
}
```

- Now u can generate client

```json title="package.json"
{
  "prisma:gen": "prisma generate",
}
```

```sh
npm run prisma:gen
```

- Model your data (in `schema.prisma`)

- Add some more scripts

```json title="package.json"
{
  "db:gen": "prisma generate",
  "db:studio": "prisma studio",
  "db:seed": "prisma db seed",
  "db:pull": "prisma db pull",
  "migrate:dev": "prisma migrate dev",
  "migrate:reset": "prisma migrate reset",
  "migrate:status": "prisma migrate status",
  "migrate:deploy": "prisma migrate deploy",
}
```

- Config the `DB_URL`

```env title=".env"
DB_URL=
# or
DATABASE_URL=
```

- Do DEV mode migration

```sh
npm run migrate:dev
```

- Make the Prisma module:

```sh
nest g mo prisma
nest g s prisma
```

- Make the `PrismaModule` global (with `@Global()`)

- Make the `PrismaService`

```ts title="src/prisma/prisma.service.ts"
import { Injectable, OnModuleDestroy, OnModuleInit } from "@nestjs/common"
import { PrismaClient } from "generated/prisma"

@Injectable()
export class PrismaService
  extends PrismaClient
  implements OnModuleInit, OnModuleDestroy
{
  async onModuleInit() {
    await this.$connect()
  }

  async onModuleDestroy() {
    await this.$disconnect()
  }
}
```
