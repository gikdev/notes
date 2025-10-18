---
sidebar_position: 3
---

# Testing

Get rid of testing...

- Removed tests folder

```sh
rm -rf test/
```

- Remove all testing scripts:

```json title="package.json"
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

```json title="package.json"
{
  "jest": {...}
}
```

- Also disable Nest's CLI's spec file generation:

```json title="nest-cli.json"
// ...
"generateOptions": {
  "spec": false
},
// ...
```
