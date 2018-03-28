# element-ui 自定义表头

每个表头需要有一个图标，鼠标经过时显示其注释。

```html
<el-table-column
:width="commonWidth"
:class-name="hiddenClass"
prop="session_count"
label="会话数"
:render-header="renderHeader"
sortable="custom">
</el-table-column>
```

```js
  // 会话数
renderHeader (createElement, { column, index }) {
  return createElement(
    'span',
    {
      'class': 'renderTableHead'
    },
    [
      createElement('span', ['会话数']),
      createElement(
        'el-tooltip',
        {
          attrs: {
            content: '会话是指在指定的时间段内在您的网站上发生的一系列用户互动。' +
            '例如，一次会话可以包含多个网页浏览、事件、社交互动和电子商务交易会话结束的方式分为以下两种：　一.将特定时间作为过期标志：　1.不活动状态超过30分钟　' +
            '2.午夜 　二.广告系列变更：用户通过一个广告系列来到网站，随后离开，然后通过另一个广告系列返回网站。',
            placement: 'top' }
        },
        [
          createElement('span', [
            createElement('span', {
              attrs: { class: 'el-icon-question tableHeaderIcon' }
            })
          ])
        ]
      )
    ]
  )
},
```