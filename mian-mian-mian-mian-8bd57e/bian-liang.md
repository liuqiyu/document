# <center> 变量

### Javascript变量分为两种类型

* 基本类型： Undefined、Null、Boolean、Number 和 String
    * 基本类型值在内存中占据固定大小的空间，因此被保存在`栈内存`中；
    * 从一个变量向另一个变量复制基本类型的值，会创建这个值的一个副本；
* 引用类型： Object
    * 引用类型的值是对象，保存在`堆内存`中；
    * 包含引用类型值的变量实际上包含的并不是对象本身，而是一个指向该对象的** 指针 **；
    * 从一个变量向另一个变量复制引用类型的值，复制的其实是指针，因此两个变量最终都指向同一个对象； 
    
#### 1、复制

* 基本类型： 两个完成独立的变量
    ```
    var num1 = 5;
    var num2 = num1;
    ```

* 引用类型： 复制一个指针，指向储存在堆里面的对象

    ```
    var obj1 = {a: 1};
    var obj2 = obj1;
    
    obj1 = {a: 2}; // {a: 2} 是另外一个堆内存。所以改变了obj1的指针。
    obj2 // => {a: 1}
    obj1 // => {a: 2}
    
    obj1.a = 2;   // 直接改变指向内存里面的a的值
    obj2 // => {a: 2}
    obj1 // => {a: 2}
    ```
 
#### 2、传递参数

`function student(name, obj){};`所有参数都是按值传递的。把函数外部的值复制给函数内部的参
数，就和把值从一个变量复制到另一个变量一样

* 基本类型：复制给函数的局部变量 => arguments
    * 修改arguments不会影响外部传递的对象

* 引用类型：对象内存的地址复制给局部变量 => arguments
    * 修改arguments会影响外部的对象，因为他是根据指针地址去修改堆里面的值
    
#### 3、检查类型

* 确定一个值是哪种基本类型可以使用 typeof 操作符，而确定一个值是哪种引用类型可以使用instanceof 操作符。
* 当使用typeof 去检查一个为`null`的变量时，会返回`Object`. 检查函数： 会返回`function`
* `instanceof`只能检查引用类型，对基本类型无效。返回`false`，因为不是对象。

#### 4、执行环境和作用域

* 执行环境
    * 全局执行环境：关闭网页或者浏览器时销毁
    * 局部执行环境：当执行流进入一个函数时，函数的环境就会被推入一个环境栈中。
而在函数执行之后，栈将其环境弹出，把控制权返回给之前的执行环境

* 作用域链
    * 每次进入一个新执行环境，都会创建一个用于搜索变量和函数的作用域链
    * 函数的局部环境不仅有权访问函数作用域中的变量，而且有权访问其包含（父）环境，乃至全局环境；
    * 用途： 是保证对执行环境有权访问的所有变量和函数的有序访问
    * 一个函数的作用域链： 函数内部变量+arguments+函数外部全局变量。可以在函数内部访问外部变量，是因为在作用域链中找到了。
    * 变量的执行环境有助于确定应该何时释放内存。
    
#### 5、没有块级作用域

#### 6、垃圾收集

JavaScript 是一门具有自动垃圾收集机制的编程语言，开发人员不必关心内存分配和回收问题

* 离开作用域的值将被自动标记为可以回收，因此将在垃圾收集期间被删除。
* `标记清除`是目前主流的垃圾收集算法，这种算法的思想是给当前不使用的值加上标记，然后再回收其内存。
    * 垃圾回收器，在运行的时候会给存储在内存中的所有变量都加上标记
    * 去掉环境中的变量以及被环境中的变量引用的变量的标记
    * 再被加上标记的会被视为准备删除的变量
    * 垃圾回收器完成内存清除工作，销毁那些带标记的值并回收他们所占用的内存空间
* 另一种垃圾收集算法是“引用计数”

#### 7、内存泄露

虽然Javascript有垃圾回收机制，但是当我们编写代码不当时，也会造成内存泄露。

* 意外的全局变量导致内存泄露
    * 原因： 厍变量，不会被回收
    * 解决： 会用严格模式避免
* 闭包引起内存泄露
    * 原因： 闭包可以维持函数内部的变量，使其不能被释放
    * 解决： 将事件处理函数定义在外部，解除闭包,或者在定义事件处理函数的外部函数中，删除对dom的引用
* 未清理DOM元素的引用
    * 原因： 对象中存在dom引用
    * 解决： 手动
* 被遗忘的定时器或者回调
    * 定时器中有dom的引用，即使dom删除了，但是定时器还在，所以内存中还是有这个dom。
    * 手动删除定时器和dom。
* 子元素存在引用引起的内存泄漏
    * 原因：div中的ul li  得到这个div，会间接引用某个得到的li，那么此时因为div间接引用li，即使li被清空，也还是在内存中，并且只要li不被删除，他的父元素都不会被删除。
    * 解决：手动删除清空。

    
   
   
   
   
   
    
    