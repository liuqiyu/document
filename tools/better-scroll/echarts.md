# 使用echarts外链问题


> 问题1： 使用echarts外链导致出现`echarts is not defined`问题

```js
let myChart = echarts.getInstanceByDom(document.getElementById('main-chart'))
  if (myChart === undefined) {
    /* global echarts:true */
    /* eslint no-undef: "error" */
    myChart = echarts.init(document.getElementById('main-chart'))
  }
```