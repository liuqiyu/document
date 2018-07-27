# 经典的后台布局

![](/assets/企业微信截图_15326824247043.png)

** 代码如下： **

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        * {
            box-sizing: border-box;
            padding: 0;
            margin: 0;
        }

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .main {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: row;
        }

        .leftnav {
            flex: none;
            width: 200px;
            height: 100%;
            background: salmon;
        }

        .content {
            flex: 1;
            display: flex;
            flex-direction: column;
            width: 100%;
            overflow: hidden;
            background: #e1e1e1;
        }

        .header {
            height: 40px;
            flex: none;
            background: aquamarine;
        }

        .box {
            flex: 1;
            background: pink;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .search {
            height: 40px;
            background: cadetblue;
        }

        .height {
            height: 80px;
        }

        .table-wrapper {
            flex: 1;
            padding: 10px 0;
            overflow: hidden;
        }
        .table {
            height: 100%;
            background: rosybrown;
            overflow-y: auto;
        }
    </style>
</head>
<body>
<div class="main">
    <div class="leftnav">left</div>
    <div class="content">
        <div class="header">header</div>
        <div class="box">
            <div class="search" id="search">search</div>
            <div class="table-wrapper">
                <div class="table">
                    <p>1</p>
                    <p>1</p>
                    <p>1</p>
                    <p>1</p>
                    <p>1</p>
                    <p>1</p>
                </div>
            </div>
        </div>
    </div>
</div>
<script>
    var $search = document.getElementById('search');
    $search.addEventListener('click', function() {
        var class1 = 'height';
        var classList = this.className.split(' ');
        console.log(classList.indexOf(class1));
        if (classList.indexOf(class1) >0) {
            this.classList.remove(class1);
        } else {
            this.classList.add(class1);
        }
    });
</script>
</body>
</html>
```