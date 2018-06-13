# 分支

最先进的分布式版本控制系统

<hr/>

#### 分支管理

* 查看分支： `git branch`
* 创建分支： `git branch <name>`
* 切换分支： `git checkout <name>`
* 创建+切换分支： `git checkout -b <name>`
* 合并某分支到当前分支： `git merge <name>`
* 删除分支： `git branch -d <name>`

<hr/>

#### 解决冲突

人生十有八九不如意，我们常常与遇到合并产生冲突的时候。

当在`lqy2`分支上提交修改后，切换到`master`上，提交相同已修改文件的代码。执行`git merge lqy2`，会出现下面情况。

```
<<<<<<< HEAD
master
=======
lqy2
>>>>>>> lqy2
```

我们手动处理，选择需要留下的代码。

<hr/>

#### 查看分支情况

** git log --graph --pretty=oneline --abbrev-commit **

```
* a68d2bc 'aa'
* 51225c0 'aa'
*   8bbf92a '推送'
|\
| * a7fa0fc 'lqy2修改'
* | f33ba70 'master修改'
|/
* e5a4e9e '修改lqy2'
* 24189d5 '提交Lqy2'
* 561285f '安安'
* cd8da40 'aa'
:...skipping...
```





