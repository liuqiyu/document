# 圣杯布局1

![](/assets/企业微信截图_15325007928611.png)

** HTML **

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>圣杯布局</title>
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
            background: #e1e1e1;
            display: flex;
            flex-direction: column;
        }
        .header {
            height: 40px;
            background: yellow;
            display: flex;
        }
        .h-left {
            width: 100px;
            height: 40px;
            background: #333333;
            flex: none;
        }
        .h-right {
            flex: 1;
            overflow: hidden;
            text-align: center;
        }
        .content {
            flex: 1;
            background: red;
            align-items: center;
        }
        .footer {
            height: 40px;
            background: deeppink;
        }
    </style>
</head>
<body>
<div class="container">
    <div class="header">
        <div class="h-left">头部 - 左</div>
        <div class="h-right">头部 - 右</div>
    </div>
    <div class="content">圣杯布局</div>
    <div class="footer">底部</div>
</div>
</body>
</html>
```