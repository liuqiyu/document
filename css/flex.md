# flex布局

![](/assets/5a7d00514af1e464221c677c15e8e990.png)

### 基本概念

![](/assets/3791e575c48b3698be6a94ae1dbff79d.png)

### 容器属性

* [flex-direction](flex-direction)
* [flex-wrap](flex-wrap)
* [flex-flow](flex-flow)
* [justify-content](justify-content)
* [align-items](align-items)
* [align-content](align-content)

<a name="flex-direction"></a>
#### flex-direction (方向)

```css
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
* row: 主轴为水平方向，起点在左端
![](/assets/企业微信截图_15324859183170.png)

* row-reverse:  主轴在水平方向， 起点在右端
![](/assets/企业微信截图_15324859699106.png)

* column: 主轴在垂直方向， 起点在上端
![](/assets/企业微信截图_15324860154034.png)

* column-reverse: 主轴在垂直方向， 起点在下端
![](/assets/企业微信截图_15324860251421.png)

<a name="flex-wrap"></a>
#### flex-wrap

如果一条轴线排不下，如何换行

```css
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

* nowrap（默认）: 不换行， 会挤压`item`宽度
![](/assets/企业微信截图_1532486704653.png)

* wrap： 换行， 第一行在上面
![](/assets/企业微信截图_15324867271595.png)

* wrap-reverse： 换行，第一行在下面
![](/assets/企业微信截图_15324868257680.png)

<a name="flex-flow

"></a>
### flex-flow

### 兼容性

![](/assets/8712d713c7d0b884a5cb9770efc422b4.jpg)


