
# DAY1-学习重点（5个）
- ==**4个概念**==
   - **设备检测**
        - 判断 是苹果或安卓手机
        - window.navigator.appVersion
   - **移动app的开发方式**
        - nativeapp（原生app）
        - webApp
        - hybridapp（混合app）
   - **手机像素**
        - 逻辑像素 css
        - 物理像素 设备
        - 设备像素比（window.devicePixelRatio）
   - **手机视口 - viewport**
        - 理想视口
        - 布局视口
        - 视觉视口
- ==**1种布局** - 弹性盒布局==
    - 自适应
    - 圣杯布局
    - 双飞翼布局s
    - 绝对定位布局
    - flex弹性盒布局（父/子元素、属性、使用场景）
    - 优缺点

## 1: 课程导入
- **简介**：在新的移动互联网的浪潮中，移动web的份额将会逐渐超越PC端。身为Web前端工程师我们，更应该站在时代和技术的最前缘，拥抱移动web所带来的变革
- **课程**包含移动web的开发基础，高效的排版布局，常见的移动web问题，终端触摸交互，各种bug坑如何解决等多方面。

## 2: 移动开发中的像素（px）
- 首先，大家来思考一个问题：==640x1136的图片，能不能在iPhone5上完全显示==？
- 毕竟iPhone5的分辨率是为640x1136的。
- 代码展示
- 发现在浏览器上显示的iPhone5尺寸是320px*568px，
- 我们先捋一捋各种像素之间的关联马上就能明白

## 3：物理像素与逻辑像素傻傻分不清楚？
- iPhone5的分辨率（640x1136）
- 但是iPhone5尺寸是320px*568px，（物理像素）
    - 物理像素，也可以说是设备无关像素，
    - 单位是dp或者pt
    - 
- 而我们开始使用的CSS样式中
    - px代表的是逻辑像素
    - 是浏览器使用的抽象单位
    - 
- dpr 两种像素之间的关系
    - 获取设备像素比
    - var devicePixelRatio=window.devicePixelRatio;==(必考题)==
###### - 在维度上-dpr计算公式：1px = 2*dp
- 设备像素比(DPR) = 逻辑像素(640)/物理像素(320) 
- 320px = 640dp

## 4：Viewport相关知识
- 一个PC的页面在移动设备上展示的效果是怎么样的？答案就是整个页面都铺满在手机上了（不过里面的文字和照片什么的全都变小了）！是不是非常的unimaginable？其实这就是在html文档中Viewport的神秘力量。
- 手机浏览器默认为我们做了两件事：     
    -  1、使页面渲染在一个980px（IOS）的布局viewport中；
    -  2、对页面进行缩放

#### >1、为什么要有Viewport？
- 为什么手机浏览器在渲染一个页面时，要有Viewport？
那是因为Viewport是手机浏览器虚拟出来的一个区域，目的是为了避免PC端的页面到了手机端可能会出现的布局错乱问题。
#### 2、为什么不使用980px
- 但是在真正的开发中，我们却不会去使用默认的980px的布局viewport，为什么不使用呢？原因如下：

- 宽度不可控制，不同系统不同设备的默认值都可能不同；
- 页面缩小版显示，交互不友好；
- 链接不可点击；
- 有缩放，缩放后又有滚动；
- 最主要的是font-size为40px等于PC上12px同等物理大小，不规范
- 
**基于以上原因，我们可以通过meta标签去改变**
####  3、meta标签  -Viewport
- 设置Viewport中meta标签的默认语法为：
```
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
    - width:设置布局viewport的特定值（device-width）
    - initial-scale:设置页面的初始缩放
    - minimum-scale:最小缩放
    - maximum-scale:最大缩放
    - user-scalable:用户能否缩放
- 如何将宽高为320x568的元素铺满整个iPhone5手机浏览器屏幕呢？ meta
- <meta name="viewport" content="width=320" />
###### - width=device-width
- width=device-width这个属性值的含义就是布局viewport 等于我们的设备viewport。

**总结就是：** 移动web最佳viewport设置为：布局viewport = 设备宽度 = 度量viewport

## 5: 高效的移动web布局，还需掌握技术栈
- 移动设备上有着不同尺寸不同分辨率，使用高效的弹性布局或响应式布局，开发出高效简洁且兼容性强的页面是我们这章要学习的主要内容。
- 百分比布局
- 弹性盒布局
- 响应式布局

## 6: flexbox弹性盒子布局
#### **回顾一下我们常用的布局：**
- pc布局
    - 固定布局
    - 流式布局
    - 圣杯布局
    - 双飞翼布局
- 移动端布局
    - 百分比布局
    - 弹性盒布局 flex
    - 响应式布局 



### **flex布局注意点：**
- 任何一个容器都可以指定为Flex布局
- 行内元素也可以使用Flex布局。
```
.box{
 display:inline-flex;
}
```
- Webkit内核的浏览器，必须加上 -webkit前缀。
- 注意：设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。
### **6个属性设置在父元素上**
- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content
- //给父元素设置
- display:flex;      设置一个弹性和     （后边的元素才会起效）



**align-items  //设置垂直(侧轴)方向的对齐方式  **
           flex-start     交叉轴起点对齐。
           flex-end      交叉轴终点对齐。
           center        交叉轴中点对齐。
     	   baseline     项目的第一行文字的基线对齐。
           stretch (默认值)：如果项目未设置高度或设为auto，将占满整个容器的高度

**align-content    //设置多轴对齐的方式  (如果只有一根轴线，一行，这个属性不起作用)**
     flex-start 
     flex-end  
     center
     space-between

<!--Easy Sass-->
<!--Js-css-HTML For-->

### 以下6个属性设置在项目(子元素)上。
- order
- flex-grow
- flex-shrink
- flex-basis
- flex
- align-self

### 优点：
1. 跨平台和终端且不需要分配子域
2. 兼容当前及未来新设备
3. 节约了开发成本
### **不足:**
   1. 兼容性：低版本浏览器兼容性有问题
   2. 移动带宽流量：相比较手机定制网站，流量稍大，但比较加载一个完整pc端网站显然是小得多
   3. 代码累赘（dom结构复杂，样式复杂），会出现隐藏无用的元素，加载时间加长，兼容各种设备工作量大，后期制作维护复杂。
   4. 
   
### - 考试题填空题
- 判断 苹果或安卓手机
- var isAndroid=win.navigator.appVersion.match(/android/gi)
- var isIPhone=win.navigator.appVersion.match(/iphone/gi)
- 获取设备像素比
- var devicePixelRatio=win.devicePixelRatio;





优点 | 缺点
---|---
圣杯 | 结构简单，无多余 dom 层 | 中间部分宽度小于左侧时布局混乱
绝对定位 | 结构简单，且无需清理浮动 | 两侧高度无法支撑总高度
双飞翼 | 支持各种宽高变化，通用性强 | dom 结构多余层，增加渲染树生成的计算量



<html>
<h1>圣杯</h1>
<!--在这里插入内容-->
<img width="400" src="https://upload-images.jianshu.io/upload_images/5109559-cde7ae6d2899b5c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/550/format/webp">
</html>

<html>
<h1>双飞翼</h1>
<!--在这里插入内容-->
<img width="400" src="https://segmentfault.com/img/bVYtjF?w=922&h=561">
</html>

<html>
<h1>flex</h1>
<!--在这里插入内容-->
<img width="200" height="200" src="https://upload-images.jianshu.io/upload_images/5109559-cde7ae6d2899b5c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/550/format/webp">
<img width="300" height="200" src="https://segmentfault.com/img/bVYtjF?w=922&h=561">
</html>



