# Prettier Setup

- Install dependencies

```sh
npm i -D prettier
# OR
bun i -d prettier
```

- Add the `format` script (`package.json`)

```json
{
  "scripts": {
    "format": "prettier --write ."
  }
}
```

- Create `.prettierrc`

```json
{
  "arrowParens": "avoid",
  "semi": false
}
```

- Create `.prettierignore`

```
node_modules/
dist/
generated/
bun.lock
```

- Now use it! 🥳

```sh
npm run format
# OR
bun format
```
