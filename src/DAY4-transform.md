# DAY4-学习重点（3个）
[toc]

- http://www.w3school.com.cn/cssref/index.asp
## transform
- transform  用来改变属性
- transform  改变多个属性的时候 用空格隔开
#### 1.位移												
- translate(x,y)
- translate3d(x,y,z)
- translateX(x)
- translateY(y)
- translateZ(z)
#### 2.缩放
- scale (x,y)
- scale3d(x,y,z)
- scaleX()
- scaleY()
- scaleZ()
#### 3.旋转 
- rotate（angle 角度）  单位deg
- rotate3d（x,y,z,angle） 第四个参数是角度
- rotateX（angle）
- rotateY（angle）
- rotateZ （angle）
#### 4.倾斜 //没有3d
- skew（x,angle,y）
- skewX（）
- skewY（）

## transition - 过渡属性
- transition 过渡多个属性的时候 属性名称要用逗号隔开  属性和时长和曲线之间还是空格隔开
- transition : 过渡属性的名称 过渡的时长 过渡的曲线 延时
- transition-property  默认值是all
- transition-duration  秒或者毫秒为单位
- transition-timing-function   	linear（匀速) 	ease （慢快慢）	ease-in（慢速开始) 	
- ease-out(慢速结束)	ease-in-out(慢速开始和结束)
- transition-delay  	单位是秒或者毫秒	定义过渡何时开始
- transition-origin 	改变当前元素的位置  	默认值是 50%  50%  0   该属性必须与transform 一起使用
- baceface-visibility :hidden(背面不可见)
- visible(背面可见)



## animation 动画
```
@keyframes	关键帧
@keyframes  名字{
0%（from）{
}
100%(to){
}
}
```
- animation : 名字	动画执行时长		动画的运动曲线 	 延时   动画的播放次数	播放方向
- animation-iteration-count:infinite(无限循环)
- animation-direction 播放方向   默认 normal/ altrenate(反向播放)
- 
- animation-play-state 设置当前动画正在运行还是暂停 running(正在运行)  paused(暂停)
- animation-fill-mode 动画执行完成之后 保留哪一帧  none (默认)forwards保留最后一帧 					   backwards(第一帧) 		both


###  动画里面的一种 - 帧动画
- steps （n(自然数),start | end）
- steps-strat 等于 steds(1,strat)
- steps-end 等于 steds(1,end)
- step-start等同于steps(1,start)，动画分成1步，动画执行时为开始左侧端点的部分为开始；

- step-end等同于steps(1,end)：动画分成一步，动画执行时以结尾端点为开始，默认值为end。
- 回顾：
    定义服务器端：
        @font-face{
            font-family:"自定义",
            src: woff svg eot ttf
        }

    
    iconfont


    flexible.js   
        源码核心点：
            initial-scale = 1 / 设备像素比devicePixelRatio

           根元素的字体大小 = 布局视口的宽 / 10


帧动画：
    定义动画 @keyframes 动画名{
        0%{}
        50%{}
        100%{}
    }

    使用

transform:变形属性，可以设置元素大小，位置，角度，倾斜的变化
大小变化：
    transform:
        scale(x,y);  宽高的变化 
        scaleX(val); 宽度的变化
        scaleY(val); 高度的变化

    val值：>1 表示放大   <1表示缩小


旋转（角度的变化 ）rotate
    rotate(deg) 
    rotate3d(x,y,z)

位置的变化   translate

倾斜   skew
transition过渡动画
    属性值：
    <' transition-property '>： 过渡的属性    必填项
    <' transition-duration '>： 过渡的持续时间（总时长）  必填项
    <' transition-timing-function '>： 过渡的动画类型 
    <' transition-delay '>： 过渡的时间 
    

transition-timing-function:过渡动画类型

linear： 线性过渡。
ease： 平滑过渡。 
ease-in： 由慢到快。 
ease-out： 由快到慢。
ease-in-out： 由慢到快再到慢



sass循环：

@for $i from 起始值  to 截止值   {
    CSS code
}
注意：不包含截止值





    