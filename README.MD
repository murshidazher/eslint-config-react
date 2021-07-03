# [@murshidazher/eslint-config-react](https://github.com/murshidazher/eslint-config-react) [![npm](https://img.shields.io/npm/v/@murshidazher/eslint-config-react.svg?label=&color=0080FF)](https://github.com/murshidazher/eslint-config-react/releases/latest)

![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)

> An opinionated eslint configuration to make linting a 🌬️. **Accepting PRs**

- ESLint configuration for React Project.
- Easy to install and configure, ant it follows the best code standards from airbnb.
- Integrated with [@murshidazher/prettier-config](https://github.com/murshidazher/prettier-config) configuration for code formatting.

## Table of Contents

- [Table of Contents](#table-of-contents)
  - [Purpose](#purpose)
  - [Installation](#installation)
  - [How to use](#how-to-use)
  - [Contributing](#contributing)
  - [License](#license)

## Purpose

This configuration uses airbnb and Prettier configuration plus some extra rules that we find handy for *React* applications.

For more information you can check [eslint](https://eslint.org/) and [prettier](https://prettier.io/) documentations as well the [airbnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb) and [prettier configurations](https://github.com/prettier/eslint-config-prettier)  for more information.

This package integrates the Prettier rules with ESLint using our configuration. You can check it at [@murshidazher/prettier-configuration](https://github.com/murshidazher/prettier-config)

## Installation

You need ESLint and Prettier installed as development dependencies on your project. You can install them by using either **npm** or **yarn**.

### Option 1: NPM

If you use **npm** as the package manager,

```sh
npm install -D eslint prettier
```

Install all peer dependencies of our configuration, these can be listed by the command:

```sh
npm info "@murshidazher/eslint-config-react@latest" peerDependencies
```

If running *npm > v5* you install them by:

```sh
npx install-peerdeps --dev @murshidazher/eslint-config-react
```

If *npm < v5*, Linux/OSX users can run:

```sh
(
  export PKG=@murshidazher/eslint-config-react;
  npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
)
```

### Option 2: YARN

If you use **yarn** as the package manager,

```sh
yarn add eslint prettier -D
```

Install the peer dependencies tool, by running:

```sh
yarn global add install-peerdeps
```

and after that run the following command to install the project's config:

```sh
install-peerdeps @murshidazher/eslint-config-react
```

## How to use

To configure add the following to your `package.json` file,

```json

"eslintConfig": {
  "extends": "@murshidazher/react",
},
"prettier": "@murshidazher/prettier-config"
```

## Extending

This configuration is not intended to be changed, but if you have a setup where modification is required, it is possible. Prettier does not offer an "extends" mechanism as you might be familiar from tools such as ESLint.

To extend a configuration you will need to create a `.eslintrc.js` and `.prettierrc.js` or `prettier.config.js` files:

```js
//.eslintrc
{
  "root": true,
  "extends": "@murshidazher/react"
  // more configuration options goes here!
}

// .prettierrc.js
module.exports = {
    ...require('@murshidazher/prettier-config'),
    semi: false
    // more configuration options goes here!
};
```

Finally, you can add this scripts to your `package.json` file,

```json
"lint": "eslint ./ --ignore-path .gitignore",
"lint:fix": "npm run lint -- --fix",
"format": "prettier --write \"{,!(node_modules)/**/}*.js\""
```

## Commit Hook

If you need to add a pre-commit hook for linting,

```sh
npm install -D husky lint-staged
```

```json
// package.json
"lint-staged": {
  "*.{js,css,html}": [
    "yarn run lint:fix",
    "yarn run format",
    "git add"
  ]
},
```

## Contributing

How to [contribute](/CONTRIBUTING.MD) to this open source library

## License

Copyright © 2020-2021 [Murshid Azher](https://murshidazher.com). This library is licensed under the [MIT](./LICENCE).
