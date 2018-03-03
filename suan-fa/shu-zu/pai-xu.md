# 数组排序

### 数字排序

```js
  var arr = [1,4,1,2,6,12,9,8]
  
  console.log(arr.sort())
  
  function compare (val1, val2) {
    return val1 - val2      // 从小到大
    // return val2 - val1   // 从大到小

  }
  
  
  arr.sort(compare)   // [1, 1, 2, 4, 6, 8, 9, 12]
```