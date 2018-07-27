# http协议详解

*http*全过程
<hr>
输入域名(URL) -> DNS映射为IP（浏览器缓存 -> 操作系统缓存 -> 读取本地host文件） -> TCP三次握手 -> HTTP请求 -> HTTP响应 -> (浏览器跟踪重定向地址) -> 服务器处理请求 -> 服务器返回一个html响应 -> (视情况决定释放TCP连接) -> 客户端解析HTML -> 获取嵌入在HTML中的对象重新发起HTTP请求 

### TCP三次握手

* client -> server: 发起一个TCP连接，同步报文
* server -> client: 应答报文，表示已创建连接
* client -> server: 应答报文，表示收到已连接

### 输入域名

一个点分隔一级，域名由分量组成，一级为一个分量。
```js

网站(www) ... 三级域名(pic)  ...二级域名(baidu) ...顶级域名(com)
www.pic.baidu.com

```
* 解决跨域问题
    * jsonp
    * 服务器代理:proxy
    * CORS
    
### http与https的区别

`http+加密+认证+完整性保护=https`

* http: 应用层的无状态，超文本传输协议，端口是80。
* https: 只是http通信接口部分用SSL和TLS协议替代。http直接和TCP通信，而HTTPS使用SSL所以是先和SSL通信，再由SSL和TCP通信。端口为443

