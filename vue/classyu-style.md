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

##### 对象语法

```
<div v-bind:style="color: whatColor"></div>

<div v-bind:style="{color: whatColor, background: whatBg}"></div>

data:{
    whatColor: 'red,
    whatBg: 'green'
}
```


##### 数组语法

```
<div v-bind:style="[baseStyles, overridingStyles]"></div>

data: {
  baseStyles: {
    'color': 'red'
  },
  overridingStyles: 'text-danger'
}

```

