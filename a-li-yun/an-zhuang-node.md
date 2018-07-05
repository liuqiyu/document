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



