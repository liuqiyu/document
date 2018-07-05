# 阿里云服务器安装node

#### 1、下载node最新包

`wget https://nodejs.org/dist/v8.4.0/node-v8.4.0-linux-x64.tar.xz`

#### 2、解压缩

`tar -xvJf node-v8.4.0-linux-x64.tar.xz`

#### 3、编辑profile文件

`vi /etc/profile //进入vim编辑模式`

文件最后插入下面代码：

```json
export NODE_HOME=/kaway/software/node-v8.4.0-linux-x64/bin //解压后的文件目录，可用pwd查看，bin为文件家中的子目录
export PATH=$NODE_HOME:$PATH
```
#### 4、重启

```
node -v

// v8.4.0
````

#### 5、部署node服务

** 永久开启 **

* 安装 `npm install -g pm2`

```json
$ pm2 logs 显示所有进程日志
$ pm2 stop all 停止所有进程
$ pm2 restart all 重启所有进程
$ pm2 reload all 0秒停机重载进程 (用于 NETWORKED 进程)
$ pm2 stop 0 停止指定的进程
$ pm2 restart 0 重启指定的进程
$ pm2 startup 产生 init 脚本 保持进程活着
$ pm2 web 运行健壮的 computer API endpoint (http://localhost:9615)
$ pm2 delete 0 杀死指定的进程
$ pm2 delete all 杀死全部进程
```

