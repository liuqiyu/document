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
        // 或者 margin 换成transform: translate(-50%,-50%);
```

### 方案2

```css
 .center {
            width: 100px;
            height: 100px;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            margin:auto;
            background: red;
        }
```