# 引用css...

### css
```
npm i style-loader css-loader -D

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
