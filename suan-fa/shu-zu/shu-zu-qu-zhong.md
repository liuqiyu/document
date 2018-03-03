# 数组去重

> 方法1
判断是否包含在数组中

```js
function unique(arr) {
  var newArr = []

  for (var i = 0; i < arr.length; i ++) {
    if (newArr.indexOf(arr[i]) < 0) {
      newArr.push(arr[i])
    }
  }
  return newArr
}

var arr = [1, 2, 3, 4, 4, 5, 6, 7]

unique(arr)  // [1,2,3,4,5,6,7]
```

> 方法二