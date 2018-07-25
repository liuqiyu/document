# 一点

![](/assets/1.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>flex-direction</title>
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
            width: 200px;
            height: 200px;
            background: #fff;
            border: 1px solid #111;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
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
    </style>
</head>
<body>
<div class="demo">
  <div class="item">1</div>
</div>
</body>
</html>
```