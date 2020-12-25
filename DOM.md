# DOM



区分标准模式和怪异模式

> document.compatMode

CSS1Compat：标准模式

BackCompat：怪异模式



##### offsetWidth

`HTMLElement.offsetWidth` 是一个只读属性，返回一个元素的布局宽度。属性值将会 round(四舍五入)为一个整数。

测量包含元素的边框(border)、水平线上的内边距(padding)、竖直方向滚动条(scrollbar)（如果存在的话）、以及CSS设置的宽度(width)的值。

[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/offsetWidth)

![](https://developer.mozilla.org/@api/deki/files/186/=Dimensions-offset.png)



##### clientWidth

`Element.clientWidth` 属性表示元素的内部宽度，以像素计。属性值会被四舍五入为一个整数。

该属性包括内边距 padding，但不包括边框 border、外边距 margin 和垂直滚动条（如果有的话）。

[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/clientWidth)

![](https://developer.mozilla.org/@api/deki/files/185/=Dimensions-client.png)



```js
网页正文全文高： document.body.scrollHeight; 
网页正文全文高： document.body.clientHeight;
网页正文全文高： document.body.offsetWidth;  // 包含border

屏幕分辨率的高： window.screen.height;
屏幕可用工作区高度： window.screen.availHeight;  // 不包含任务栏

视口的高： document.documentElement.clientHeight
视口的高： window.innerHeight // 包含横向滚动条

```





##### offsetLeft			offsetTop

`HTMLElement.offsetTop` 为只读属性，它返回当前元素相对于其 [`offsetParent`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/offsetParent) 元素的顶部内边距的距离。















