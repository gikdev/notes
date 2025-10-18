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

- Change client config if u need to

```prisma
generator client {
  provider = "prisma-client"
  output   = "../src/generated/prisma"
}
```

- Now u can generate client

```json title="package.json"
{
  "prisma:gen": "prisma generate"
}
```

```sh
npm run prisma:gen
```
