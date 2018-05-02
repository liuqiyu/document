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

**当然在npm run dev命令下，打包的文件存在于内存中，并不会产生在dist目录下**

**but It's not so simple**,因为热更新还需要配置一个webpack自带的插件并且还要在主要js文件里检查是否有module.hot
**会报错，会报错，会报错**

```js
// webpack.config.js
let webpack = require('webpack');

module.exports = {
    plugins: [
        // 热替换，热替换不是刷新
        new webpack.HotModuleReplacementPlugin()
    ],
    devServer: {
        contentBase: './dist',
        hot: true,
        port: 3000
    }
}

作者：chenhongdong
链接：https://juejin.im/post/5adea0106fb9a07a9d6ff6de
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```
