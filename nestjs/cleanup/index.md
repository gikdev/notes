# NestJS Cleanup

- Remove unused files

```sh
rm README.md
```

- Also remove eslint

```sh
rm eslint.config.*
```

```json
// Remove:
{
  "scripts": {
    "lint": "...",
  }
}
```

```sh
npm remove @eslint/eslintrc @eslint/js eslint eslint-config-prettier eslint-plugin-prettier typescript-eslint
```

- [CLEANUP TESTING](./testing.md) (optional)

- Don't forget to [config prettier](../../prettier/setup.md) too! 

- Fix `package.json#scripts`

```json
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
cd src;
rm app.con*;
rm app.ser*;
```

- Simplify `src/app.module.ts`

```ts
import { Module } from "@nestjs/common"

@Module({})
export class AppModule {}
```
