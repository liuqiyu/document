# module

```js
import Vue from 'vue';
import Vuex from 'vuex';
import vux from './vux';
import main from './main';
import products from './products';
import cart from './cart';

Vue.use(Vuex);

export default new Vuex.Store({
  modules: {
    vux,
    main,
    products,
    cart,
  },
});

```
