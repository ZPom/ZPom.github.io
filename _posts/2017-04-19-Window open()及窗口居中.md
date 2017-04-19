---
layout: post
title: "Window open()及窗口居中"
date:  2017-4-19
description: "Window open()及窗口居中"
tag: JavaScript 

---
**定义和用法**

> open() 方法用于打开一个新的浏览器窗口或查找一个已命名的窗口。

----------
**语法**

> ``window.open(URL,name,specs,replace)``

| 参数    |     说明|
| --- | --- |
|   URL  |  可选。打开指定的页面的URL。如果没有指定URL，打开与新的空白窗口   |
|   name  |   	可选。指定target属性或窗口的名称。支持以下值：<br />&nbsp;&nbsp;&nbsp;&nbsp;==_blank - URL加载到一个新的窗口。这是默认;==<br/>&nbsp;&nbsp;&nbsp;&nbsp;==_parent - URL加载到父框架;==<br />&nbsp;&nbsp;&nbsp;&nbsp;==_self - URL替换当前页面;==<br />&nbsp;&nbsp;&nbsp;&nbsp;==_top - URL替换任何可加载的框架集;==<br />&nbsp;&nbsp;&nbsp;&nbsp;==name- 窗口名称;==|
|  specs   |   可选。一个逗号分隔的项目列表。支持以下值： <br />	&nbsp; &nbsp;&nbsp;&nbsp;`channelmode=yes|no|1|0`：==是否要在影院模式显示 window。默认是没有的。仅限IE浏览器==;<br />	&nbsp; &nbsp;&nbsp;&nbsp;`directories=yes|no|1|0`：==是否添加目录按钮。默认是肯定的。仅限IE浏览器;==<br />&nbsp; &nbsp;&nbsp;&nbsp;`fullscreen=yes|no|1|0`：==浏览器是否显示全屏模式。默认是没有的。在全屏模式下的 window，还必须在影院模式。仅限IE浏览器==<br />&nbsp; &nbsp;&nbsp;&nbsp;`height=pixels`：==窗口的高度。最小.值为100==<br />&nbsp; &nbsp;&nbsp;&nbsp;`left=pixels`：==该窗口的左侧位置==<br />&nbsp; &nbsp;&nbsp;&nbsp;`location=yes|no|1|0`：==是否显示地址字段.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`menubar=yes|no|1|0`：==是否显示菜单栏.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`resizable=yes|no|1|0`：==是否可调整窗口大小.默认值是yes==<br />&nbsp;&nbsp; &nbsp;&nbsp;`scrollbars=yes|no|1|0`：==是否显示滚动条.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`status=yes|no|1|0`：==是否要添加一个状态栏.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`titlebar=yes|no|1|0`：==是否显示标题栏.被忽略，除非调用HTML应用程序或一个值得信赖的对话框.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`toolbar=yes|no|1|0`：==是否显示浏览器工具栏.默认值是yes==<br />&nbsp; &nbsp;&nbsp;&nbsp;`top=pixels`：==窗口顶部的位置.仅限IE浏览器==<br />&nbsp; &nbsp;&nbsp;&nbsp;`width=pixels`：==窗口的宽度.最小.值为100==|
|  replace   |    	Optional.Specifies规定了装载到窗口的 URL 是在窗口的浏览历史中创建一个新条目，还是替换浏览历史中的当前条目。支持下面的值：<br />&nbsp; &nbsp;&nbsp;&nbsp;==true - URL 替换浏览历史中的当前条目。==<br />&nbsp; &nbsp;&nbsp;&nbsp;==false - URL 在浏览历史中创建新的条目。== |

----------

**弹出窗口居中方法**

``` javascript
function openWin(url,name,iWidth,iHeight) { 
            //获得窗口的垂直位置 
            var iTop = (window.screen.availHeight - 30 - iHeight) / 2; 
            //获得窗口的水平位置 
            var iLeft = (window.screen.availWidth - 10 - iWidth) / 2; 
            window.open(url, name, 'height=' + iHeight + ',innerHeight=' + iHeight + ',width=' + iWidth + ',innerWidth=' + iWidth + ',top=' + iTop + ',left=' + iLeft + ',status=no,toolbar=no,menubar=no,location=no,resizable=no,scrollbars=0,titlebar=no'); 
        }
```

----------
**如何关闭弹出窗口？**

在新打开页面中执行代码：

``` stata
window.opener = null; window.open('', '_self'); window.close();
<input type="button" onclick="window.opener = null; window.open('', '_self'); window.close();" value="关闭" />
```


