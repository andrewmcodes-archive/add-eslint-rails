# README

```
➜ rails new add-eslint-rails --webpack
yarn rn add -D eslint eslint-config-airbnb eslint-loader eslint-plugin-import

➜ yarn add -D eslint@latest eslint-config-airbnb@latest eslint-plugin-import@2.14.0

➜ yarn eslint --init
yarn run v1.12.3
$ /my_path/add-eslint-rails/add-eslint-rails/node_modules/.bin/eslint --init
? How would you like to configure ESLint? Use a popular style guide
? Which style guide do you want to follow? Airbnb (https://github.com/airbnb/javascript)
? Do you use React? No
? What format do you want your config file to be in? JavaScript
Checking peerDependencies of eslint-config-airbnb-base@latest
The config that you've selected requires the following dependencies:
eslint-config-airbnb-base@latest eslint@^4.19.1 || ^5.3.0 eslint-plugin-import@^2.14.0
? Would you like to install them now with npm? No
Successfully created .eslintrc.js file in /my_path/add-eslint-rails/add-eslint-rails
✨  Done in 10.21s.
```

Add the following to package.json under `"name": "add-eslint-rails",`

```
  "scripts": {
    "lint": "yarn run eslint --ext .js app/javascript"
  }
```

To lint your app, run `yarn lint`. On a greenfield app, generated according to these instructions, your output will be:

```
➜ yarn lint
yarn run v1.12.3
$ yarn run eslint --ext .js app/javascript
$ /path/add-eslint-rails/add-eslint-rails/node_modules/.bin/eslint --ext .js app/javascript

/path/add-eslint-rails/app/javascript/packs/application.js
  10:42  error  Missing semicolon  semi

✖ 1 problem (1 error, 0 warnings)
  1 error and 0 warnings potentially fixable with the `--fix` option.

error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```
