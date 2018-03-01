# 自定义组件

因为打算写一个自己的UI框架，所以在这里记录一下原理。

### 实例

> `button.vue` 目录： packages/button/src/button.vue

```vue
<template>
  <button
    class="ice-button"
    :class="['ice-button--' + type, 'ice-button--' + size, {
      'is-disabled': disabled
    }]"
    :disabled="disabled"
  >
    <span><slot></slot></span>
  </button>
</template>

<script>
export default {
  name: 'ice-button',
  props: {
    type: {
      default: 'default'
    },
    size: {
      default: 'large'
    },
    disabled: Boolean
  }
}
</script>
```

> `index.js` 目录：packages/button/index.js

```js
import ICEButton from './src/button'

export default ICEButton

```

> ui.js

```js
import Vue from 'vue'
import {
  ICEButton
} from './ui'

Vue.use(ICEButton)
```

### 全部加载

```js
// main.js

import ICEMANUI from './ui'
```













