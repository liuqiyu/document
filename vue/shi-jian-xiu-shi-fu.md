# 事件修饰符

* `.stop` 阻止冒泡，调用 `event.stopPropagation()`
* `.prevent` 阻止默认行为，调用 `event.preventDefault()`
* `.capture` 添加事件侦听器时使用事件捕获模式
* `.self` 只当事件在该元素本身（比如不是子元素）触发时，才会触发事件
* `.once` 事件只触发一次