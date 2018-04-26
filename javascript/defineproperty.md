# 理解Object.defineProperty的作用

#### 语法

`Object.defineProperty(obj, prop, descriptor)`.

> obj:<必须> 目标对象
> prop:<必须> 需要定义或者修改的属性名字
> descriptor:<必须> 目标属性所拥有的特性

```js
//对象已有的属性添加特性描述
Object.defineProperty(obj,"age",{
    configurable:true | false,
    enumerable:true | false,
    value: 24,
    writable:true | false
});
```








