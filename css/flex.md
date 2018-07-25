# flex布局

![](/assets/5a7d00514af1e464221c677c15e8e990.png)

### 基本概念

![](/assets/3791e575c48b3698be6a94ae1dbff79d.png)

### 容器属性

* [flex-direction](#flex-direction)
* [flex-wrap](#flex-wrap)
* [flex-flow](#flex-flow)
* [justify-content](#justify-content)
* [align-items](#align-items)
* [align-content](#align-content)

<a name="flex-direction"></a>
#### 1、flex-direction (方向)

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
#### 2、flex-wrap

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

<a name="flex-flow"></a>
### 3、flex-flow
`flex-flow`其实是`flex-direction`和`flex-wrap`的简写方式， `flex-flow: row wrap`

```css
.box {
  flex-flow: <flex-direction> || <flex-wrap>;
}
```

<a name="justify-content"></a>
### 4、justify-content
定义了项目在主轴上的对其方式（X轴）

```css
.box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
```

* flex-start（默认值）： 左对齐

![](/assets/企业微信截图_15324875459222.png)

* flex-end： 右对齐

![](/assets/企业微信截图_15324875564780.png)

* center: 居中

![](/assets/企业微信截图_15324875689034.png)

* space-between: 两端对齐， 项目之间间隔都相等

![](/assets/企业微信截图_15324875894963.png)

* space-around: 每个两侧间隔相等，项目之间的间隔比项目与边框的间隔大一倍

![](/assets/企业微信截图_15324875992670.png)

<a name="align-items"></a>
### 5、align-items

`align-items`属性定义项目在交叉轴上如何对齐。(Y轴)

```css
.box {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```

* flex-start： 上起点

![](/assets/企业微信截图_15324881253598.png)

* flex-end: 下起点

![](/assets/企业微信截图_15324881351029.png)

* center: 中点

![](/assets/企业微信截图_15324881461602.png)

* baseline： 项目的第一行文字的基线对齐
* stretch（默认值）： 如果项目未设置高度或设为auto，将占满整个容器的高度

<a name="align-content"></a>
### 6、align-items


### 兼容性

![](/assets/8712d713c7d0b884a5cb9770efc422b4.jpg)


