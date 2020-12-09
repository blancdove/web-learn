# CSS选择器

id选择器

标签选择器

属性选择器



### css权重

!important（Infinity）

行间样式（1000）

id（100）

class/属性/伪类（10）

标签/伪元素（1）

通配符（0）

注：

权重相同时，书写靠后的代码覆盖书写靠前的代码。

!important 写在 css 代码后，最好不要用。不利于代码维护

这里的值是 256 进制



### css属性

opacity

透明度，取值0~1



text-align

文字对齐方式，默认 left（左对齐），还有 right（右对齐），center（居中对齐）



line-height

单行文本所占高度，就是单行文字高度+间距高度，如果单行文本所占高度 = 文字高度，则没有行间距，要想单行文本垂直居中，则需要让单行文本所占高度 = 外部盒子高度(必须是单行才可以)。



text-indent

首行缩进 2 个 em（空两格），1em=1font-size（em 为相对单位）



text-decoration

文字样式：line-through 中划线；还有一些值，none（无），underline（下划线），overline（上划线）



#### 文字特性

凡是带有 inline 的元素（文本类属性元素），都有**文字特性**。

利用4个 img 标签引入4张图片，发现中间有一条缝，因为浏览器会把回车当成文本分隔符，解决这个问题的方法可以是写代码的时候两个 img 中间不要加空格也不要按回车，紧挨着即可。



#### 盒模型

**margin+border+padding+（content=width+height）**

外边距：margin（容器与容器之间的距离）

盒子边框：border

内边距：padding（容器与内部内容之间的距离, 内边距是不能放内容的,并且会把盒子撑开）

盒子内容：width+height



#### 层模型（定位）

绝对定位：position：absolute;

脱离文档流，通过设置top、left、right、bottom来相对于最近的有定位的父级进行定位，如果没有，那么相对于文档进行定位。



相对定位：position：relative;

不脱离文档流（占着原来的位置），通过设置top、left、right、bottom来相对于原来的位置进行定位。



固定定位：position：fixed;

不随着滚动条的拖曳而改变，始终在屏幕上的那个位置；



z-index

只对设置了position的元素有效，即其 `position` 属性值不是 `static`，提高层级，值越大越在上层。



**绝对定位**和**固定定位**可以用来实现居中效果：

```css
div{
    width: 100px;
	height: 100px;
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: -50px;
	margin-top: -50px;
}
```











### 练习

##### 1. 写一个直角三角形

html代码

```css
<div></div>
```

css代码

```css
div{
    width: 0;
    height: 0;
    border: 50px solid transparent;
    border-bottom-color: #000;
    border-left-color: #000;
}
```

##### 2. 求出下列盒子的可视化宽高

```css
div {
    width: 100px;
    height: 100px;
    background-color: red;
    border: 10px solid black;
    padding: 10px 20px 30px;
    margin: 10px 20px;
}
```

宽 160px，高 160px

可视化宽高不包括 margin 值，宽等于 widtn 的 100+border 的左右各 10+padding 的左右各 20，高等于 height 的 100+border 的上下各 10+padding 的上 10 和下 30。

































