# Promise

    
   *  三种状态： `pending` 进行中  `fulfilled` 已成功  `rejected` 已失败。Promise对象会出现两种状态的改变。 `pending` 进行中 => `fulfilled` 已成功 、`pending` 进行中 => `rejected` 已失败。
   
   *  `Promise.prototype.then()` 方法可接受两个回调函数作为参数
   
           
           promiose.then(resolveCallback, rejectCallback)；
           
           ## 实例
    
           const promise = new Promise((resolve, reject) => {
                // ... some code
                
                if (/*** 异步操作的判断 ***/) {
                    resolve('成功');
                } else {
                    reject('失败');
                }
           });
           
           promise.then((value) => {
               // success
               // resolve 返回的数据
               // value => 成功
           }, (error) => {
               // failure
               // reject 返回的数据
               // error => 失败
           });
   
   *  `Promise.prototype.catch();`方法是.then(null, rejection)的别名【第二个参数】。指定错误的回调函数。
        
        ```
        
        .then((value) => {
            // success
        }).catch((error) => {
            // error
        })
        
        ```
        
   *  `Promise.prototype.finally();`不管是成功还是错误，都是执行这个操作。
    
        ```
        
        .finally(() => {
            // 执行完请求的操作
            // 该操作无关请求成功与否
        })
        
        
   * `Promise.all();`将多个Promise实例，包装成为一个新的promise实例。
    
        ```
        const promise = Promise.all(p1, p2, p3);
        // p1, p2, p3 都是Promise实例
        // 只有p1, p2, p3的状态都为fulfilled时, promise的状态才会变成fulfilled。promise的返回值时p1, p2, p3返回值组成的数组。
        
        const p1 = new Promise((resolve, reject) => {
          resolve('成功p1')
          reject('失败p1')
        })
    
        const p2 = new Promise((resolve, reject) => {
          resolve('成功p2')
          reject('失败p2')
        })
    
        Promise.all([p1, p2]).then((value) => {
          console.log(value)
        }, (error) => {
          console.log(error)
        })
        
        // ['成功1', '成功2'];
        
   
   *  使用说明 == 仿 axios
   
        ```
        const axios = {
          get (path) {
            return new Promise((resolve, reject) => {
              if (value >1) {
                resolve('成功')
              } else {
                reject('失败')
              }
            })
          }
        }
        
        axios.get(1).then((value) => {
          console.log(value)
        }, (error) => {
          console.log(error)
        })
        ```
       