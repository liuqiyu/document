# class 详解

在es6诞生之前，javascript没有类，只有对象。实现类则需要先定义一个对象，定义构造函数，然后通过new的方式完成。


### 基本实现方式

> old code

```js
function studentInfo (name, age) {
  this.name = name
  this.age = age
}

studentInfo.prototype.say = function () {
  alert('I am a student')
}

var bob = new studentInfo('bob', 18)
bob.name  // 'bob'
bob.age   // 18
bob.say() // 'I am student'
```

> new es6 code

```js
class studentInfo {
  constructor (name, age) {
    this.name = name
    this.age = age
  }
  
  say () {
    alert('I am a student')
  }
}

const may = new studentInfo('may', 18)
may.name   // 'may'
may.age    // 18
may.say    // 'I am student'
```


### 继承

> 直接上干活

> 当子类需要定义构造参数时，需要在子类的`constructor`中写入`super()`，不然会报错。

> 子类有方法与父类同名，子类会覆盖父类的方法。

```js
class People {
  constructor (name, age) {
    this.name = name
    this.age = age
  }
  
  say () {
    alert('I am a people')
  }
}

class Student extends People {
  
  constructor (name, age, gender) {
    //不调super()，则会报错  this is not defined
    //必须调用super
    super(name, age)
    this.gender = gender
  }
  
  say () {
    alert('I am a student')
   }
    
  says () {
    alert('I am a student')
  }
}

const bob = new Student('bob', 18, '男')

bob.name    // 'bob'
bob.age     // 18'
bob.gender  // '男'

bob.say()   // 'I am a student' 直接覆盖父类的输出
bob.says()   // 'I am a student'
```
