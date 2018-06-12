# 版本回退

</hr>
#### 完全回退

* 查看所有的版本
    * git log
    
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
    * git log --pretty=oneline
    
    ```
    cd8da402c018e7a70aa81585664c657415cb65b7 'aa'
    2bdb3e539b35f2bcd00edc7cede12f14440ab936 'aa'
    3414ee387213d0f57b823335c926047561429a79 'addIndex2'

    ```
    
    ```
    
    ```