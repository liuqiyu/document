# 打包优化

## 打包后的文件说明

使用vue+webapck，打包文件后会生成3个Js文件`app.js` `vendor.js` `manifest.js`
下面分析3个js各自的职责。

> app.js

基本上是按照编写的那个app.vue（.vue/.js），没有这个跑不起来
    
> vendor.js   // 公共部分

vue-cli全家桶默认配置里面这个chunk就是将所有的node_modules/里require(import)的依赖都打包到这里，所以这个就是所有node_modules/下的被require(import)的js文件

> manifest.js

最后一个chunk，被注入了webpackJsonp的定义及异步加载相关的定义(webpack调用CommonsChunkPlugin处理后模块管理的核心,因为是核心,所以要第一个进行加载,不然会报错).



## 案列说明

> vendor.js 打包后文件过大优化
    
 * 在使用element-ui框架局部引入，会全部引入，导致js过大
    
    * 首先，需要安装babel-plugin-component：
    
    ```
        npm install babel-plugin-component -D
    ```
    
    * 然后，将 .babelrc 修改为：
    
    ```
        {
          "presets": [
            ["es2015", { "modules": false }]
          ],
          "plugins": [["component", [
            {
              "libraryName": "element-ui",
              "styleLibraryName": "theme-chalk"
            }
          ]]]
        }
        
        // 与之前的代码合并如下
        
        {
          "presets": [
            ["env", {
              "modules": false,
              "targets": {
                "browsers": ["> 1%", "last 2 versions", "not ie <= 8"]
              }
            }],
            "stage-2"
          ],
          "plugins": [
            "transform-vue-jsx",
            "transform-runtime",
            ["component", [
              {
                "libraryName": "element-ui",
                "styleLibraryName": "theme-chalk"
              }
            ]]
          ]
        }
    ```
    
    * 这样，打包后的vendor.js从890KB减少到290KB。
  
> 使用Gzip进行压缩，去掉.map文件
    
* 修改config/index.js
    
    ```
        productionSourceMap: false,   // 不打包.map文件
        productionGzip: true,         // 压缩
    ```
    
> 组件引入

* 按需引用

