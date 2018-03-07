# base 基础正则语法

> `test()`: `patt.test(test)` -> 在字符串查找符合正则的内容。若找到，则返回true；若为找到，则返回false。

```js
## 用于验证表单是否为空

var patt = /\S/    // 匹配非空字符
var val = ''

patt.test(val)     // false
```