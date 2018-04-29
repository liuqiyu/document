# 深拷贝

在面试过程中，时常会被问如何实现深克隆\深拷贝。也许你可以回答一些实现的方法，但是深追时，便原形毕露。


首先，`Javascript`基本类型了解一下。

> Javascript基本数据类型：Undefined,Null,Boolean,Number,String

> Javascript复杂数据类型：Object


### 1、浅克隆

浅克隆之所以被称为浅克隆，是因为对象只会被克隆最外面的一层。更深层的东西，则依旧指向通过引用指向同一堆块内存。

`Object.assign()`

### 2、深克隆

`const newObj = JSON.parse(JSON.stringify(oldObj));`



















```js
JSON.parse(JSON.stringify(a))
```

