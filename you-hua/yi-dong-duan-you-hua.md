# 移动端H5前端性能优化指南

*Mobile我们提出3秒渲染完成首屏指标，首屏加载3秒完成或者使用Loading。基于联通3G网络平均338KB/S(2.71Mb/s)，所以首屏支援不应超过1014KB*

<hr/>


### 1、加载优化

* 合并CSS,JavaScript
* 合并小图片，使用雪碧图
* 缓存一切可缓存的资源
* 使用长Cache
* 使用外联式引用CSS、JAVASCRIPT
* 压缩HTML、CSS、JAVASCRIPT
* 启用GZip
* 使用首屏加载
* 使用按需加载
* 使用滚屏加载
* 通过Media Query加载
* 增加Loading进度条
* 减少Cookie
* 避免重定向
* 异步加载第三方资源

### 2、CSS优化

* CSS写在头部、JAVASCRIPT写在尾部或者异步
