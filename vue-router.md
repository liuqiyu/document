# Vue-router
文档管理

## 目录

1. [安装使用](#install)
2. [基础](#basic)
    * [动态路由 - /user/:id](#dynamicRouter)
    * [路由访问](#visit)
    * [重定向和别名](#redirect)
2. [进阶](#advanced)
    * [导航守卫 -- 路由变化](#navigationGuard)
    * [路由元信息 -- meta](#meta)
    * [数据获取](#getData)
    * [路由懒加载](#lazyLoad)
    * [样式 - router-link](#style)



<a name="install"></a>
## 安装使用

```
npm install vue-router

import Vue from 'vue'

import VueRouter from 'vue-router'

Vue.use(VueRouter)

const routes = {}

const router = new VueRouter({
    routes
})

const app = new Vue({
    router
}) // 路由已经启动

```

<a name="basic"></a>
## 基础

<a name="dynamicRouter"></a>
### 动态路由

> 同一个组件不同的路由

> 例如：`/user/93` `/user/92` 都将映射到同一个路由。获取当前路由的参数使用`this.$route.params.id`

```
routes:[{
    path: "/user/:id",
    component: User
}]
```
> 相应参数变化

```
watch监听
    watch: {
        '$route' (to, from) {
            // to  将要跳往的路由
            // from  当前炉头
        }
    }

beforeRouteUpdate守卫
    beforeRouteUpdate (to, from, next) {
        // 监听路由变化
    }
```

<a name="visit"></a>
### 路由访问

    ```
    this.$router.push({path: '/user', params: { id: '123'}})
    等同于
    <router-link :to='{path: '/user', params: {id: '123'}}'></router-link>
    ```

<a name="redirect"></a>
### 重定向和别名

> 重定向
##### 访问 `/user` 但是url会被替换成`/info`，然后匹配路由为`/info`
```
routes: [{
    path: '/user',
    redirect: '/info',
    // redirect: { name : 'info'},  // name
    // redirect: to => {} // 方法
}]
```

> 别名    
##### 访问 `/user` 但是url会被替换成`/info`，然后匹配路由为`/user`
```
routes: [{
    path: '/user',
    alias: '/info'
}]
```

<a name="advanced"></a>
## 进阶

<a name="navigationGuard"></a>
### 导航守卫 -- 路由变化

#### 全局守卫

> `router.beforeEach((to, from, next) {})`    会受`next()`影响
 
#### 全局后置守卫

> `router.afterEach((to, from){})`  不会受`next()`影响

#### 路由独享的守卫

> beforeEnter: (to, from, next) => {}

```
const router = new VueRouter({
  routes: [
    {
      path: '/foo',
      component: Foo,
      beforeEnter: (to, from, next) => {
        // ...
      }
    }
  ]
})
```

#### 组件内的守卫

> `beforeRouteEnter`

> `beforeRouteUpdate`

> `beforeRouteLeave`

```
const Foo = {
  template: `...`,
  beforeRouteEnter (to, from, next) {
    // 在渲染该组件的对应路由被 confirm 前调用
    // 不！能！获取组件实例 `this`
    // 因为当守卫执行前，组件实例还没被创建
      next(vm => {
        // 通过 `vm` 访问组件实例   ！！！！！！！！！！
      })
  },
  beforeRouteUpdate (to, from, next) {
    // 在当前路由改变，但是该组件被复用时调用
    // 举例来说，对于一个带有动态参数的路径 /foo/:id，在 /foo/1 和 /foo/2 之间跳转的时候，
    // 由于会渲染同样的 Foo 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
    // 可以访问组件实例 `this`
  },
  beforeRouteLeave (to, from, next) {
    // 导航离开该组件的对应路由时调用
    // 可以访问组件实例 `this`
    next(false)  // 不离开当前路由 ！！！！！！！！！！
  }
}
```

> 完整的导航解析流程

* 导航被触发。
* 在失活的组件里调用离开守卫。
* 调用全局的 beforeEach 守卫。
* 在重用的组件里调用 beforeRouteUpdate 守卫 (2.2+)。
* 在路由配置里调用 beforeEnter。
* 解析异步路由组件。
* 在被激活的组件里调用 beforeRouteEnter。
* 调用全局的 beforeResolve 守卫 (2.5+)。
* 导航被确认。
* 调用全局的 afterEach 钩子。
* 触发 DOM 更新。
* 用创建好的实例调用 beforeRouteEnter 守卫中传给 next 的回调函数。


<a name="meta"></a>
### 路由元信息 - meta

> 路由配置meta字段.  `meta: { requiresAuth: true }`


<a name="getData"></a>
### 数据获取

* 导航完成之后获取
    > 可以有load加载提示
* 导航完成之前获取


<a name="lazyLoad"></a>
### 路由懒加载

> 当打包构建应用时，Javascript 包会变得非常大，影响页面加载。如果我们能把不同路由对应的组件分割成不同的代码块，然后当路由被访问的时候才加载对应组件，这样就更加高效了。

```
const Layout = r => require.ensure([], () => r(require('@/views/Basic/Layout')), 'init');

routes: [{
    path: '/',
    name: Layout,
    component: Layout
}]
```


<a name="style"></a>
### 样式 - router-link

> router-link

* active-class  链接激活使用的类名
    * default : "router-link-active"
    * 自定义 :  :active-link="avtive"
    
* 将激活 class 应用在外层元素
    ```
    <router-link tag="li" to="/foo">
      <a>/foo</a>
    </router-link>

    ```
    