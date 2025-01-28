# eslint-config-rules-base

* Simple port from Airbnb's base eslint config rules from [here](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-rules-base)
* Upgraded to eslint v9 support, by [this PR](https://github.com/airbnb/javascript/pull/3061/files#diff-1a0e408629173016fd2c9cc2f0635c8d0e3f57d9cec29351ae1a646ec79a1379)
* Without react packages

## Usage

We export two ESLint configurations for your usage.

### eslint-config-rules-base

Our default export contains all of our ESLint rules, including ECMAScript 6+. It requires `eslint` and `eslint-plugin-import`.

1. Install the correct versions of each package, which are listed by the command:

  ```sh
  npm info "eslint-config-rules-base@latest" peerDependencies
  ```

  If using **npm 5+**, use this shortcut

  ```sh
  npx install-peerdeps --dev eslint-config-rules-base
  ```

  If using **yarn**, you can also use the shortcut described above if you have npm 5+ installed on your machine, as the command will detect that you are using yarn and will act accordingly.
  Otherwise, run `npm info "eslint-config-rules-base@latest" peerDependencies` to list the peer dependencies and versions, then run `yarn add --dev <dependency>@<version>` for each listed peer dependency.


  If using **npm < 5**, Linux/OSX users can run

  ```sh
  (
    export PKG=eslint-config-rules-base;
    npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
  )
  ```

  Which produces and runs a command like:

  ```sh
    npm install --save-dev eslint-config-rules-base eslint@^#.#.# eslint-plugin-import@^#.#.#
  ```

  If using **npm < 5**, Windows users can either install all the peer dependencies manually, or use the [install-peerdeps](https://github.com/nathanhleung/install-peerdeps) cli tool.

  ```sh
  npm install -g install-peerdeps
  install-peerdeps --dev eslint-config-rules-base
  ```

  The cli will produce and run a command like:

  ```sh
  npm install --save-dev eslint-config-rules-base eslint@^#.#.# eslint-plugin-import@^#.#.#
  ```

2. Add `"extends": "airbnb-base"` to your .eslintrc.

### eslint-config-rules-base/legacy

Lints ES5 and below. Requires `eslint` and `eslint-plugin-import`.

1. Install the correct versions of each package, which are listed by the command:

  ```sh
  npm info "eslint-config-rules-base@latest" peerDependencies
  ```

  Linux/OSX users can run
  ```sh
  (
    export PKG=eslint-config-rules-base;
    npm info "$PKG" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG"
  )
  ```

  Which produces and runs a command like:

  ```sh
  npm install --save-dev eslint-config-rules-base eslint@^#.#.# eslint-plugin-import@^#.#.#
  ```

2. Add `"extends": "airbnb-base/legacy"` to your .eslintrc

See [Airbnb's overarching ESLint config](https://npmjs.com/eslint-config-airbnb), [Airbnb's JavaScript styleguide](https://github.com/airbnb/javascript), and the [ESlint config docs](https://eslint.org/docs/user-guide/configuring#extending-configuration-files) for more information.

3. For flat usage with eslint v9

Import `"eslint-config-airbnb-base/flat"` on your `eslint.config.mjs` file like this:

  ```javascript
  import airbnbBase from "eslint-config-airbnb-base/flat";

  export default [
    ...airbnbBase,
    // Add your own configs
  ];
  ```

### eslint-config-rules-base/whitespace

This entry point only errors on whitespace rules and sets all other rules to warnings. View the list of whitespace rules [here](https://github.com/airbnb/javascript/blob/master/packages/eslint-config-rules-base/whitespace.js).

## Improving this config

Consider adding test cases if you're making complicated rules changes, like anything involving regexes. Perhaps in a distant future, we could use literate programming to structure our README as test cases for our .eslintrc?

You can run tests with `npm test`.

You can make sure this module lints with itself using `npm run lint`.
