#async&await

### 初识Async/await

Async/await是javascript编写异步的新方法。以往的异步无外乎回调函数和Promise。但是async&await建立在Promise之上。

> 1、async 函数执行后，总是返回了一个 promise 对象
> 2、await 所在的那一行语句是同步的


### 实例

> 配合Promise实现异步

```javascript
const stop = (time) => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            console.log(2)
            resolve('成功')
        },time)
    })
}

const start = async () => {
    console.log('start');
    
    const res = await stop(3000)   // 返回 '成功'
    
    console.log(res)
    
    console.log('stop')  // 需要等待上面stop函数执行完成再输出
}

start()

// 上面代码一次输出如下。
// 'start'
// 2
// '成功'
// 'stop'
```