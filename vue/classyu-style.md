# Class 与 Style 绑定

### Class

##### 对象语法

```
<div v-bind:class="{ active: isActive }"></div>

data:{
    isActive: true
}
```

##### 数组语法

```
<div v-bind:class="[activeClass, errorClass]"></div>

data: {
  activeClass: 'active',
  errorClass: 'text-danger'
}
```


### style 

对象语法

```
<div v-bind:style="{ color: whatColor}"></div>

data:{
    whatColor: red
}

```

