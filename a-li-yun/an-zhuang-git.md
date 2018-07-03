# 阿里云服务器安装git

#### 1、下载git

`sudo wget https://www.kernel.org/pub/software/scm/git/git-2.8.0.tar.gz`

#### 2、安装以来

`sudo yum -y install zlib-devel openssl-devel cpio expat-devel gettext-devel curl-devel perl-ExtUtils-CBuilder perl-ExtUtils- MakeMaker`

#### 3、解压

`sudo tar -zxvf git-2.8.0.tar.gz`

#### 4、执行命令

```json
sudo make prefix=/usr/local/git all

sudo make prefix=/usr/local/git install

```

[地址](https://blog.csdn.net/Andy86869/article/details/79150275)