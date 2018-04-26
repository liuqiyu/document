# 理解Object.defineProperty的作用

#### 语法

`Object.defineProperty(obj, prop, descriptor)`.

> obj:<必须> 目标对象
> prop:<必须> 需要定义或者修改的属性名字
> descriptor:<必须> 目标属性所拥有的特性

```js
//对象已有的属性添加特性描述
Object.defineProperty(obj,"age",{
    writable: true | false,  // 属性是否可以被重写，默认false
    enumerable: true | false,    // 属性是否可以被枚举，默认false
    value: 24,
    configurable: true | false       // 是否可以删除目标属性或是否可以再次修改属性的特性，默认false
});
```

#### configurable








