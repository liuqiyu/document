# http响应码

** 5种类型 **

* 1**： 信息，服务器受到请求，需要请求者继续执行操作
    * 100 继续请求
    * 101 切换协议，只能切换到更高级的协议
* 2**： 成功，操作成功接收并处理
    * 200 请求成功
    * 201 成功创建并创建新的资源
    * 202 已接受。已经接受请求，但未处理完成
    * 203 非授权信息。请求成功
    * 204 无内容。服务器处理成功，但未返回内容
    * 205 重置内容。
    * 206 服务器处理了部分GET请求
* 3**： 重定向，需要进一步的操作以完成请求
    * 300 多种选择。请求的资源可包括多个位置，相应可返回一个资源特征与地址的列表用于用户终端（例如：浏览器）选择
    * 301 永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新URI。今后任何新的请求都应使用新的URI代替
    * 302 临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI
    * 303 查看其它地址。与301类似。使用GET和POST请求查看
    * 304 未修改。所请求的资源未修改，服务器返回此状态码时，不会返回任何资源。客户端通常会缓存访问过的资源，通过提供一个头信息指出客户端希望只返回在指定日期之后修改的资源
    * 305 使用代理。所请求的资源必须通过代理访问
    * 306 已经被废弃的HTTP状态码
    * 307 临时重定向。与302类似。使用GET请求重定向
* 4**： 客户端错误，请求包含语法错误或无法完成请求
    * 400 客户端请求的语法错误，服务器无法理解
    * 401 请求要求用户的身份认证
* 5**： 服务器错误，服务器在处理请求的过程中发生错误
    * 500 服务器内部错误，无法完成请求
    * 501 服务器不支持请求的功能，无法完成请求
    * 502 充当网关或代理的服务器，从远端服务器接收到了一个无效的请求   Bad Gateway
    * 503 超载或系统维护，服务器暂时的无法处理客户端的请求。
    * 504 Gateway Time-out 充当网关或代理的服务器，未及时从远端服务器获取请求
    * 505 服务器不支持请求的HTTP协议的版本，无法完成处理