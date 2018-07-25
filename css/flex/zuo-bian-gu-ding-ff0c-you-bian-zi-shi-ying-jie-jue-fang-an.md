# 左边固定，右边自适应解决方案

![](/assets/企业微信截图_15324289479106.png)

** html **
```
<div class="wrapper">
    <div class="left">左边固定</div>
    <div class="right">
        <div class="content">右边</div>
    </div>
</div>
```

### 使用flex实现

```css
<style>
    .wrapper {
        display: flex;
        width: 400px;
        height: 200px;
    }

    .left {
        width: 100px;
        height: 100%;
        background: red;
        flex: none;
        line-height: 200px;
        text-align: center;
        color: #fff;
    }
    .right {
        background: blue;
        flex: 1;
        height: 100%;
        overflow: hidden;
    }
    .content {
        width: 100%;
        height: 100px;
        background: pink;
        line-height: 100px;
        text-align: center;
    }
</style>
```

### 其他解决方案

```css
<style>
    .wrapper {
        width: 400px;
        height: 200px;
        position: relative;
    }

    .left {
        width: 100px;
        height: 100%;
        background: red;
        line-height: 200px;
        text-align: center;
        color: #fff;
        position: absolute;
        opacity: 0.1;
        top: 0;
        left: 0;
    }
    .right {
        background: blue;
        height: 100%;
        overflow: hidden;
        margin-left: 100px;
    }
    .content {
        width: 100%;
        height: 100px;
        background: pink;
        line-height: 100px;
        text-align: center;
    }
</style>
```