# 模块化


一、情景一

* func.js

```js
function add(num) {
    return num += 1;
}

function del(num) {
    return num -= 1;
}

module.exports = {
    add,
    del,
}
```

* app.js

```js
var { add, del }= require('./func');

add(1); // 1 
del(1); // 0   
```

</hr>

* func.js

```js
exports.add = function (num) {
    return num += 1;
};

exports.delete = function (num) {
    return num -= 1;
};
```

* app.js

```js
var func = require('./func');

func.add(1); // 2
func.del(1); // 0
```