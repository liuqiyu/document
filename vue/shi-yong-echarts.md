# 使用echarts

使用echarts并不难，因为echarts的文档很健全。但是如何在使用echarts同事考虑打包性能的问题，便是一个课题。`npm install echarts --save` 下载后并`import echarts from 'echarts'`引入使用是一种方法，但是当其打包时会造成，`vendor.js`过大。从而使浏览器加载速度变慢，影响性能。如何让打包体积变小，如何高效使用echarts，便是今日要记录的。

#### 使用外链方式

```js
// index.html    
<script src="./static/script/echarts.common.min.js"></script>

let myChart = echarts.getInstanceByDom(document.getElementById('chart'))
if (myChart === undefined) {
  /* global echarts:true */
  /* eslint no-undef: "error" */
  myChart = echarts.init(document.getElementBy+-  