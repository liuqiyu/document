# ES5新增的Array的方法详解

## 前言

ES5新增了很多新的方法，更加简便的解决了我们编码遇到的问题。

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


## one by one

<a name="forEach"></a>
### forEach

> 等同于传统的遍历，循环。`forEach(val, index, array){}` 。 `val` 表示循环的值， `index` 表示当前循环的位置， `array` 表示输出整个数组
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
### map

<a name="filter"></a>
### filter

<a name="some"></a>
### some

<a name="every"></a>
### every

<a name="indexOf"></a>
### indexOf

<a name="lastIndexOf"></a>
### lastIndexOf

<a name="reduce"></a>
### reduce

<a name="reduceRight"></a>
### reduceRight