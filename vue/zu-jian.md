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

> index.js 目录：packages/button/index.js

