# 使用import和export

### 前言

在es6前，前端就使用RequireJS或者seaJS实现模块化，requireJS是基于AMD规范的模块化库，  而像seaJS是基于CMD规范的模块化库；

现在es6自带模块化，也是JS第一次支持module。现在我们可以直接使用export和import在浏览器中导入和导出各个模块，`一个js文件代表一个js模块`；

因为现代浏览器对es6的支持程度不同，所以需要使用babelJS对es6代码进行编译转码成es5代码;

 
#### export

```javascript
// export.js
export const str = 'STR';

export const func = () => {};

import {str, func} from './export';

```

#### export default

```javascript
// export.js
const str = 'STR';

const func = () => {};

export default {
    str,
    func
}

import export from './export'
// export.str  // 'STR'
// export.func
```

