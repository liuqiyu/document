# keeep-alive 缓存问题

`<keep-alive>`是Vue的内置组件，能在组件切换过程中将状态保留在内存中，防止重复渲染DOM;

> 包裹动态组件时，时缓存它们，而不是销毁它们。和 <transition> 相似，<keep-alive> 是一个抽象组件：它自身不会渲染一个 DOM 元素，也不会出现在父组件链中。

* Props:
    * include - 字符串或正则表达式。只有匹配的组件会被缓存。
    * exclude - 字符串或正则表达式。任何匹配的组件都不会被缓存。

### 生命周期

* `activated` - keep-alive路由切换开始触发

* `deactivated` - keep-alive路由切换结束触发

### 实例

> 判断路由是否需要缓存

```js

// .vue
<keep-alive>
    <router-view v-if="$route.meta.keepAlive"></router-view>
</keep-alive>
<router-view v-if="!$route.meta.keepAlive"></router-view>

// route.js

meta: {
    keepAlive: false // 不需要被缓存
}

meta: {
    keepAlive: false // 不需要被缓存
}

```



