# webpack4学习笔记

首先安装`webpack`和`webpack-cli`。

```
npm i webpack -D

npm i webpack-cli -D
```

* `webpack-dev-server`

`npm i webpack-dev-server -D`是一个小型的`Node.js Express`服务器。它使用`webpack-dev-middleware`来服务于`webpack`的包。除此自外，它还有一个通过Sock.js来连接到服务器的微型运行时.



### 配置文件

```
"build": "webpack",         npm run build   // 打包后的文件，这个是生产环境，生成/dist文件夹。上线需要
"dev":"webpack-dev-server"  npm run dev     // 这是开发环境打包的文件，由于dev-server帮我们把文件放入内存当中，所以不会输出打包后的/dist文件夹
```