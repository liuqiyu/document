# 二点

![](/assets/企业微信截图_20180725161537.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>二点</title>
    <style>
        body, html {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }
        .demo{
            margin-left: 200px;
            margin-top: 200px;
            padding: 10px;
            width: 200px;
            height: 200px;
            background: #fff;
            border: 1px solid #111;
            border-radius: 10px;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
        }
       .item {
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

        .item:nth-child(2) {
            align-self: flex-end;
        }
    </style>
</head>
<body>
<div class="demo">
  <div class="item">1</div>
  <div class="item">2</div>
</div>
</body>
</html>
```