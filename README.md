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



#### 盒模型

**margin+border+padding+（content=width+height）**

外边距：margin（容器与容器之间的距离）

盒子边框：border

内边距：padding（容器与内部内容之间的距离, 内边距是不能放内容的,并且会把盒子撑开）

盒子内容：width+height