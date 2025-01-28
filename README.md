# eslint-config-rules-base

* Simple port from Airbnb's base eslint config rules from [here](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-rules-base)
* Upgraded to eslint v9 support, by [this PR](https://github.com/airbnb/javascript/pull/3061/files#diff-1a0e408629173016fd2c9cc2f0635c8d0e3f57d9cec29351ae1a646ec79a1379)
* Without react packages

## Usage

Only one configuration will be exported in this repo, and only flat configuration will be supported.

1. Install as dependancy

  ```sh
  npm info "eslint-config-rules-base@latest" peerDependencies
  ```

  If using **npm 5+**, use this shortcut

  ```sh
  npx install-peerdeps --dev eslint-config-rules-base
  ```

  If using **yarn**, you can also use the shortcut described above if you have npm 5+ installed on your machine, as the command will detect that you are using yarn and will act accordingly.
  Otherwise, run `npm info "eslint-config-rules-base@latest" peerDependencies` to list the peer dependencies and versions, then run `yarn add --dev <dependency>@<version>` for each listed peer dependency.

2. For flat usage with eslint v9

Import `"eslint-config-airbnb-base"` on your `eslint.config.mjs` file like this:

  ```javascript
  import airbnbBase from "eslint-config-airbnb-base";

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
