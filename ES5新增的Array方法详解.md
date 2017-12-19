# ES5新增的Array的方法详解

## 前言

ES5新增了很多新的方法，更加简便的解决了我们编码遇到的问题。由于ES5不兼容IE8及以下的浏览器，所以要求兼容请查看
[兼容地址](http://www.zhangxinxu.com/wordpress/2013/04/es5%E6%96%B0%E5%A2%9E%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95)

## 目录

1. [forEach](#forEach)
2. [map](#map)
3. [filter](#filter)
4. [some](#some)
5. [every](#every)
6. [indexOf](#indexOf)
7. [lastIndexOf](#lastIndexOf)
8. [reduce](#reduce)
9. [reduceRight](#reduceRight)
10. [兼容文件](#compatible)


## ONE BY ONE

<a name="forEach"></a>
### forEach 遍历

> 等同于传统的遍历，循环。`forEach(val, index, array){}` 。 `val` 表示循环的值， `index` 表示当前循环的位置， `array` 表示输出整个数组

> 用法: `array.forEach(callback,[ thisObject])
```
var arr = [1, 2, 3, 4, 5];

arr.forEach(function(value, index, array)){
    console.log(value, index, array);
    
    // 1 , 0, [1, 2, 3, 4]
    // 2 , 1, [1, 2, 3, 4]
    // 3 , 2, [1, 2, 3, 4]
    // 4 , 3, [1, 2, 3, 4]
}

// 使用ES6编写

arr.forEach((value, index, array) => {});
```
<a name="map"></a>
### map 映射

> 这里的`map`不是`地图`的意思，而是指`映射`。不难理解，映射就是讲原数组映射成新的数组。用法跟forEach类似。

> 用法： `array.map(callback,[ thisObject]);`

```
var arr = [1, 2, 3,]

var newArr = arr.map((value, index, array) => {
    return value + 1;
})

console.log(newArr)

// [2, 3, 4]
```

<a name="filter"></a>
### filter 过滤，筛选

> filter，`过滤`，`筛选`之意。数组filter后，返回一个新的数组。用法类型`map`。

> 用法： `array.filter(callback,[ thisObject]);`

> filter的callback函数需要返回布尔值`true`或者`false`。`true`则通过，`false`则不返回

```
var arr = [1, 2, 3, 4]

var newArr = arr.filter((value, index, array) => {
    return value > 2
})

console.log(newArr)
// [3,4]
```

<a name="some"></a>
### some 

> `某些`，指是否`某些项`符合条件。与`every`是好基友，`every`表示每一项都合乎条件。

> 用法: `array.some(callback,[ thisObject]);`
```
var arr = [1, 2, 3, 4];

var pp = arr.some((value) => {
    return value > 2
})

console.log(pp)
// true
```

<a name="every"></a>
### every

> 与`some`是好基友,需要每一项都符合条件

> 用法： `array.every(callback,[ thisObject]);`

```
var arr = [1, 2, 3, 4]

var pp = arr.every((value) => {
    return value > 0
})

// true; 每一项都大于0
```

<a name="indexOf"></a>
### indexOf

> `indexOf`在数组中的方法与在字符串的使用方法类似。返回整数的索引值，如果没有匹配，则返回`-1`。

> 用法：`array.indexOf(searchElement[, fromIndex])`

```
var arr = [1, 2, 3, 4]

console.log(arr.indexOf(1)) // 0
```

<a name="lastIndexOf"></a>
### lastIndexOf

> 如上

<a name="reduce"></a>
### reduce

> reduce是JavaScript 1.8中才引入的，中文意思为“减少”、“约简”。不过，从功能来看，我个人是无法与“减少”这种含义联系起来的，反而更接近于“迭代”、“递归(recursion)”，擦，因为单词这么接近，不会是ECMA-262 5th制定者笔误写错了吧~~

> 用法： `array.reduce(callback[, initialValue])`

> callback函数接受4个参数：之前值、当前值、索引值以及数组本身

```$xslt
var sum = [1, 2, 3, 4].reduce(function (previous, current, index, array) {
  return previous + current;
});

console.log(sum); // 10
```

<a name="reduceRight"></a>
### reduceRight

> 与上

<a name="compatible"></a>
### compatible
[兼容代码](http://www.zhangxinxu.com/wordpress/2013/04/es5%E6%96%B0%E5%A2%9E%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95)

