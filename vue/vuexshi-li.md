# vuex实例


### vuex异步操作

> `index.js`

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

> `mutations.js`

```js
import {HEIGHT} from './mutation-types.js'

const mutatiosn = {
    [HEIGHT] (state, value) {
        state.height = value
    }
}

export default mutations
```

> `actions.js`

```js
import {HEIGHT} from './mutation-types.js'

const setHeight = ()=> {

}
```