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

```