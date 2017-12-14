# Vue-router
文档管理


1. [安装使用](#install)
2. [学习笔记](#studyNote)
    * [动态路由 - /user/:id](#dynamicRouter)



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

<a name="studyNote"></a>
## 学习笔记

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