# 函数参数解构

例子：React

```js
 <PrivateRoute path="/protected" component={Protected} />
 
 const PrivateRoute = ({ component: Component, ...rest }) => (
  <Route
    {...rest}
    render={props =>
      fakeAuth.isAuthenticated ? (
        <Component {...props} />
      ) : (
        <Redirect
          to={{
            pathname: "/login",
            state: { from: props.location }
          }}
        />
      )
    }
  />
);
```

由上面代码发现：PrivateRoute 函数的`({ component: Component, ...rest })`是一个不常见的写法，如何解释他呢。

我们console.log(({ component: Component, ...rest }));

```JS
{
component
:
ƒ Protected()
path
:
"/protected"
}
```