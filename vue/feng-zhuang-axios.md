# 封装axios

### 安装

`npm install axios`

### 代码

> 封装axios： index.js

```js
import axios from 'axios'
import config from './../config'

const instance = axios.create({
    baseUrl: config.apiHost,
})
```