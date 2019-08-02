# DAY2-学习重点（3个）
- ==1个sass==
    - sass使用
- ==2种布局==
   - **@media - 响应式布局**
        - 使用语法
        - 使用场景
        - sass的使用(混合宏/占位符/函数的定义)
   - **利用rem 布局**
        - 利用media计算
        - 利用js计算
        - 利用calc计算
        - 利用sass计算(函数)

- ==温馨提示:请注意==
```
-在掌握上述的基础知识后，需要进行大量的排版练习，加深记忆
```

## 响应式网页设计(媒体查询)
- 如何实现
- 1.CSS3-media Query(媒体查询)
- 媒体查询的语法：
    - @media(规定制度)and(规定制度){css样式}
    - 样式仅在规定的宽度范围内生效
- 2.Javascript
- 3.第三方开源框架(Bootstrap)
```
@media screen and (min-width: 640px){
body{
  background:red;
        }
}
@media (min-width: 640px) and (max-width:980px){
body{
  background:pink;
}
}

@media screen and (max-width:980px){
body{
  background:blue;
}
}
```


## css预处理器
#### scss/less  scss功能更强大点，里面有宏概念
- .sass 后缀名
- .scss 后缀名
- 1.编译风格
- nested:嵌套缩进

- 2.变量  以 $开头
- 3.加减乘除的计算
- 4.嵌套
```
                                        标签嵌套：
div{
p{
}
}
属性嵌套
div{
border:{
color:#fff
}
}
& 当前位置的父元素
```
- 5.注释
 - 单行注释 // 单行注释只存在源文件里
 - 多行注释 /* */   会编译到CSS文件里面
- 6.继承
 - @extend 类名
- 7.mixin    强大之处在于可以传参和设置缺省值
```
@mixin 名字{
代码块
}
传参 
@mixin 名字（$变量：默认值）{                             
属性：$变量名
}
调用： @include 名字
            @include 名字（参数)
```
- 8.引入外部文件
 - @import “ ”；

- 9.自定义函数
```
@function 函数名（参数）{
@return 返回值
}
调用   div{
属性：函数名（参数）
}
```
## 响应式网页设计(rem)
- 单位 rem
- rem相对于html 也就是根元素
- em 相对于父元素 有继承性

- 引入flexible.js	做适配用的
- 只适配了iPhone手机 安卓手机没又做适配 安卓手机适配为1