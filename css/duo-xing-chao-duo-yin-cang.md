# 多行超出隐藏省略号

```css
overflow:hidden; 

text-overflow:ellipsis;

display:-webkit-box; 

-webkit-box-orient:vertical;

-webkit-line-clamp:2; 

// 英文换行
word-wrap:break-word; 
word-break:break-all; 
```
### 一条省略号

* overflow:hidden; // 文本超出隐藏
* text-overflow:ellipsis; // 溢出用省略号显示
* white-space:nowrap; // 溢出不换行,只显示一条
