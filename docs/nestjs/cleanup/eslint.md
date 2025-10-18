---
sidebar_position: 2
---

# Remove ESLint

Get rid of ESLint...

```sh
rm eslint.config.*
```

- Remove the `lint` script

```json title="package.json"
{
  "scripts": {
    "lint": "...",
  }
}
```

- Remove it's deps

```sh
npm remove @eslint/eslintrc @eslint/js eslint eslint-config-prettier eslint-plugin-prettier typescript-eslint
```

