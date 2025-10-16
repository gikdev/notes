# NestJS Cleanup Testing

- Removed tests folder

```sh
rm -rf test/
```

- Remove all testing scripts (`package.json`):

```json
{
  "scripts": {
    "test": "jest",
    "test:watch": "jest --watch",
    "test:cov": "jest --coverage",
    "test:debug": "node --inspect-brk -r tsconfig-paths/register -r ts-node/register node_modules/.bin/jest --runInBand",
    "test:e2e": "jest --config ./test/jest-e2e.json"
  }
}
```

- Remove these dependencies:

```sh
npm remove @nestjs/testing @types/jest @types/supertest jest supertest ts-jest typescript-eslint
```

- Also remove `package.json#jest`

```sh
{
  "jest": {...}
}
```

- Also set `nest-cli.json#generateOptions.spec` to `false`

```json
// ...
"generateOptions": {
  "spec": false
},
// ...
```
