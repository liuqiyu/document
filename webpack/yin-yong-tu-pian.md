# 引用图片

`npm i file-loader url-loader -D`

在`webpack.config.js`修改配置

```js
 {
                test: /\.(jpe?g|png|gif)$/,
                use: [
                    {
                        loader: 'url-loader',
                        options: {
                            limit: 8192,    // 小于8k的图片自动转成base64格式，并且不会存在实体图片
                            outputPath: 'images/'   // 图片打包后存放的目录
                        }
                    }
                ]
            }

作者：chenhongdong
链接：https://juejin.im/post/5adea0106fb9a07a9d6ff6de
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```