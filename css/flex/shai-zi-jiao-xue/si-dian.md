# 四点

![](/assets/企业微信截图_20180725162202.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>三点</title>
    <style>
        body, html {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }

        .box {
            margin-left: 200px;
            margin-top: 200px;
            padding: 10px;
            width: 200px;
            height: 200px;
            background: #fff;
            border: 1px solid #111;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .column {
            display: flex;
            justify-content: space-between;
        }

        .item {
            display: block;
            overflow: hidden;
            width: 40px;
            height: 40px;
            background: #111111;
            color: #fff;
            border-radius: 10px;
            line-height: 40px;
            text-align: center;
            border: 1px solid #333;
        }
    </style>
</head>
<body>
<div class="box">
    <div class="column">
        <span class="item">1</span>
        <span class="item">2</span>
    </div>
    <div class="column">
        <span class="item">3</span>
        <span class="item">4</span>
    </div>
</div>
</body>
</html>
```