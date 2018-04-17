# dom绑定与解绑

### click的绑定与解绑

```js
<input id="btn" type="button" />

var btn = document.getElementById('btn');

// 绑定1
btn.onclick = action ();

function action () {
    alert(123);
}
```

