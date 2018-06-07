# 服务器

```
ssh dev@192.168.1**.***
dev@culckqooy
sudo -i
dev@culckqooy
cd /data/www/product_selection_front
git status
git pull
ll
pwd
cd -
logout

ssh码地址： `C:\Users\Administrator\.ssh\id_rsa.pub`
ssh-keygen
ssh-copy-id dev@192.168.1**.***

```

### 前端发布代码并配置服务器

```
/data/www  git clone ~

cd msoa
git status
ls
cd dist
pwd
cd /etc/nginx/conf.d/
ls
cp ~~ msoa.stosz.com.conf
vim msoa.stosz.com.conf
service nginx restart
cat ~ 查看

server {
     listen 8099;
     server_name msoa.stosz.com;
     index index.html;
     root /data/www/msoa/dist;
}
```