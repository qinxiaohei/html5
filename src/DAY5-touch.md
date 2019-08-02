# DAY5-移动事件（3个）
[toc]


## 什么是touch事件
- 随着智能手机和平板电脑的普及, 越来越多的人用移动设备浏览网页，我们平时在pc浏览器上用的鼠标事件，比如：click, mouseover等， 已经无法满足移动设备触摸屏的特点，触摸时代的到来，离不开那些触摸事件. touch事件多用于移动端，可响应用户手指（或触控笔）对屏幕或者触控板操作，给基于触控操作，给基于触控的用户界面提供可靠的支持

## 移动端操作和pc端操作的区别
### pc端事件操作
- 鼠标按下 mousedown
- 鼠标移动 mousemove
- 鼠标抬起 mouseup

### 移动端事件操作
- 手指按下 touchstart
- 手指移动 touchmove
- 手指抬起 touchend

### 移动端的四个基本事件
- touchstart 手指接触到屏幕就触发
- touchmove 手指在屏幕上滑动持续触发
- touchend 手指离开屏幕时触发
- touchcancel 当前正在进行的事件被一些外来因素打断的时候，会触发；

## 移动端事件对象存储信息
- touches
- targetTouches
- changedTouches

## 手指信息存放
- e.touches	所有的手指信息
- e.touches[0]	第一个手指的信息
- targetTouches		目标元素的信息
- changedTouches	手指离开时候的信息

- screenX/screenY	屏幕
- pageX/pageY 		页面
- clientX/clientY		视口

## 多点触摸

## 移动端300ms的故事
- tap事件是zepto里面的点击事件
- click有300ms延时 这延时是判断单击还是双击
- 
- 移动web页面上的click事件响应都要慢上300ms。原因是在开始的时候移动设备访问的web页面都是PC上的页面，在默认的viewport（980px）的页面往往都是需要“双击”或“捏开”放大页面来看清页面。而正是为了确认用户是“双击”还是“单击”，safari浏览器需要个300ms的延迟来判断。而后来的iPhone也一直延用这样的设计，而借鉴成功iPhone的android也延用这样的设计。于是300ms就成为了一道规范。

### 如何解决300ms延迟的问题？
- 使用Tab事件代替click事件，其中的原理是：在touchstart、touchend时记录时间、手指的位置，在touchend时进行比较，如果手指位置为同一位置（或允许移动一个非常小的位移值）且时间间隔较短（一般认为是150ms），且过程中未曾触发过touchmove，即可认为触发了手持设备上的“click”，一般称它为“tap”

## 简单移动端事件的封装
- 为什么要封装事件，因为仅有的四个事件不符合人类的操作习惯，需要封装
- 
- 封装轻击（tap）
```
// 移动端的点击事件会有300ms的延迟，（这300ms的延时是来判断是单击还是双击） 优化
// 触发点击事件是
// 先触发了touch事件  如果是点击事件   没有touchmove事件
// 触屏开始 和 结束 的时间差 要小于 150ms
/*
* 参数说明
* obj：绑定点击事件的对象
* callback: 点击事件触发后 要执行的代码
* */


/* 全局污染 */
// 命名空间  避免全局污染

var myTap={
  tap:function(obj,callback){
    if(typeof obj=="object"){
      //定义变量记录数据
      var startTime=0;
      var isMove=false;
      //触屏开始
      obj.addEventListener('touchstart',function(){
        startTime=Date.now(); //时间戳
      });


      //触屏移动
      obj.addEventListener('touchmove',function(){
        isMove=true;
      });


      //触屏结束
      obj.addEventListener('touchend',function(e){
        //判断 没有移动过 时间小于150ms  为点击事件
        if(!isMove&&Date.now()-startTime<150){
          callback&&callback(e);
        }


        //数据重置
        isMove=false;
        startTime=0;
      });
  }
  }
};
```
- 封装滑动事件(swipeLeft,swipeRight,swipeTop,swipeBottom) ...
