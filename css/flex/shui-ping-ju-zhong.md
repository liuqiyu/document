# 水平居中

![](/assets/企业微信截图_15324824123718.png)

** HTML **

```html
    <div class="center"></div>
```

<hr/>

### 方案1

```css
.center {
            width: 100px;
            height: 100px;
            position: absolute;
            left: 50%;
            top: 50%;
            margin-left: -50px;
            margin-top: -50px;
            background: red;
        }
```