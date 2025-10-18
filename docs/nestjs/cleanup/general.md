---
sidebar_position: 1
---

# General

- Get rid of some general stuff...

- Remove unused files

```sh
rm README.md
```

- Don't forget to [config prettier](../../prettier/setup) too! 

- Fix `package.json#scripts`

```json title="package.json"
// from
"build": "nest build",
"format": "prettier --write \"src/**/*.ts\" \"test/**/*.ts\"",
"start": "nest start",
"start:dev": "nest start --watch",
"start:debug": "nest start --debug --watch",
"start:prod": "node dist/main"

// to
"dev": "nest start --watch",
"format": "prettier --write .",
"debug": "nest start --debug --watch",
"build": "nest build",
"start": "nest start",
```

- Unused `src/` files

```sh
cd src && rm app.con* && rm app.ser*
```

- Simplify:

```ts title="src/app.module.ts"
import { Module } from "@nestjs/common"

@Module({})
export class AppModule {}
```
