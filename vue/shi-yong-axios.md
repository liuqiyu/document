# 使用axios

### 封装方法

```js
import axios from 'axios';
import config from './../config';

const userinfo = JSON.parse(window.sessionStorage.getItem('userinfo'));
const instance = axios.create({
  baseURL: config.apiHopst,
  params: {
    session_id: userinfo ? userinfo.session_id : null,
  },
});

export default instance;
```

### POST表单

```js
const addParame = form => api.post(path.addParame, form, {
  headers: {
    'Content-Type': 'application/x-www-form-urlencoded',
  },
  transformRequest: [(data) => {
  // Do whatever you want to transform the data
    let ret = '';
    const keys = Object.keys(data);
    keys.forEach((key) => {
      ret += `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}&`;
    });
    const newRet = ret.slice(0, ret.length - 1);
    return newRet;
  }],
});
```

### GET方法

```js
const getPpoolInfos = (page, count, formValue) => api.get(path.ppoolInfos, {
  params: {
    page,
    count,
    score_type: formValue.score_type,
    sort_type: formValue.sort_type,
    category_id: formValue.category_id,
    website_id: formValue.website_id,
  },
});
```