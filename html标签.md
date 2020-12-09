# html

> hyperText markup language 超文本标记语言

空格（回车）在编辑器里被称为文本分隔符。不管在编辑器里写多少个空格，在网页里只显示一个。

在一个宽度很小的 div 里边写了一堆字母，会发现字母会超出 div 边界显示，而不换行，写入中文却可以自动换行，是因为系统认为写的字母是一个单词，所以就不会换行，必须加上空格才可以，空格就是英文单词分隔符。

### html实体

\&nbsp;空格文本

\&lt;/\&gt;左/右尖角号



### 元素的分类

常见的行级元素（内联元素、inline）：**span、strong、em、a、del** 等，

特点：内容决定元素所占位置，不独占一行，不可以通过 css 改宽高。宽=内部元素的宽，高＝内部元素的高。



常见的块级元素（block）：**div、p、ul、li、ol、form、address** 等，

特点：独占一行；可以通过 css 改宽高。在没有设置宽高时，宽=100%，高＝内部元素的高。



行级块元素（inline-block）：**img** 等，

特点：内容决定大小，不独占一行，可以改宽高。在没有设置宽高时，宽=内部元素的宽，高＝内部元素的高。

注：图片只设置宽，高会等比缩放，只设置高，宽会等比缩放。



### 标签

#### 常用

##### ul

```html
<ul type="disc">
	<li></li>
	<li></li>
</ul>
```

无序列表标签，默认前边为小黑点，即属性为 `type=“disc`，小方块为 `type="square”`，小圆圈 `type=“circle”`

##### a

超链接

```html
<a href="" target="_self"></a>
```

`href` 属性里边放网址，

`target=“_self”` 在当前窗口打开，还有一个 `_blank` 作用是在新的标签页打开。

**a 标签里不能嵌套a标签**



锚点

```html
<div id=“div1”></div>
<div id=“div2”></div>

<a href=“#demo1”>jump div1</a>
<a href=“#demo2”>jump div2</a>
```

当两个 div 在一个页面中时，a 标签可以起到一个目录的作用，点击 a 标签，跳转到对应的位置。



协议限定符

```html
<a href="javascript:while(1){alert('让你手欠!')}">点我</a>
```

运行js代码



#### 不常用

##### ol

```html
<ol type="1">
	<li></li>
	<li></li>
</ol>
```
有序列表标签，默认以阿拉伯数字排序，即 `type="1"` ，除此之外值还可以是 `a/A/i/I` 

`start="2"` 属性定义开始的序号 

`reversed="reversed"` 属性倒过来排











































