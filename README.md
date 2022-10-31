# @agilecontent/prettier-config

Base configuration for Prettier, used internally by @agilecontent

## How to use

Install the package as development dependency:

npm:

```
npm i -D @agilecontent/prettier-config
```

yarn:

```
yarn add -D @agilecontent/prettier-config
```

In your package.json, add the following:

```json
{
  "prettier": "@agilecontent/prettier-config"
}
```

We **do not recommend**, but if you need to change or add any other config to the prettier, you must
remove the prettier option on `package.json` and create a `.prettierrc.js` file with the following
content:

```js
const baseConfig = require('@agilecontent/prettier-config');

module.exports = {
  ...baseConfig,
  //Add your config here
};
```

## Config Reasoning

- `singleQuote: true`: Prettier defaults to the quotes with fewer escapes in a given string. This
  introduces inconsistency. This config normalizes to only single quotes
- `"trailingComma": "all"`: This puts a comma to the end of every entry of objects and parameters.
  This prevents merge conflicts when new entries are added.
- `"proseWrap": "always"`: Applies to Markdown only. This breaks lines on paragraphs.
- `"overrides[0].options.printWidth": 100`: Applies to Markdown only. Relaxes a bit the width of the
  lines, as plain text doesn't need to be so narrow.
