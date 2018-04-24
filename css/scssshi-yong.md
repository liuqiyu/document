# vue使用scss

* 安装依赖
`npm install sass-loader node-sass vue-style-loader --D`

* 配置文件 `webpack.base.config.js`
```js
module: {
    rules: [
      {
        test: /\.vue$/,
        loader: 'vue-loader',
        options: vueLoaderConfig
      },
      {
        test: /\.js$/,
        loader: 'babel-loader',
        include: [resolve('src'), resolve('test')]
      },
      {
        test: /\.(png|jpe?g|gif|svg)(\?.*)?$/,
        loader: 'url-loader',
        options: {
          limit: 10000,
          name: utils.assetsPath('img/[name].[hash:7].[ext]')
        }
      },
      {
        test: /\.(woff2?|eot|ttf|otf)(\?.*)?$/,
        loader: 'url-loader',
        options: {
          limit: 10000,
          name: utils.assetsPath('fonts/[name].[hash:7].[ext]')
        }
      },
      {  //从这一段上面是默认的！不用改！下面是没有的需要你手动添加，相当于是编译识别sass!
        test: /\.scss$/,
        loaders: ["style", "css", "sass"]
      }
    ]
  }

作者：飞奔的阿加西
链接：https://www.jianshu.com/p/8e60048baeb7
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```