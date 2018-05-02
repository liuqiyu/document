# 0配置打包

```js
// node v8.2版本以后都会有一个npx
// npx会执行bin里的文件

npx webpack     // 不设置mode的情况下 打包出来的文件自动压缩

npx webpack --mode development  // 设置mode为开发模式，打包后的文件不被压缩
```