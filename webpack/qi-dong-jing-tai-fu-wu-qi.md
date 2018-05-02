# 启动静态服务器

* 自动启动服务器

* 自动打开浏览器

* 开发环境中 -- 无需打包 -- `npm run dev` => `webpack-dev-server`

代码如下：

```js
module.exports = {
    devServer: {
        contentBase: './dist',
        host: 'localhost',      // 默认是localhost
        port: 3000,             // 端口
        open: true,             // 自动打开浏览器
        hot: true               // 开启热更新
    }
}
```

当然在npm run dev命令下，打包的文件存在于内存中，并不会产生在dist目录下