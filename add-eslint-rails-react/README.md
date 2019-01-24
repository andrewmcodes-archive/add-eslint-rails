# README

```
➜ rails new add-eslint-rails --webpack=react
➜ yarn add -D eslint eslint-config-airbnb@latest eslint-plugin-import@2.14.0 eslint-plugin-jsx-a11y@6.1.1 eslint-plugin-react@7.11.0

➜ yarn eslint --init
yarn run v1.12.3
$ /path/add-eslint-rails/add-eslint-rails-react/node_modules/.bin/eslint --in
it
? How would you like to configure ESLint? Use a popular style guide
? Which style guide do you want to follow? Airbnb (https://github.com/airbnb/javascript)
? Do you use React? Yes
? What format do you want your config file to be in? JavaScript
Checking peerDependencies of eslint-config-airbnb@latest
The config that you've selected requires the following dependencies:

eslint-config-airbnb@latest eslint@^4.19.1 || ^5.3.0 eslint-plugin-import@^2.14.0 eslint-plugin-jsx-a11y@^6.
1.1 eslint-plugin-react@^7.11.0
? Would you like to install them now with npm? No
Successfully created .eslintrc.js file in /path/add-eslint-rails/add-eslint-rails-react
✨  Done in 11.96s.
```

Add the following to package.json under `"name": "add-eslint-rails-react",`

```
  "scripts": {
    "lint": "yarn run eslint --ext .js --ext .jsx app/javascript"
  }
```

To lint your app, run `yarn lint`. On a greenfield app, generated according to these instructions, your output will be:

```
➜ yarn lint
yarn run v1.12.3
$ yarn run eslint --ext .js --ext .jsx app/javascript
warning From Yarn 1.0 onwards, scripts don't require "--" for options to be forwarded. In a future version,
any explicit "--" will be forwarded as-is to the scripts.
$ /path/add-eslint-rails/add-eslint-rails-react/node_modules/.bin/eslint --ex
t .js --ext .jsx app/javascript

/path/add-eslint-rails/add-eslint-rails-react/app/javascript/packs/applicatio
n.js
  10:42  error  Missing semicolon  semi

/path/add-eslint-rails/add-eslint-rails-react/app/javascript/packs/hello_reac
t.jsx
  1:1   error  Line 1 exceeds the maximum line length of 100  max-len
   2:1   error  Line 2 exceeds the maximum line length of 100  max-len
   5:26  error  Missing semicolon                              semi
   6:33  error  Missing semicolon                              semi
   7:35  error  Missing semicolon                              semi
  10:8   error  `Hello ` must be placed on a new line          react/jsx-one-expression-per-line
  10:14  error  `{props.name}` must be placed on a new line    react/jsx-one-expression-per-line
  10:15  error  Must use destructuring props assignment        react/destructuring-assignment
  10:26  error  `!` must be placed on a new line               react/jsx-one-expression-per-line
  11:2   error  Missing semicolon                              semi
  14:16  error  Missing trailing comma                         comma-dangle
  15:2   error  Missing semicolon                              semi
  18:25  error  Missing trailing comma                         comma-dangle
  19:2   error  Missing semicolon                              semi
  21:1   error  'document' is not defined                      no-undef
  24:5   error  'document' is not defined                      no-undef
  24:31  error  'document' is not defined                      no-undef
  25:4   error  Missing semicolon                              semi
  26:3   error  Missing semicolon                              semi

✖ 20 problems (20 errors, 0 warnings)
  14 errors and 0 warnings potentially fixable with the `--fix` option.

error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.

```
