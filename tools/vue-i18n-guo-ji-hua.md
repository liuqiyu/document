# vue-i18n ，vue项目中如何实现国际化

### 前言

在布谷鸟的第二个月。

可能要做一个新项目，一个集合站，类似Mini版的京东。适配多国语言。恰巧在网上看到一篇博客说如何实现国际化，于是跟着写了一遍。

### 实现国际化

##### 安装

`npm install vue-i18n`

##### 使用

> `i18n.js` 与`main.js`同级

```js
import Vue from 'vue';
import VueI18n from 'vue-i18n';

Vue.use(VueI18n);

export default new VueI18n({
    locale: 'zh-CN',      // 默认语言
    //this.$i18n.locale， // 通过切换locale的值来实现语言切换
    messages: {
        'zh-CN': require('./common/lang/zh'),    // 中文语言包
        'ja-JP': require('./common/lang/ja'),    // 日文语言包
        'th-TH': require('./common/lang/thai'),  // 泰文语言包
        'en-US': require('./common/lang/en'),    // 英文语言包
    },
});
```


> `main.js`

```js
import i18n from 'i18n'  // 切记小写

new Vue({
  el: '#app',
  i18n,  ---->>>> 记得挂载
  router,
  store,
  render: h => h(App),
});
```

> `common -> lang -> all`

>> `zh.js`

```js
export const m = {
  title: '中文',
};
```

>> `en.js`

```js
export const m = {
  title: '英文',
};
```
...... 补充

###### html使用 -- 切换语言

```vue
{{$t('m.title')}}

// change

this.$i18n.locale = 'zh-CN';
this.$i18n.locale = 'ja-JP';
this.$i18n.locale = 'th-TH';
this.$i18n.locale = 'en-US';
```



