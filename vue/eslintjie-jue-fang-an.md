# eslint解决方案

<hr/>

##### 变量参数未使用

```js
  /* eslint-disable no-unused-vars */
    objectSpanMethod({ row, column, rowIndex, columnIndex }) {
      if (columnIndex === 0) {
        if (row.length > 0) {
          return {
            rowspan: row.length,
            colspan: 1,
          };
        }
        return {
          rowspan: 0,
          colspan: 0,
        };
      }
      return {
        rowspan: 1,
        colspan: 1,
      };
    },
```