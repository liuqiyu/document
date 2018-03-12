# vuex实例


### vuex异步操作

```js
import Vue from 'vue'
import Vuex from 'vuex'
import mutations from 'mutations'
import actions from 'actions'

Vuex.use(vue)

const state = {
    height: 0,
}

export default new Vuex.store({
    state,
    mutations,
    actions
})
```