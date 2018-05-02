# 多页面打包详解

所谓多页面，就是多个页面需要配置多个出口文件。无论是单页面还是多页面，我们都可以使用`html-webpack-plugin`插件来`copy`html文件。

`npm i html-webpack-plugin`

```
let path = require('path');
let HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    // 多页面开发，怎么配置多页面
    entry: {
        index: './src/index.js',
        login: './src/login.js'
    },
    // 出口文件  
    output: {                       
        filename: '[name].js',
        path: path.resolve('dist')
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: './src/index.html',   
            filename: 'index.html',
            chunks: ['index']   // 对应关系,index.js对应的是index.html
        }),
        new HtmlWebpackPlugin({
            template: './src/login.html',
            filename: 'login.html',
            chunks: ['login']   // 对应关系,login.js对应的是login.html
        })
    ]
}
```

**.html最终打包后的地址会根据`output`地址打包，所哟可以配置`HtmlWebpackPlugin`的`filename`：filename: './../index.html'**

最终允许`webpack`命令会生成`/dist`文件夹如下：

```
├── dist
    ├── login.html
    ├── login.js
    ├── main.html
    ├── main.js
```