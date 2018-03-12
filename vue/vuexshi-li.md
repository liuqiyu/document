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

> `mutation-types.js`

```js
export const HEIGHT = 'HEIGHT'
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
import heights from './utils/heights'

const setHeight = async ({commit}, value) => {
    const height = await heights(val)             ===> 异步操作
    commit(HEIGHT, height)
}
```

> `heights.js`

```js
const heights = (dom) => {
    return new Promise((resolve) => {
        setTimeout(() => {
          let h = 0;
          dom.forEach((value) => {
            try{
              const $el = document.querySelector(value);
              if ($el !== null) {
                h += $el.offsetHeight;
                console.log($el.offsetHeight)
              }
            } catch(e) {
              h += 0;
            }
          });
          console.log(window.innerHeight)
          resolve(window.innerHeight - h - 20 - 10);
        })
    })
}
```