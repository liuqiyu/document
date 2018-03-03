# 数组排序

### 数字排序

```js
var arr = [1,4,1,2,6,12,9,8]

console.log(arr.sort())

function compare (val1, val2) {
  return val1 - val2
}

arr.sort(compare)
```