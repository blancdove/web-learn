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