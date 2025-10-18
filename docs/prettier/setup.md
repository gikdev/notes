# Prettier Setup

Set Prettier up simply!

```sh
npm i -D prettier
```

```json title="package.json"
{
  "scripts": {
    "format": "prettier --write ."
  }
}
```

```json title=".prettierrc"
{
  "arrowParens": "avoid",
  "semi": false
}
```

```text title=".prettierignore"
node_modules/
dist/
generated/
bun.lock
```

- Now use it! 🥳

```sh
npm run format
```
