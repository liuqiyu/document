# eslint 报错规避

### 使用echarts外链问题

> 问题1： 使用echarts外链导致出现`echarts is not defined`问题
> 附加： 避免使用echarts造成内存泄露问题

```js
// 避免使用echarts造成内存泄露问题

let myChart = echarts.getInstanceByDom(document.getElementById('main-chart'))
if (myChart === undefined) {
  /* global echarts:true */
  /* eslint no-undef: "error" */
  myChart = echarts.init(document.getElementById('main-chart'))
}
```

> 问题2： 不支持 `new`

```JS
/* eslint-disable no-new */
```