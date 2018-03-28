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