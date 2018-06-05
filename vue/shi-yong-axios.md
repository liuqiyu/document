# 使用axios

### 封装方法

```js
const instance = axios.create({
  baseURL: config.apiHopst,
  params: {
    session_id: userinfo ? userinfo.session_id : null,
  },
});

export default instance;
```