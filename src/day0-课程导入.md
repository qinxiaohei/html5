想一想
[toc]
### # 平常上网的时候，我们都用过什么设备呢？
- https://segmentfault.com/

### # 思考 计算机如何知道 我们现在使用的到底是什么设备呢？
```
function browserRedirect(pcurl,appurl) {  
    var sUserAgent = navigator.userAgent.toLowerCase();  
//  console.info(sUserAgent)
    var bIsIpad = sUserAgent.match(/ipad/i) == "ipad";  
    var bIsIphoneOs = sUserAgent.match(/iphone os/i) == "iphone os";  
    var bIsMidp = sUserAgent.match(/midp/i) == "midp";  
    var bIsUc7 = sUserAgent.match(/rv:1.2.3.4/i) == "rv:1.2.3.4";  
    var bIsUc = sUserAgent.match(/ucweb/i) == "ucweb";  
    var bIsAndroid = sUserAgent.match(/android/i) == "android";  
    var bIsCE = sUserAgent.match(/windows ce/i) == "windows ce";  
    var bIsWM = sUserAgent.match(/windows mobile/i) == "windows mobile";  
     
    if (bIsIpad || bIsIphoneOs || bIsMidp || bIsUc7 || bIsUc || bIsAndroid || bIsCE || bIsWM) {   
        window.location.href = appurl;
    } else {  
        document.writeln("pc");  
         window.location.href = pcurl;
    }  
}  
```
   
### - 考试题填空题
```
- 判断 苹果或安卓手机
- var isAndroid=window.navigator.appVersion.match(/android/gi)
- var isIPhone=window.navigator.appVersion.match(/iphone/gi)
- 获取设备像素比
- var devicePixelRatio=window.devicePixelRatio;
```

### #pc/手机app的运行系统
### #移动端app的开发方式
### #640x1136的图片，能不能在iPhone5上完全显示？


flex 弹性盒布局
父元素写的属性
- 开一个弹性盒  display:flex()
主轴  flex-derection


项目默认设置：
	- 项目在一行显示
	- 项目自动继承弹性父盒子的高度
	- float  vertical-align:middle 不起作用
	


子元素/项目
- flex-grow:1;   撑开剩余的空间
- order:2;   flex盒子排序
- 