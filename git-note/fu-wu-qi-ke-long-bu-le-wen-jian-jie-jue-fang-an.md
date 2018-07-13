# 服务器克隆不了文件

```
Permissiondenied (publickey).

fatal:Could not read from remote repository.

Pleasemake sure you have the correct access rights

andthe repository exists.
```

* ssh-keygen -t rsa -C "1064839051@qq.com"

* cat ~/.ssh/id_rsa.pub

* 将公钥复制到`github` `alicode` ssh. -- 复制这个公钥放到你的个人设置中的SSH/My SSH Keys下，请完整拷贝从ssh-开始直到你的用户名和主机名为止的内容。

* 然后 git clone **************