# 引用css...

### css
```
npm i style-loader css-loader -D

```

```
let path = require('path');
let HtmlWebpackPlugin  = require('html-webpack-plugin');

module.exports = {
  entry: {
    main: ["./src/js/main.js"],
    login: ["./src/js/login.js"]
  },
  output: {
    filename: '[name].js',
    path: path.resolve('dist')
  },
  module: {
    rules: [
      {
        test: /\.(css|less)$/,
        use: [
          {loader: 'style-loader'},
          {loader: 'css-loader'},
          {loader: 'less-loader'}
        ]
      }
    ]
  },
  plugins:[
    new HtmlWebpackPlugin({
      template: './main.html',
      filename: 'main.html',
      chunks: ['main']
    }),
    new HtmlWebpackPlugin({
      template: './login.html',
      filename: 'login.html',
      chunks: ['login']
    })
  ]
}
```
