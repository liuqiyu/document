# 怎么画一条0.5px的边
什么是像素？像素是屏幕显示最小的单位，在一个1080p的屏幕上，它的像素数量是1920 * 1080，即横边有1920个像素，而竖边为1080个。一个像素就是一个单位色块，是由rgba四个通道混合而成。对于一个1200万像素的相机镜头来说，它有1200万个感光单元，它能输出的最大图片分辨率大约为3000 * 4000。那么像素本身有大小吗，一个像素有多大？有的，如果一个像素越小，那么在同样大小的屏幕上，需要的像素点就越多，像素就越密集，如果一英寸有435个像素，那么它的dpi/ppi就达到了435。Macbook Pro 15寸的分辨率为2880 x 1800，15寸是指屏幕的对角线为15寸（具体为15.4），根据长宽比换算一下得到横边为13寸，所以ppi为2880 / 13 = 220 ppi. 像素越密集即ppi(pixel per inch)越高，那么屏幕看起来就越细腻越高清。在Mac/Windows上可以设置屏幕显示的分辨率，Mac默认为设备分辨率的一半，它的dpr = 2，即长和宽用2个像素表示1个像素，所以2880个物理像素点实际上只表示1440个逻辑像素：那么我们的问题来了，怎么在高清屏上画一条0.5px的边呢？0.5px相当于高清屏物理像素的1px。这样的目的是在高清屏上看起来会更细一点，效果会更好一点，例如更细的分隔线。大漠在《再谈Retina下1px的解决方案》已经讨论过这个问题，这里我们再理一理思路。理论上px的最小单位是1，但是会有几个特例，高清屏的显示就是一个特例。高清屏确实可以画0.5px，对比效果如下：如果我们直接设置0.5px，在不同的浏览器会有不同的表现，使用如下代码：
```
<!DOCType html>
<html>
<head>
    <meta charset="utf-8">
    <style>
        .hr {
            width: 300px;
            background-color: #000;
        }
        .hr.half-px {
            height: 0.5px;
        }
        .hr.one-px {
           height: 1px;
        }
    </style>
</head>
<body>
    <p>0.5px</p>
    <div class="hr half-px"></div>
    <p>1px</p>
    <div class="hr one-px"></div>
</body>
</html>

```
在PC上的不同浏览器上测试测试结果如下所示：其中Chrome把0.5px四舍五入变成了1px，而firefox/safari能够画出半个像素的边，并且Chrome会把小于0.5px的当成0，而Firefox会把不小于0.55px当成1px，Safari是把不小于0.75px当成1px，进一步在手机上观察IOS的Chrome会画出0.5px的边，而安卓(5.0)原生浏览器是不行的。所以直接设置0.5px不同浏览器的差异比较大，并且我们看到不同系统的不同浏览器对小数点的px有不同的处理。所以如果我们把单位设置成小数的px包括宽高等，其实不太可靠，因为不同浏览器表现不一样。第二种能想到的方法是缩放，能否设置1px，然后scale 0.5呢，我们可以尝试一下，如下代码所示：
```
<style>
.hr.scale-half {
    height: 1px;
    transform: scaleY(0.5);
}
</style>
<p>1px + scaleY(0.5)</p>
<div class="hr scale-half"></div>
```
效果如下图所示：我们发现Chrome/Safari都变虚了，只有Firefox比较完美看起来是实的而且还很细，效果和直接设置0.5px一样。所以通过transform: scale会导致Chrome变虚了，而粗细几乎没有变化，所以这个效果不好。我们还想到做移动端的时候还使用了rem做缩放，但实际上rem的缩放最后还是会转化成px，所以和直接使用0.5px的方案是一样的。还有什么办法呢？还可以用线性渐变linear-gradient，如下代码所示：<style>
.hr.gradient {
    height: 1px;
    background: linear-gradient(0deg, #fff, #000);
}
</style>
<p>linear-gradient(0deg, #fff, #000)</p>
<div class="hr gradient"></div>
linear-gradient(0deg, #fff, #000)的意思是：渐变的角度从下往上，从白色#fff渐变到黑色#000，而且是线性的，在高清屏上，1px的逻辑像素代表的物理（设备）像素有2px，由于是线性渐变，所以第1个px只能是#fff，而剩下的那个像素只能是#000，这样就达到了画一半的目的。逻辑分析很完美，实际的效果又怎么样呢，如下图所示：我们发现这种方法在各个流览器上面都不完美，效果都是虚的，和完美的0.5px还是有差距。这个效果和scale 0.5的差不多，都是通过虚化线，让人觉得变细了。还有另外一种方法，使用boxshadow，如下代码所示：
```
<style>
.hr.boxshadow {
    height: 1px;
    background: none;
    box-shadow: 0 0.5px 0 #000;
}
</style>
<p>box-shadow: 0 0.5px 0 #000</p>
<div class="hr boxshadow"></div>
```
设置box-shadow的第二个参数为0.5px，表示阴影垂直方向的偏移为0.5px，效果如下：这个方法在Chrome和Firefox都非常完美，但是Safari不支持小于1px的boxshadow，所以完全没显示出来了。不过至少找到了一种方法能够让PC的Chrome显示0.5px。还可以使用SVG，利用SVG的1px还是物理像素的1px，不是高清屏的1px。如下代码所示：
```
<style>
.hr.svg {
    background: none;
    height: 1px;
    background: url("data:image/svg+xml;utf-8,<svg xmlns='http://www.w3.org/2000/svg' width='100%' height='1px'><line x1='0' y1='0' x2='100%' y2='0' stroke='#000'></line></svg>");
}
</style>
<p>svg</p>
<div class="hr svg"></div>

```
设置background为一个svg文件，这个svg单独拷出来是这样的：
```
<svg xmlns='http://www.w3.org/2000/svg' width='100%' height='1px'>
    <line x1='0' y1='0' x2='100%' y2='0' stroke='#000'></line>
</svg>

```
使用svg的line元素画线，stroke表示描边颜色，默认的宽度stroke-width="1"，由于svg的1px是物理像素的px，相当于高清屏的0.5px，另外还可以使用svg的rect等元素进行绘制。在Chrome和Safari的效果如下：这个方案也是很完美，但是在firefox挂了，究其原因是因为firefox的background-image如果是svg的话只支持命名的颜色，如"black"、"red"等，如果把上面代码的svg里面的#000改成black的话就可以显示出来，但是这样就很不灵活了。否则只能把svg转成base64的形式，我们把svg的内容转成base64（可以找一些在线的工具），对比如下：
```
.hr.svg {
    background: url("data:image/svg+xml;utf-8,<svg xmlns='http://www.w3.org/2000/svg' width='100%' height='1px'><line x1='0' y1='0' x2='100%' y2='0' stroke='#000'></line></svg>");
    background: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHdpZHRoPScxMDAlJyBoZWlnaHQ9JzFweCc+PGxpbmUgeDE9JzAnIHkxPScwJyB4Mj0nMTAwJScgeTI9JzAnIHN0cm9rZT0nIzAwMCc+PC9saW5lPjwvc3ZnPg==");
}
```
这样在firefox也能完美展示了。其实0.5px的需求在移动端应该会更常见，比较一下以上五种方法在IOS和安卓的表现，如下图所示：IOS下的Safari和Chrome表现一致，都是以直接设置0.5px的效果最好，而安卓浏览器则是以box-shadow的效果最好（试了5和7），而svg的方案在IOS和安卓的设备上都能完美支持。读者可以打开这个网页，看一下在你的设备是哪种效果最好。结合以上，我们初步得到以下结论：使用SVG相对于box-shadow等方法，还有一个好处是可以借助svg的元素画出任意图形，如四边形，圆角等。最后还有一个万能的方法，那就是通过控制viewport，在移端开发里面一般会把viewport的scale设置成1：`<meta name="viewport" content="width=device-width,initial-sacle=1">`
其中width=device-width表示将viewport视窗的宽度调整为设备的宽度，这个宽度通常是指物理上宽度。默认的缩放比例为1，如iphone 6竖屏的宽度为750px，它的dpr=2，用2px表示1px，这样设置之后viewport的宽度就变成375px。这时候0.5px的边就使用我们上面讨论的方法。但是你可以把scale改成0.5：`<meta name="viewport" content="width=device-width,initial-sacle=0.5">`
这样的话，viewport的宽度就是原本的750px，所以1个px还是1px，正常画就行，但这样也意味着UI需要按2倍图的出，整体面面的单位都会放大一倍。在iPone X和一些安卓手机等dpr = 3的设备上，需要设置scale为0.333333，这个时候就是3倍地画了。综上讨论了像素和viewport的一些概念，并介绍和比较了在高清屏上画0.5px的几种方法——可以通过直接设置宽高border为0.5px、设置box-shadow的垂直方向的偏移量为0.5px、借助线性渐变linear-gradient、使用transform: scaleY(0.5)的方法，使用SVG的方法。最后发现SVG的方法兼容性和效果都是最好的，所以在viewport是1的情况下，可以使用SVG画0.5px，而如果viewport的缩放比例不是1的话，那么直接画1px即可。