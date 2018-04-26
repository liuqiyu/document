# 理解Object.defineProperty的作用

#### 语法

`Object.defineProperty(obj, prop, descriptor)`.

> obj:<必须> 目标对象
> prop:<必须> 需要定义或者修改的属性名字
> descriptor:<必须> 目标属性所拥有的特性

```js
var obj = {
    name: 'lqy',
};

Object.defineProperty(obj,"age",{
    writable: true | false,  // 属性是否可以被重写，默认false
    enumerable: true | false,    // 属性是否可以被枚举，默认false
    value: 24,
    configurable: true | false       // 是否可以删除目标属性或是否可以再次修改属性的特性，默认false
});
```

#### writable

> 新属性：默认不能重写 `writable：false`
```js
Object.defineProperty(obj, 'age', {
  value: 24,
});

console.log(obj.age)   // 24

obj.age = 25;

console.log(obj.age)   // 24 不可被重写

// 将`writable`改为`true`，即可编辑.
// writable: true,
```

#### writable

> 原有属性：可以被重写
> 新属性：默认不能重写 `writable：false`
```js
Object.defineProperty(obj, 'age', {
  value: 24,
});

console.log(obj.age)   // 24

obj.age = 25;

console.log(obj.age)   // 24 不可被重写

// 将`writable`改为`true`，即可编辑.
// writable: true,
```

















