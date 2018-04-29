# 深拷贝

在面试过程中，时常会被问如何实现深克隆\深拷贝。也许你可以回答一些实现的方法，但是深追时，便原形毕露。


首先，`Javascript`基本类型了解一下。

> Javascript原始类型：Undefined,Null,Boolean,Number,String,Symbol

> Javascript引用类型：Object

```js
JSON.parse(JSON.stringify(a))
```

