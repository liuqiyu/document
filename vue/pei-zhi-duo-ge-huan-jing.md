# vue-cli 配置多个环境

vue-cli默认只有两个环境，`development`和`production`。但是在实际开发中特别是大团队中，会要求有测试环境或者更多。要怎么办呢？

### 1、/build/test.js

复制build.js ==> test.js,代码如下：
```js
// 更改
const webpackConfig = require('./webpack.test.conf')
```

### 2、/build/webpack.test.conf.js

复制webpack.prod.conf.js ==> /webpack.test.conf.js,代码如下：
```js
// 更改
const env = require('../config/test.env')
```

### 3、/config/test.env.js

复制prod.env.js ==>test.env.js,代码如下：
```js
'use strict'
module.exports = {
  NODE_ENV: '"test"'
}
```

### 4、package.json

```js
"scripts": {
    "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
    "start": "npm run dev",
    "lint": "eslint --ext .js,.vue src",
    "build": "node build/build.js",
    "test": "node build/test.js",
    "preview": "node build/preview.js"
  },
```




