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
* 预加载
    * 可感知Loading
    * 提前加载下一页
    * 对用户行为分析，可以在当前页加载下一页资源，提升速度
* 通过Media Query加载
* 增加Loading进度条
* 减少Cookie
* 避免重定向
* 异步加载第三方资源
* 减少HTTP请求

### 2、CSS优化

* CSS写在头部、JAVASCRIPT写在尾部或者异步
* 避免图片和iFrame等的空Src
* 尽量避免重设图片大小
* 图片尽量避免使用DataURL
* 尽量避免在HTML标签中写Style属性
* 避免CSS表达式
* 移除空的CSS规则
* 正确使用Display的属性
* 不滥用Float
* 不滥用Web字体
* 不声明过多的Font-size
* 值为0时不需要任何单位
* 标准化各种浏览器前缀
    * 无前缀应放在最后。
    * CSS动画只用（-webkit- 无前缀）两种即可
    * 其它前缀为“-webkit- -moz- -ms-无前缀”四种（-o-Opera浏览器改用blink内核，所以淘汰）
* 避免让选择符看起来像正则表达式

### 3、图片优化

* 使用智图
* 使用（css3、SVG、IconFont）代替图片
* 使用Srcset
* webP优于JPG
* PNG8优于GIF
* 首次加载不大于1014KB(基于3秒联通平均网速所能达到值)
* 图片不宽于640

### 4、脚本优化

* 减少重绘和回流
* 缓存DOM选择与计算
* 缓存列表length
* 尽量使用时间代理，避免批量绑定事件
* 尽量使用ID选择器
* 使用touchStart、touchend代替click

## 5、渲染优化

* HTML使用Viewport
    * <meta name=”viewport” content=”width=device-width, initial-scale=1″>
* 减少Dom节点
* 尽量使用CSS3动画
* 合理使requestAnimationFrame动画代替setTimeout
* 适当使用Canvas动画
* Touchmove、Scroll时间会导致多次渲染
* 使用{ CSS3 transitions、CSS 3D transforms、Opacity、Canvas、WebGL、Video } 来触发GPU渲染