# Better Commit

Cross env commit conventions flow

## Dependencies:

Global dependency: [commitlint](https://commitlint.js.org/#/)
Project dependency: [husky](https://typicode.github.io/husky/#/), [commitizen](https://commitizen.github.io/cz-cli/)

## Project setup

### Start git

```
git init
```

### Install commitlint globaly

```
npm install -g @commitlint/cli @commitlint/config-conventional
```

### Install husky and commitizen on your project as a dev dependencies

```
npm install -D husky commitizen
```

### Start husky

```
npx husky install
```

### Setting husky to use linter

```
npx husky add .husky/commit-msg \"npx --no -- commitlint --edit '$1'\"
```

### Start commitizen

```
npx commitizen init cz-conventional-changelog --yarn --dev --exact
```

### Setting husky to use commitizen

```
npx husky add .husky/prepare-commit-msg "exec < /dev/tty && node_modules/.bin/cz --hook || true"
```

## Running commit flow

```
git commit
```
