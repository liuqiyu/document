# git 常用的命令


## 基本命令行  
repositories => repo => 仓库

> git init : 创建仓库

> git clone : 获取远程的仓库，创建一个local copy  // git clone https://github.com/liuqiyu/document.git newName

> git status : 查询repo的状态

> git add . : 在提交之前，Git有一个暂存区（staging area）,可以放入新添加的文件或者新的改动。commit时提交的改动是上一次加入到`staging area`中的改动。

> git diff : 比较差异

> git commit : 提交已经被add的改动
    
    git commit --amend : 增补提交. 会使用与当前提交节点相同的父节点进行一次新的提交,旧的提交将会被取消.

> git branch : 用来列出分支,创建分支和删除分支.
    
    git branch -v可以看见每一个分支的最后一次提交
    
    git branch: 列出本地所有分支,当前分支会被星号标示出.
    
    git branch (branchname): 创建一个新的分支(当你用这种方式创建分支的时候,分支是基于你的上一次提交建立的). 
    
    git branch -d (branchname): 删除一个分支.
    
    git push (remote-name) :(branch-name): delete a remote branch.

> git checkout ：git checkout (branchname)  切换到一个分支

    git checkout -b (branchname) // 创建并切换到新的分支， 这个命令是将git branch newbranch和git checkout newbranch合在一起的结果.
    
> git merge

    把一个分支merge进当前的分支.
    git merge [alias]/[branch]
    把远程分支merge到当前分支.
    
> git pull

    git pull会首先执行git fetch,然后执行git merge,把取来的分支的head merge到当前分支.这个merge操作会产生一个新的commit.    
    如果使用--rebase参数,它会执行git rebase来取代原来的git merge.

> git push

    将会把当前分支merge到alias上的[branch]分支.如果分支已经存在,将会更新,如果不存在,将会添加这个分支.
    如果有多个人向同一个remote repo push代码, Git会首先在你试图push的分支上运行git log,
    检查它的历史中是否能看到server上的branch现在的tip,如果本地历史中不能看到server的tip,
    说明本地的代码不是最新的,Git会拒绝你的push,让你先fetch,merge,之后再push,这样就保证了所有人的改动都会被考虑进来.
    

## 创建管理远程分支

> 查看本地分支： git branch

> 创建本地分支： git checkout -b develop

> 将新建的本地分支push到远程服务器，远程分支与本地分支同名： git push origin develop:develop

> 删除远程分支： git push origin --delete develop