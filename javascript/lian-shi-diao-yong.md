# 链式调用

第一次听见`链式调用`这个专业名词的时候，一脸懵逼。

什么是`链式调用`呢！相信大部分人都用过`jQuery`吧。

`$('div').html('123').show()`

简单的一行`jQuery`便是`链式调用`。但这又是如何实现的呢？

```
var Obj = {
    a: 1,
    func: function(){
        this.a += 1;
        return this
    }
}
Obj.func().func();
```