# 自定义指令

除了核心内置指令(v-show)外，vue也允许注册自定义的指令。注意，在 Vue2.0 中，代码复用和抽象的主要形式是组件。

然而，有的情况下，你仍然需要对普通 DOM 元素进行底层操作，这时候就会用到自定义指令。


### 实例

> 进入页面时，Input默认获取焦点。

```html
<input v-focus></input> 
```

注册一个全局的自定义指令 `v-focus`
```javascript
Vue.directive('focus', {
  // 当被绑定的元素插入到 DOM 中时……
  inserted: function (el) {
    // 聚焦元素
    el.focus()
  }   
})
```
注册局部自定义指令,组件也接受一个directives参数

```javascript
directives: {
  focus: {
    // 指令的定义
    inserted: function (el) {
      el.focus()
    }
  }
}
```

### 钩子函数

> `bind`: 只能调用一次，初始化使用。

```javascript
// 初始化时往div添加元素
<div v-addHtml:foo.a.b="message"></div>

// el --> dom
// binding --> message 参数
Vue.directive('addHtml', {
  bind (el, binding, vnode) {
    el.innerHTML = '<span>binding。value</span>'
  }
})
```

