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

add(1);   
add(1);   
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