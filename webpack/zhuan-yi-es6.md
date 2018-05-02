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

作者：chenhongdong
链接：https://juejin.im/post/5adea0106fb9a07a9d6ff6de
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```