# 如何实现双向绑定

面试官通常会问你一些Vue的实现原理。比如：如何实现双向绑定。可能大部分会说`v-model`。是的没错，这只是语法糖，但是然后呢？其实原理很简单：

### Object.defineProperty数据劫持


### 类似react实现

> input 子组件

> 小知识： input事件当输入框改变会处罚change方法。
 
```
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
    }
  }
};
</script>

```

> 父组件

```
    <Iinput :value="value" @input="value = arguments[0]"></Iinput>{{value}}
```