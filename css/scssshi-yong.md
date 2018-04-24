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
```

* base.scss

```css
$primary-color: red;
```

* login.vue

```js
<style scoped lang="scss">
  @import './../../assets/css/base';

  div {
    color: $primary-color;
    p {
      color: $primary-color;
      &:hover {
        color: pink;
      }
    }
  }
</style>
```

* 使用混合器

```css
@mixin rounded-corners {
  -moz-border-radius: 5px;
  -webkit-border-radius: 5px;
  border-radius: 5px;
}
notice {
  background-color: green;
  border: 2px solid #00aa00;
  @include rounded-corners;
}
```