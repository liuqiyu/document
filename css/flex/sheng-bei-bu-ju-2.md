# 圣杯布局2

![](/assets/企业微信截图_15325015203016.png)

** HTML **

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        html, body {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }

        .container {
            width: 100%;
            height: 100%;
            display: flex;
            display: -webkit-flex;
        }

        .left {
            width: 200px;
            height: 100%;
            background: pink;
            flex: none;
        }

        .content {
            flex: 1;
            height: 100%;
            background: antiquewhite;
            overflow: hidden;
        }
        .top {
            height: 60px;
            background: aquamarine;
        }
    </style>
</head>
<body>
<div class="container">
    <div class="left"></div>
    <div class="content">
        <div class="top"></div>
    </div>
</div>
</body>
</html>
```