# vuex

## 目录

1. [说明](#explain)
2. [安裝使用](#install)
2. [项目结构](#structure)
4. [核心概念](#core)
    * [State](#State)
    * [Getter](#Getter)
    * [Mutation](#Mutation)
    * [Action](#Action)


<a name="explain"></a>
## 说明

Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。Vuex 也集成到 Vue 的官方调试工具 devtools extension，提供了诸如零配置的 time-travel 调试、状态快照导入导出等高级调试功能。


<a name="install"></a>
## 安装使用

```
npm install vuex --save

// main.js

import Vue from 'vue'

import Vuex from 'Vuex'

Vue.use(Vuex)

使用

import store from './vuex/'

// store.js

export default new Vuex.Store({
    state,
    getters,
    mutations,
    actions
})
```


<a name="structure"></a>
## 项目结构

__store.js__

```
├── vuex
    ├──  index.js
    ├──  getters.js
    ├──  mutations.js
    ├──  mutation-types.js
    ├──  actions.js
```
#### 文件截图

<img src="https://github.com/liuqiyu/docs/blob/master/images/vuex/index.js.png" width="300"></img>
<img src="https://github.com/liuqiyu/docs/blob/master/images/vuex/mutations.js.png" width="300"></img>
<img src="https://github.com/liuqiyu/docs/blob/master/images/vuex/mutation-types.js.png" width="300"></img>
<img src="https://github.com/liuqiyu/docs/blob/master/images/vuex/actions.js.png" width="300"></img>

<a name="core"></a>
## 核心概念
深入理解所有的概念对于使用 Vuex 来说是必要的。

<a name="State"></a>
### State

> 单一状态树

```
this.$store.state.city

// mapState 辅助函数
import {mapState} from 'vuex'

computed : {
    ...mapState([
        'city',
    ])
}   // 或者
computed: mapState([
    'city'
])

```

<a name="Getter"></a>
### Getter

> 计算属性

```
this.$store.getters.getCity

// mapGetters 辅助函数
import {mapGetters} from 'vuex'

computed: {
    ...mapGetters:([
        'getCity'
    ])
}   // 或者
computed: mapGetters([
    'getCity'
])
```

<a name="Mutation"></a>
### Mutation

> 更改Vuex中state的状态唯一方法是提交Mutation。类似`事件`

* 简单用法
```
state: {
    count : 1
}

mutations: {
    increment (state, n) {
        state.count + n
    }
}
```

* 使用常量代替Mutation事件类型

```
// mutation-types.js
export const CITY_UPDATE = 'CITY_UPDATE'

// mutations.js
import {CITY_UPDATE} from './mutation-types.js'

const mutations = {
    [CITY_UPDATE] (state, val) {
        state.city = val
    }
}

// index.vue 使用
import { mapMutations } from 'vuex'

export default {
    methods: {
        ...mapMutations: ([
            'CITY_UPDATE'    // 相当于一个方法，介意使用 `this.CITY_UPDATE('深圳')` 调用
        ]) // 如下
        click () {
            this.CITY_UPDATE('深圳') // 或者不使用辅助函数
            this.$store.commit('CITY_UPDATE')
        }
    }
}
```

* mutation必须是同步

<a name="Action"></a>
### Action

> Action类似Mutation。 但是它提交的是Mutation,而不是直接改变状态。可以 `异步`

```
// actions.js
import {CITY_UPDATE} from './mutation-types'
import { getCity } from './../utils/getData'

const cityUpdate = ({commit}) => {
    let city = getCity()        // 异步获取当前城市
    commit(CITY_UPDATE, city)   // 提交Mutation事件
}

export default  {
    cityUpdate
}

// 使用 index.vue 
import { mapActions} from 'vuex'

export default {
    methods: {
        ...mapActions([
            'cityUpdate'
        ]),
        click () {
            this.cityUpdate()  // 使用action
        }
    }
}
```
