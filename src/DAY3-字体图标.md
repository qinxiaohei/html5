[toc]

## 服务端字体

### 为什么要用服务器字体

在css3之前，页面文字所使用的字体必须已经在客户端中被安装才能正常显示，但是如果这个字体在客户端中没有安装的话，使用这个字体就不能正常显示了。

为了解决这个问题，在css3中，新增了web fonts功能，网页中可以使用web服务器端的字体，只要某个字体在web服务器端安装了，这个字体就能正常显示了。


### 怎么使用服务器字体
>定义服务器端字体的语法

```
@font-face {
	font-family: 'diyfont'; // 自定义字体名称
	src: url('diyfont.eot'); /* IE9+src:url('路径') 设置字体路径 */   
	src: url('diyfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
		 url('diyfont.woff') format('woff'), /* chrome、firefox */
		 url('diyfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
		 url('diyfont.svg#fontname') format('svg'); /* iOS 4.1- */
}
// 使用服务器端字体
body{
    font-family:myFirstFont;
}


.box{
	font-family:'diyfont'
}

```


### 兼容当前的主流浏览器服务器字体四大格式
>TureType              (.ttf)
 Web Open Font Format  (.woff)
 Embedded Open Type    (.eot)
 SVG                   (.svg)

## 字体图标icontont

### 是什么
>Iconfont 就是指用字体文件取代图片文件，来展示图标、特殊字体等元素的一种方法

### 哪些网站在用它
淘宝：

![image](https://images2015.cnblogs.com/blog/885995/201602/885995-20160224134748536-1884639931.jpg)
![image](https://images2015.cnblogs.com/blog/885995/201602/885995-20160224134801552-1475584184.jpg)

新浪微博用到的地方：

![image](https://images2015.cnblogs.com/blog/885995/201602/885995-20160224134836958-1312914092.jpg)
![image](https://images2015.cnblogs.com/blog/885995/201602/885995-20160224134848802-193501372.jpg)

### 优点
- 加载文件体积小
- 可以直接通过css的font-size，color修改它的大小和颜色
- 矢量图，放大缩小不失真。
- 兼容低版本浏览器（ie4）

### 缺点
- 矢量图只能是纯色的。
- 制作门槛高，耗时长，维护成本也很高

### 使用Iconfont

- 设计师设计矢量图片然后通过工具直接转换成相应的字体
- 使用第三方Iconfont 在线服务（例如： 阿里巴巴Iconfont平台 ），然后直接上传你自己设计的图标矢量图生成字体文件