# 分支

最先进的分布式版本控制系统



</hr>

git branch 所有

git branch -r 远程

git branch -b lqy 创建lqy分支

git checkout lqy  切换到lqy分支


git push origin lqy 推到lqy分支


git pull <远程主机名> <远程分支名>:<本地分支名>

git checkout master

git mergin lqy    => lqy分支合并到master

git branch -D lqy   删掉本地分支


git status 文件被修改了，但没有准备提交的修改。

git diff 代码与版本的差异

git commit -m 'update' 提交修改

git log --pretty=oneline  

```
cd8da402c018e7a70aa81585664c657415cb65b7 'aa'
2bdb3e539b35f2bcd00edc7cede12f14440ab936 'aa'
3414ee387213d0f57b823335c926047561429a79 'addIndex2'
1cf47b7fa7876177d0b2f7f2ce274a0629f2a8e6 'lqy'
7adee8d4ee4c4d4093559d9b680ca74f551b076f 'master'

```



