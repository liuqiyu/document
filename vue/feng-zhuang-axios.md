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

/*
* 增加拦截器
*/

// 添加请求拦截器
axios.interceptors.request.use(function (config) {
    // 在发送请求之前做些什么
    return config;
  }, function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  });

// 添加响应拦截器
axios.interceptors.response.use(function (response) {
  // 对响应数据做点什么
  return response;
}, function (error) {
  // 对响应错误做点什么
  return Promise.reject(error);
});


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

###  使用

> api.js

```js
import api from 'index'

const path = {
  // 流量分析
  traffic: '/analytics/traffic'
}

/**
 * 流量分析
 *
 * @param page
 * @param count
 * @param filterForm
 * @returns {AxiosPromise<any>}
 */
const getRraffic = (page, count, filterForm) => api.get(path.traffic, {
  params: {
    page: page,
    count: count,
    search_time: filterForm.search_time,
    url: filterForm.url,
    page_url: filterForm.page_url,
    targets: filterForm.targets.length > 0 ? JSON.stringify(filterForm.targets) : null,
    order: filterForm.order
  }
})


export default {
  getRraffic
}
```

