# 转译ES6

`npm i babel-core babel-loader babel-preset-env babel-preset-stage-0 -D`


> .babelrc
```
{
    "presets": ["env", "stage-0"]   // 从右向左解析
}
```

```js
module.exports = {
    module: {
        rules: [
            {
                test:/\.js$/,
                use: 'babel-loader',
                include: /src/,          // 只转化src目录下的js
                exclude: /node_modules/  // 排除掉node_modules，优化打包速度
            }
        ]
    }
}
```