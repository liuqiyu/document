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
axios.post(`${config.host}/psuser/login`, this.form, {
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded',
        },
        transformRequest: [(data) => {
          // Do whatever you want to transform the data
          let ret = '';
          Object.keys(data).forEach((value) => {
            ret += `${encodeURIComponent(value)}=${encodeURIComponent(data[value])}&`;
          });
          const newRet = ret.slice(0, ret.length - 1);
          return newRet;
        }],
      })
        .then((res) => {
          if (res.data.info.status_code === 200) {
            const data = res.data.info.data;
            window.sessionStorage.setItem('userinfo', JSON.stringify(data));
            setTimeout(() => {
              this.$router.push({ path: '/search' });
            }, 100);
            this.$message({
              message: '登录成功',
              type: 'success',
            });
          } else {
            this.$message.error(res.data.info.message);
          }
        });
```