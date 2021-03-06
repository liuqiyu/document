# GIT

### 版本库

* 工作区

  实际的工作目录。

* 版本库

  工作区有一个隐藏的目录`.git`,是一个版本库。
  
  `stage`是暂存区，`master`是默认创建的第一个分支，`HEAD`是指向`master`的指针。

  ![](/assets/0.jpg)
  
  我们将文件往`git`版本库添加的时候，分两步执行：
  
  第一步是用`git add .`把文件添加进去，将文件的修改放入暂存区
  第二步是用`git commit`提交更改，将暂存区的所有内容提交到当前的分支
  
  实践出真理，我们可以看看工作原理:
  
  ```
  git status
  
  On branch master![](/assets/1.jpg)
  Your branch is up-to-date with 'origin/master'.
  Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   bb.txt

  Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   aa.txt
        modified:   bb.txt

  ```


  上面的提示告诉我们，`bb.txt`文件未被提交，`aa.txt`文件有更改未被commit。
  
  先执行`git add .`，查看版本库的情况
  
  ![](/assets/1.jpg)
  
  在执行`git commit -m 'update'`，查看版本库的情况
  
  ![](/assets/2.jpg)
  
  <hr/>
  
  
  
  