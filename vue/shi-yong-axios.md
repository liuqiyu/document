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