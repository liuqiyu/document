# 生命周期

```
var vm = new Vue({
  el: '#app',
  data: {
    message: 'Vue的生命周期'
  },
  beforeCreate: function() {
    console.group('------beforeCreate创建前状态------');
    console.log("%c%s", "color:red" , "el     : " + this.$el); //undefined
    console.log("%c%s", "color:red","data   : " + this.$data); //undefined 
    console.log("%c%s", "color:red","message: " + this.message)  //undefined 
  },
  created: function() {
    console.group('------created创建完毕状态------');
    console.log("%c%s", "color:red","el     : " + this.$el); //undefined
    console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化 
    console.log("%c%s", "color:red","message: " + this.message); //已被初始化
  },
  beforeMount: function() {
    console.group('------beforeMount挂载前状态------');
    console.log("%c%s", "color:red","el     : " + (this.$el)); //已被初始化
    console.log(this.$el);
    console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化  
    console.log("%c%s", "color:red","message: " + this.message); //已被初始化  
  },
  mounted: function() {
    console.group('------mounted 挂载结束状态------');
    console.log("%c%s", "color:red","el     : " + this.$el); //已被初始化
    console.log(this.$el);    
    console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化
    console.log("%c%s", "color:red","message: " + this.message); //已被初始化 
  },
  beforeUpdate: function () {
    console.group('beforeUpdate 更新前状态===============》');
    console.log("%c%s", "color:red","el     : " + this.$el);
    console.log(this.$el);   
    console.log("%c%s", "color:red","data   : " + this.$data); 
    console.log("%c%s", "color:red","message: " + this.message); 
  },
  updated: function () {
    console.group('updated 更新完成状态===============》');
    console.log("%c%s", "color:red","el     : " + this.$el);
    console.log(this.$el); 
    console.log("%c%s", "color:red","data   : " + this.$data); 
    console.log("%c%s", "color:red","message: " + this.message); 
  },
  beforeDestroy: function () {
    console.group('beforeDestroy 销毁前状态===============》');
    console.log("%c%s", "color:red","el     : " + this.$el);
    console.log(this.$el);    
    console.log("%c%s", "color:red","data   : " + this.$data); 
    console.log("%c%s", "color:red","message: " + this.message); 
  },
  destroyed: function () {
    console.group('destroyed 销毁完成状态===============》');
    console.log("%c%s", "color:red","el     : " + this.$el);
    console.log(this.$el);  
    console.log("%c%s", "color:red","data   : " + this.$data); 
    console.log("%c%s", "color:red","message: " + this.message)
  }
})
```

最开始的时候，我们会创建一个`instace`（实例），在`new Vue（）`的对象过程中。首先会执行`init`初始化。我们会调用`beforeCreate`。在`beforeCreate`时，`$el`选项和`$data`属性都是没有的`undefined`。所以这时前往不要去修改`$data`属性。然后injections（注射）和reactivity（反应性）的时候，他会调用`created`。`created`完成后，他会判断实例是否含有`el`选项。如果没有的话，他会去调用`vm.$mounte(el)`这个方法[参照脚手架]。然后执行下一步，如果有，则直接执行下一步。紧接着会判断是否有`template`选项。如果有的话，他会把他变异成一个`render function`。使用`render`函数的结果和我们之前使用`template`解析出来的结果是一样的。`render`函数是发生在`beforeMount`和`mounted`之间的，这也从侧面说明了，在`beforeMount`的时候，`$el`还只是我们在`HTML`里面写的节点，然后到`mounted`的时候，它就把渲染出来的内容挂载到了DOM节点上。这中间的过程其实是执行了`render function`的内容。

在使用`.vue`文件开发的过程中，我们会写`template`模板。在结果`vue-loader`处理之后，就变成了`render function`,最终放到了`vue-loader`解析的文件里面。这样做有什么好处呢？原因是由于在解析template变成render function的过程，是一个非常耗时的过程，vue-loader帮我们处理了这些内容之后，当我们在页面上执行vue代码的时候，效率会变得更高。

`beforeMount`实在有了`render function`后才会去执行。然后再去调用`mounted`这个`hook`钩子,当`mounted`挂载玩，这个`instance`算是走完了流程。

后续的钩子函数执行的过程都是需要外部的触发才会执行。比如说有数据的变化，会调用`beforeUpdate`，然后经过`Virtual DOM`，最后`updated`更新完毕。当组件被销毁的时候，它会调用`beforeDestory`，以及`destoryed`。

[文章地址]（https://juejin.im/post/5ad10800f265da23826e681e）