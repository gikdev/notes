# NestJS Prisma ORM

- Install

```sh
npm i -D prisma
```

- Add script:

```json
{
  "prisma": "prisma"
}
```

- Then

```sh
npm run prisma init
```

- Change client config if u need to

```prisma
generator client {
  provider = "prisma-client"
  output   = "../src/generated/prisma"
}
```

- Now u can generate client

```json
{
  "prisma:gen": "prisma generate"
}
```
```sh
npm run prisma:gen
```