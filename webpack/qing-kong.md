# 清空dist文件

`npm i clean-webpack-plugin -D`

```js
let CleanWebpackPlugin = require('clean-webpack-plugin');

module.exports = {
    plugins: [
        // 打包前先清空
        new CleanWebpackPlugin('dist')  
    ]
}

作者：chenhongdong
链接：https://juejin.im/post/5adea0106fb9a07a9d6ff6de
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```