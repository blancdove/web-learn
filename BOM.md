# BOM

> BOM（Browser Object Model）简称浏览器对象模型。

主要处理浏览器窗口（window）和框架（iframe），描述了与浏览器进行交互的方法和接口，可以对浏览器进行访问和操作。不过通常浏览器特定的javascript扩展都被看做BOM的一部分。扩展如下：

1. 弹出新的浏览器窗口
2. 移动、关闭浏览器窗口以及调整窗口大小
3. 提供Web浏览器详细信息的定位对象
4. 提供哦那个胡屏幕分辨率详细信息的屏幕对象
5. 对cookie的支持
6. IE扩展了BOM，加入了ActiveXObject类，可以通过javasc实例化ActiveX对象



### BOM对象的组成

1. window    JavaScript层级中的顶层对象，表示浏览器窗口
2. Navigator    包含客户端浏览器的信息
3. HIstory    包含了浏览器窗口访问过的URl
4. Location    包含了当前URl的信息
5. Screen    包含客户端显示屏的信息



### BOM核心-window

window对象是BOM的顶层（核心）对象

Window对象它具有双重角色，既是通过就是、访问浏览器窗口的一个接口，又是一个全局对象。这意味着在网页中定义的任何对象，变量和函数，都是window的属性



## 详解

### Window对象

Window 对象表示一个浏览器窗口或一个框架。在客户端JavaScript 中，Window 对象是全局对象，所有的表达式都在当前的环境中计算。也就是说，要引用当前窗口根本不需要特殊的语法，可以把那个窗口的属性作为全局变量来使用。例如，可以只写 document，而不必写 window.document。



#### window对象属性

##### innerHeight              innerWidth

返回窗口的文档显示区的高度（包含滚动条的高度）。

##### 

##### pageYOffset            pageXOffset

> `pageYOffset` 属性是 `scrollY` 属性的别名
>
> 为了跨浏览器兼容性，使用 `window.pageYOffset` 代替 `window.scrollY`。
>
> 旧版本的 IE（<9）两个属性都不支持

设置或返回当前页面相对于窗口显示区左上角的Y位置。（只读，设置不改变位置）返回文档/页面垂直方向滚动的像素值。

```js
// 兼容IE9以下写法
var y = (window.pageYOffset !== undefined) ? window.pageYOffset : (document.documentElement || document.body.parentNode || document.body).scrollTop;
```

```css
// 使页面出现滚动条
body{
	width:3000px;
	height:3000px;
}
// pageXOffset设置自定的值后滚动滚动条再次访问值不改变（pageYOffset同）
```



##### outerHeight			outerWidth

获取整个浏览器窗口的高度。（只读）

```js
//  懒加载
// css
body{
	width:3000px;
	height:3000px;
}
div{
	position:absolute;
	left:200px;
	top:1500px;
	width:200px;
	height:200px;
	background:red;
}
// html
<div id="demo" style="opacity: 0.3;"></div>
// js
function check(_id) {
    var oDiv = document.getElementById(_id);
    // HTMLElement.offsetTop 为只读属性，它返回当前元素相对于其 offsetParent 元素的顶部内边距的距离。
    if (oDiv.offsetTop <= window.pageYOffset + window.innerHeight) {

        oDiv.timer = setInterval(function () {
            if (oDiv.style.opacity == '1') {
                clearInterval(oDiv.timer)
            } else {
                oDiv.style.opacity = parseFloat(oDiv.style.opacity) + 0.01;
            }
        }, 60)
    }
}
```



##### screenLeft   screenTop  /  screenX   screenY

> 兼容写法：`window.screenX || window.screenLeft`

只读属性，声明了窗口左上角在屏幕上的X坐标和y坐标。

Chrome、Safari都支持。

Opera、IE支持前面，Firefox支持后面。



##### parent

返回父窗口。



##### top

返回最顶层的先辈窗口。



##### name

设置或返回窗口的名称。



#### window对象方法

##### confirm()

显示带有一段消息以及确认按钮和取消按钮的对话框。



##### prompt()

显示可提示用户输入的对话框。

扩展一个事件：

```js
window.onbeforeunload = function(){
    return '123';
}
// 关闭网页显示是否离开 旧版浏览器会显示return的信息
```



##### open()

打开一个新的浏览器窗口或查找一个已命名的窗口。

```js
// window.open(URL,name,features,replace)
window.open('https://www.baidu.com','百度','width=400,height=500')
// 返回值是新窗口的window
```



##### close()

关闭浏览器窗口。

```
点击+号新建的页面可以关闭，其他的页面就很玄乎
```



##### scrollBy()

按照指定的像素值来滚动内容。



##### scrollTo()

把内容滚动到指定的坐标。



##### setInterval()

按照指定的周期（以毫秒计）来调用函数或计算表达式。



##### setTimeout()

在指定的毫秒数后调用函数或计算表达式。



### Navigator对象

Navigator 对象包含的属性描述了正在使用的浏览器。可以使用这些属性进行平台专用的配置。虽然这个对象的名称显而易见的是 Netscape 的 Navigator 浏览器，但其他实现了 JavaScript 的浏览器也支持这个对象。



#### Navigator对象属性

userAgent：返回由客户机发送服务器的 user-agent 头部的值。（浏览器信息）

cookieEnabled：返回指明浏览器中是否启用 cookie 的布尔值。

onLine：返回指明系统是否处于脱机模式的布尔值。（是否处于离线断网状态）



#### Navigator对象方法





### Location对象

Location 对象包含有关当前 URL 的信息。



#### Location对象属性

href：设置或返回完整的 URL。

prrootocol：设置或返回当前 URL 的协议。

host：设置或返回主机名和当前 URL 的端口号。

pathname：设置或返回当前 URL 的路径部分。

search：设置或返回从问号 (?) 开始的 URL（查询部分）。

hash：设置或返回从井号 (#) 开始的 URL（锚）。（锚点应用：单页面应用）



#### Location对象方法

assign()：加载新文档

```
assign('https://www.baidu.com')
```

reload('force')：重新加载当前文档。参数可选，不填或填 false 则取浏览器缓存的文档（相当于刷新）

replace()：用新的文档替换当前文档。（不会出现回退按钮）



### History对象



#### History对象属性

length：返回浏览器历史列表中的 URL 数量。



#### History对象方法

back()：加载 history 列表中的前一个 URL。

forward()：加载 history 列表中的下一个 URL。

go()：加载 history 列表中的某个具体页面。



#### Screen对象

Screen 对象包含有关客户端显示屏幕的信息。每个 Window 对象的 screen 属性都引用一个 Screen 对象。Screen 对象中存放着有关显示浏览器屏幕的信息。JavaScript 程序将利用这些信息来优化它们的输出，以达到用户的显示要求。例如，一个程序可以根据显示器的尺寸选择使用大图像还是使用小图像，它还可以根据显示器的颜色深度选择使用 16 位色还是使用 8 位色的图形。另外，JavaScript 程序还能根据有关屏幕尺寸的信息将新的浏览器窗口定位在屏幕中间。



#### Screen对象属性

availHeight：返回显示屏幕的高度 (除 Windows 任务栏之外)。

height：返回显示屏幕的高度。







