# dom绑定与解绑

### click的绑定与解绑

```js
<input id="btn" type="button" />

var btn = document.getElementById('btn');

// 绑定1
btn.onclick = action ();

// 绑定2
btn.addEventListener('click', action);

// 解绑1
btn.onclick = null;

// 解绑2
btn.removeEventListener('click', action);

function action () {
    alert(123);
}
```

