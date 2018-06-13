# 标签管理

<hr/>

#### 查看标签  

git tag

#### 创建标签

git tag v1.0

#### 给版本打标签

查看所有版本: git log --pretty=oneline --abbrev-commit

```
7db38cd 'tag'
a68d2bc 'aa'
51225c0 'aa'
8bbf92a '推送'
a7fa0fc 'lqy2修改'
```

给指定版本打标签： git tag v0.9 f52c633

#### 查看指定标签

git show v1.1

```
commit 7db38cd99942a0daf8bfb447275d94a35a3cf0fb
Author: lqy <1064839051@qq.com>
Date:   Wed Jun 13 18:04:32 2018 +0800

    'tag'

diff --git a/bb.txt b/bb.txt
index 7314fc3..4c27f86 100644
--- a/bb.txt
+++ b/bb.txt
@@ -1 +1 @@
-master312312321321321
\ No newline at end of file
+tag2
\ No newline at end of file
```