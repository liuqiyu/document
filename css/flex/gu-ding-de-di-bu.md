# 固定的底部

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        body, html {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }
        .Site {
            display: flex;
            min-height: 100vh;
            flex-direction: column;
        }

        .Site-content {
            flex: 1;
        }
        header {
            flex: none;
            width: 100%;
            height: 40px;
            background: red;
        }
        footer {
            flex: none;
            height: 40px;
            width: 100%;
            background: red;
        }
    </style>
</head>
<body class="Site">
<header>...</header>
<main class="Site-content">
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
    <p>1</p>
</main>
<footer>...</footer>
</body>
</html>
```