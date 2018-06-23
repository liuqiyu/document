# nginx.conf

`nginx.conf`就是nginx服务器的配置文件。

* 普通的配置文件
```json
# 工作进程数，和CPU核数相同
worker_processes 1;

events {
    worker_connections 1024;
}
http {
    upstream firstdemo {
        server 39.106.145.33;
        server 47.93.6.93;
    }
	
    server {
		listen       1993;
		server_name  www.abab.com;
		location / {
			root   html;
			index  index.html index.htm;
		}
	}
	
	server {
		listen      4567;
		server_name www.example.com;
		location / {
			proxy_pass http://192.168.220.189:93;
		}
	}
}
```

* 配置文件解释
![](/assets/TIM截图20180623143109.png)
