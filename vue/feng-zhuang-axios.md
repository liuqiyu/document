# 封装axios

### 安装

`npm install axios`

### 代码

> 封装axios： index.js

```js
import axios from 'axios'
import config from './../config'  // 用于大型多人项目区分不同环境

const instance = axios.create({
    baseUrl: config.apiHost,
})
```

> config.js:可用于大型项目

```js

let apiHopst = `${location.protocol}//${location.host}/api/`

if (process.env.NODE_ENV === 'development') {
  console.log('开发')
} else {
  console.log('生产')
  apiHopst = `${location.protocol}//${location.host}`
  console.log(apiHopst)
}

export default {
  apiHopst
}
```

> config/index.js 配置文件

```js
module.exports = {
  dev: {
     proxyTable: {
      '/api': {
        target: 'http://bi.stosz.com/',
        changeOrigin: true,   // 是否跨域
        pathRewrite: {
          '^/api': '/'
        }
      },
    },
  }
}
```