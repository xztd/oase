# xztd/oase Setup 

## installation of root packages

### installing lerna and yarn once globally
```shell script
npm i -g yarn lerna@next
```

### installing misc dev packages
```shell script
yarn add -D core-js cross-env husky nodemon rimraf
```

### installing commitlint packages
```shell script
yarn add -D @commitlint/{config-conventional,config-lerna-scopes,cli} standard-version
```

#### setup husky for integration of lint-staged and commitlint

create [config/commitlint.config.js](../config/commitlint.config.js) file.
adding husky for running commitlint and eslint as pre-commit and commit-msg to [package.json](../package.json)

The commitlint config is extended to support some special requirements to the project.
```json
{
  "lint-staged": {
    "packages/**/*.{js,ts,tsx}": [
      "lint:staged"
    ]
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged",
      "commit-msg": "commitlint --config ./config/commitlint.config.js --env HUSKY_GIT_PARAMS"
    }
  }
}
```

### installing Typescript packages
```shell script
yarn add -D  typescript tslib @types/node
```

#### setup typescript config
* create [config/tsconfig.base.json](../config/tsconfig.base.json) file.
* create [config/tsconfig.eslint.json](../config/tsconfig.eslint.json) file.
* create [tsconfig.json](../tsconfig.json) file.

in [tsconfig.json](../tsconfig.json) and [config/tsconfig.eslint.json](../config/tsconfig.eslint.json) add the following

`tsconfig.json`
```json
{
  "extends": "./config/tsconfig.base.json"
}
```
`config/tsconfig.eslint.json`
```json
{
  "extends": "./tsconfig.base.json"
}
```
### installing babel packages
```shell script
yarn add -D @babel/{cli,core,preset-env,preset-react,plugin-transform-react-jsx} babel-plugin-styled-components
```
#### setup babel config

* create [config/babel.config.js](../config/babel.config.js) file.
* create [babel.config.js](../babel.config.js) file.

in [babel.config.js](../babel.config.js) add the following
```javascript
module.exports = { ...require("./config/babel.config") };
```

### installing rollup packages
```shell script
yarn add -D rollup @rollup/{plugin-alias,plugin-commonjs,plugin-replace} rollup-plugin-analyzer rollup-plugin-terser rollup-plugin-visualizer @wessberg/rollup-plugin-ts
```

#### setup rollup config

* create [./config/rollup.base.js](./config/rollup.base.js) file.

### installing eslint packages
```shell script
yarn add -D lint-staged eslint eslint-config-airbnb-typescript eslint-plugin-import eslint-plugin-jest eslint-plugin-react eslint-plugin-react-hooks @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-jsx-a11y
```

#### setup eslint configs

adding lint-staged config to  [package.json](./package.json)

```json
{
  "scripts": {
    "lint:staged": "lerna run linting"
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "**/*.{js,ts,tsx}": [
      "lint:staged"
    ]
  }
}
```
### installing jest packages
```shell script
yarn add -D jest jest-styled-components babel-jest
```
