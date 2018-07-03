# 阿里云安装nginx

<hr/>

```
 yum install -y gcc gcc-c++
 cd /usr/local/
 wget http://jaist.dl.sourceforge.net/project/pcre/pcre/8.33/pcre-8.33.tar.gz
$ tar -zxvf pcre-8.36.tar.gz
$ cd pcre-8.36
$ ./configure
$ make && make install

如报错:configure: error: You need a C++ compiler for C++ support
解决:yum install -y gcc gcc-c++

```

<hr/>

```json
$ cd /usr/local/
$ wget http://www.openssl.org/source/openssl-1.0.1j.tar.gz
$ tar -zxvf openssl-1.0.1j.tar.gz
$ cd openssl-1.0.1j
$ ./config
$ make && make install
```

</hr>

```json
cd /usr/local/
wget http://zlib.net/zlib-1.2.11.tar.gz
tar -zxvf zlib-1.2.11.tar.gz
./configure
make && make install
```

<hr/>

```json

$ cd /usr/local/
$ wget http://nginx.org/download/nginx-1.8.0.tar.gz
$ tar -zxvf nginx-1.8.0.tar.gz
$ cd nginx-1.8.0 
$ ./configure --user=nobody --group=nobody --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_gzip_static_module --with-http_realip_module --with-http_sub_module --with-http_ssl_module
(注: --with-http_ssl_module:这个不加后面在nginx.conf配置ssl:on后,启动会报nginx: [emerg] unknown directive "ssl" in /opt/nginx/conf/nginx.conf 异常)
$ make && make install
 
报错:./configure: error: the HTTP gzip module requires the zlib library

在–prefix后面接以下命令:
--with-pcre=/usr/local/pcre-8.36 指的是pcre-8.36 的源码路径。--with-zlib=/usr/local/zlib-1.2.8 指的是zlib-1.2.8 的源码路径。
```

<hr/>

```json
启动： /usr/local/nginx/sbin/nginx

重启： /usr/local/nginx/sbin/nginx -s reload

停止： /usr/local/nginx/sbin/nginx -s stop

测试配置文件是否正常: /usr/local/nginx/sbin/nginx -t
```