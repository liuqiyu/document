```
# 数组
```


    创建数组的基本方式有两种。第一种是使用Array构造函数：

    `var coloe = new Array();`

    > 如果预先知道数组的长度，可以创建一个已知长度的数组： `var length = new Array(10);`

    > 也可以向Array构造函数传递数组中包含的项： `var colors = new Array('red', 'blue', 'green');`

    创建数组的第二种基本方式是使用数组字面量表示法： `var colors = ['red', 'blue', 'green'];`

    #### 检查数组

    ```js
    var arr = [1, 2, 3];
    // 1
    arr instranceof Array  ==> true

    // 2
    arr.isArray(value)  ==> true
    ```
    <hr/>
    ##### 1、join()
    分割数组为字符串

    ```js
    var arr = [1, 2, 3, 4];
    console.log(arr.join('-')); // 1-2-3-4
    ```
    **注：原数组不变**
    <hr/>
    ##### 2、push()和pop()

    * push(): 接受任意数量参数，将他们添加到数组末尾，返回修改后的数组长度

    ```js
    var arr = [1, 2, 3, 4];
    var len = arr.push(5); ==> 5
    console.log(arr); ==> [1, 2, 3, 4, 5];
    ```

    * pop(): 移除数组末尾最后一项，返回移除的项

    ```js
    var arr = [1, 2, 3, 4, 5];
    var b = arr.pop(); ==> 5
    console.log(arr); ==> [1, 2, 3, 4];
    ```

    **注：原数组改变**
    <hr/>
    ##### 3、shift()和unshift()

    * unshift(): 接受任意数量的参数，将他们添加到数组开头，返回数组的长度

    ```js
    var arr = [1, 2, 3, 4];
    var len = arr.unshift(0); ==> 5
    console.log(arr); ==> [0, 1, 2, 3, 4]
    ```

    * shift(): 移除数组开头的一项，返回移除的项

    ```js
    var arr = [1, 2 , 3, 4];
    var b = arr.shift();  ==> 1
    console.log(arr); ==> [2, 3, 4]
    ```

    **注： 原数组改变**
    <hr/>

    ##### 4、sort()和reverse()

    * sort(): 数组升序排序。排序时，sort()方法调用每个数组项的toString()的转型方法，然后对得到的字符串进行排序。所以会出现以下情况：

    ```js
    var a = [1, 5, 10, 15];
    console.log(a.sort()); ==> [1, 10, 15, 5]  ==> 错误排序
    ```
    正确排序
    ```js
    var arr = [1, 5, 10, 15];

    arr.sort(function(value1, value2) {
      if (value1 < value2) {
        return -1;
      } else if (value1 > value2) {
        return 1;
      } else {
        return 0;
      }
    });
    ```
    **注： 原数组改变**

    * reverse(): 反转数组的排序

    ```js
    var arr = [1, 2, 3, 4];
    console.log(arr.reverse()); ==> [4, 3, 2, 1]
    ```
    **注： 原数组改变**
    <hr/>

    ##### 5、concat()和...

    * concat(): 将参数添加到原数组中

    ```js
    var a = [1, 2, 3];
    var b = [4, 5, 6];
    console.log(a.concat(b)); ==> [1, 2, 3, 4, 5, 6]
    ```

    **注：原数组不变**

    * ...

    ```js
    var a = [1, 2, 3];
    var b = [4, 5, 6];
    console.log(...a, ...b); ==> [1, 2, 3, 4, 5, 6]
    ```

    **注：原数组不变**
    <hr/>

    ##### 6、slice()

    ** arr.slice(index1, index2)**

    返回原数组指定开始下标到结束下标组成的新数组。

    ```js
    var arr = [1, 2, 3, 4];
    var b = arr.slice(2);
    console.log(b); ==> [3, 4]
    console.log(arr); ==> [1, 2, 3, 4]
    ```

    **注：原数组不变**
    <hr/>

    ##### 7、splice()

    **arr.splice(index, howmary, item1, ...., itemx)**

    * index: 必须。整数。添加/删除项目的位置，使用负数可从数组结尾处规定位置
    * howmary: 必须。要删除的项目数量。如果是0，则不会删除项目
    * item, ..., itemx: 可选，香数组添加新项目

    ```js
    var arr = [1, 2, 3, 4, 5, 6];

    // 数组0的位置开始，移除两个参数，返回移除的参数
    var newArr1 = arr.splice(0, 2);
    console.log(newArr1); ==> [1, 2]
    console.log(arr); ==> [3, 4, 5, 6]

    // 数组2的位置开始，增加参数11, 12
    var newArr2 = arr.splice(2, 0, 11, 12);
    console.log(newArr2); ==> []
    console.log(arr); ==> [3, 4, 11, 12, 5, 6]

    // 移除数组1额参数，添加入2, 22
    var newArr3 = arr.splice(1, 1, 21, 22);
    console.log(newArr3); ==> [4]
    console.log(arr); ==> [3, 21, 22, 11, 12, 5, 6]
    ```

    **注： 原数组改变**





