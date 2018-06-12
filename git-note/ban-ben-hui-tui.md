# 版本回退

#### 1、查看所有的版本

> git log

```
commit cd8da402c018e7a70aa81585664c657415cb65b7
Author: lqy <1064839051@qq.com>
Date:   Tue Jun 12 16:34:35 2018 +0800

    'aa'

commit 2bdb3e539b35f2bcd00edc7cede12f14440ab936
Merge: 7adee8d 3414ee3
Author: lqy <1064839051@qq.com>
Date:   Tue Jun 12 16:29:40 2018 +0800

    'aa'

commit 3414ee387213d0f57b823335c926047561429a79
Author: lqy <1064839051@qq.com>
Date:   Tue Jun 12 16:12:40 2018 +0800
```
> git log --pretty=oneline
```
cd8da402c018e7a70aa81585664c657415cb65b7 'aa'
2bdb3e539b35f2bcd00edc7cede12f14440ab936 'aa'
3414ee387213d0f57b823335c926047561429a79 'addIndex2'
```

### 2、回退到指定的版本

> git reset --hard 3414ee387213d0f57b823335c926047561429a79

```
HEAD is now at cd8da40 'addIndex2'
```

### 3、回退到某个版本后，如果想要还原，要怎么办？

> git reflog

```
cd8da40 HEAD@{0}: reset: moving to cd8da402c018e7a70aa81585664c657415cb65b7
561285f HEAD@{1}: commit: '安安'
cd8da40 HEAD@{2}: commit: 'aa'
2bdb3e5 HEAD@{3}: commit (merge): 'aa'
7adee8d HEAD@{4}: checkout: moving from lqy to master
```

> 还原版本

`git reset --hard commit_id` `git reset --hard 561285f` `HEAD is now at 561285f '安安'`
