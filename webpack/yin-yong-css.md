# 引用css...

### css与less
```
npm i style-loader css-loader -D
// 引入less文件的话，也需要安装对应的loader
npm i less less-loader -D

```

```
module.exports = {
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
  }
}
```
