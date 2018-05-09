# vue-lazyload 使用方法

[插件地址](https://github.com/hilongjw/vue-lazyload)

##### 安装

```
npm install vue-lazyload --save-dev
```

##### 使用

```js
import VueLazyLoad from 'vue-lazyload'
Vue.use(VueLazyLoad,{
    error:'./static/error.png',
    loading:'./static/loading.png'
})

<img class="item-pic" v-lazy="newItem.picUrl"/>
```