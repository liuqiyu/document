# 如何实现双向绑定

面试官通常会问你一些Vue的实现原理。比如：如何实现双向绑定。可能大部分会说`v-model`。是的没错，但是然后呢？

> input 子组件

```vue
<template>
  <div>
    <input type="text" :value="value" @input="change">
  </div>
</template>

<script>
export default {
  props: ['value'],
  methods: {
    change(e) {
      this.$emit('input', e.target.value)
      console.log(e.target.value)
    }
  }
};
</script>

<style scoped>

</style>

```

> 父组件

```vue
    <Iinput :value="value" @input="value = arguments[0]"></Iinput>{{value}}
```