# @agilecontent/prettier-config

Base configuration for Prettier, used internally by @agilecontent

## How to use

In your package.json, add the following:

```json5
{
  devDependencies: {
    "@agilecontent/prettier-config": "github:agilecontent/prettier-config",
    //...other dependencies
  },
  prettier: "@agilecontent/prettier-config",
}
```

We **do not recommend**, but if you need to change or add any other config to the prettier, you must create a `.prettierrc.js` file with the following content:

```js
const baseConfig = require("@agilecontent/prettier-config");

module.exports = {
  ...baseConfig,
  //Add your override here
};
```
