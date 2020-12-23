# 脚本化CSS

> 使用 `javascript` 来操作 `css`



### 读写行间样式

> HTMLElement.style

只能读写**行间**的css样式

含有连字符的样式属性，应改为**小驼峰式**。例如 `border-radius` 写为 `borderRadius`



### 查询计算样式

> window.getComputedStyle(element, [pseudoElt]);
>
> **element**
>
> 用于获取计算样式的 `Element`
>
> **pseudoElt ** 可选
>
> 指定一个要匹配的伪元素的字符串。必须对普通元素省略（或 `null`）。

只读的。

返回的计算样式都是实时的，且都是绝对值（没有相对单位）。



查询样式

> HTMLElement.currentStyle
>
> IE独有的属性

只读。

返回的样式不是绝对值。















