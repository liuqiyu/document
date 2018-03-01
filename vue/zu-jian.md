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

<style scoped>
  .ice-button {
    display: inline-block;
    line-height: 1;
    white-space: nowrap;
    cursor: pointer;
    background: #fff;
    border: 1px solid #dcdfe6;
    border-color: #dcdfe6;
    color: #606266;
    -webkit-appearance: none;
    text-align: center;
    box-sizing: border-box;
    outline: none;
    margin: 0;
    transition: .1s;
    font-weight: 500;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    padding: 0.12rem 0.2rem;
    font-size: 0.14rem;
    border-radius: 4px;
  }

  /** color **/
  .ice-button--default {
    background: #fff;
    border: 1px solid #dcdfe6;
    border-color: #dcdfe6;
  }

  .ice-button--primary {
    color: #fff;
    background-color: #26a2ff;
    border-color: #26a2ff;
  }

  .ice-button--primary:hover {
    background-color: #66b1ff;
    border-color: #66b1ff;
  }

  .ice-button.is-disabled {
    opacity: 0.6;
  }

  .ice-button--success {
    color: #fff;
    background-color: #67c23a;
    border-color: #67c23a;
  }

  .ice-button--warning {
    color: #fff;
    background-color: #e6a23c;
    border-color: #e6a23c;
  }

  .ice-button--danger {
    color: #fff;
    background-color: #f56c6c;
    border-color: #f56c6c;
  }

  .ice-button--info {
    color: #fff;
    background-color: #909399;
    border-color: #909399;
  }

  /** display**/
  .ice-button--block {
    display: block;
    width: 100%;
  }

  /** size **/
  .ice-button--large {
    padding: 0.12rem 0.2rem;
    font-size: 0.14rem;
  }

  .ice-button--small {
    padding: 0.1rem 0.15rem;
    font-size: 0.12rem;
  }

  .ice-button--mini {
    padding: 0.08rem 0.1rem;
    font-size: 0.12rem;
  }
</style>

```