## meta
```
<meta name="viewport"content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no">
```
- ①viewport获取视口宽度
- ②device-width设备宽度
- ③initial-scale初始化缩放比例
- ④minimum-scale最小缩放比例
- ⑤maximum-scale最大缩放比例
- ⑥user-scalable=no禁止用户缩放默认值是yes开启状态
```
<metaname="format-detection"content="telephone=no,address=no,email=no">
```
- ①telephone=no禁止浏览器自动识别手机号/禁止拨打手机号码
- ②address=no禁止浏览器自动识别地址/禁止跳转地图/地址
- ③email=no禁止浏览器自动识别邮箱/禁止发送邮件/邮箱<metahttp-equiv="X-UA-Compatible"content="IE=edge,chrome=1">
- ①优先考虑IE浏览器与谷歌浏览器
- ②IE=edge表示IE浏览器的最高模式来渲染页面(最高模式就是最新版本)
## 移动端解决1px
- ios设备 解决1px 
    - 缩放 border:1px solid red
    - transform:scale(0.5)
    - meta: inital-scale=0.5
```
<body>
	<div id="main" style="border: 1px solid #000000;"></div>
</body>
<script type="text/javascript">
if (window.devicePixelRatio && devicePixelRatio >= 2) {
	var main = document.getElementById('main');
	main.style.border = '.5px solid #000000';
}
</script>

```
```
设计师 设计稿 640px   设备尺寸 320px   
<meta name="viewport" content="initial-scale=0.5, maximum-scale=0.5, minimum-scale=0.5, user-scalable=no">

```
- android 设备
    - border-image
    - 渐变
    - 阴影
    - 伪元素
    
## iconfont 字体图标
- 阿里巴巴图标库
- font awesome字体图标库
- 