# input与textarea的区别，并用div模拟textarea

* `<textarea>`标签是成对的，有结束标签进行闭合，标签的内容写在标签对中间；`<input>`是单个标签，标签的内容通过 value 属性设置；
* `<textarea>`的值是纯文本；`<input>`的值根据类型不同而不同；
* `<textarea>`没有type属性；`<input>`有多种type来满足表单与用户的数据交互；
* `<textarea>`的值可以是多行的，并且有rows和cols来控制多行结构；`<input>`的值是单行的；

<hr/>

### 用div模拟textarea标签

```html
<div class="textarea" contenteditable="true" placeholder="This is placeholder"></div>

.textarea {
  height: 200px;
  width: 300px;
  padding: 4px;
  border: 1px solid #888;
  resize: vertical;
  overflow: auto;
}

.textarea:empty:before {
  content: attr(placeholder);
  color: #bbb;
}
```