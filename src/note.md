## better-scroll
- 3句话
- html结构  父盒子  写在父盒子  作用于 第一个子元素
- css样式   父盒子 over：h   子元素高于父元素  出现滚动条
            父盒子必须有 - 定宽/定宽

- js   初始化  new BScroll("父盒子")

## 回弹
- new BScroll("父盒子")

##上拉加载 下拉刷新
probeType 结合使用 scroll 事件
什么时候触发：
 probeType ：0不触发 scroll
            1  触发  一定时间之后
            2  触发  实时触发
            3  滑动/图滚动  触发  
- 初始化   new BScroll("父盒子",{probeType:2})
- 绑定scroll 事件    on(事件类型,callback)
   条件判断  this.y    this.maxScrollY   
        flag  true   
- 绑定scrollEnd 事件   
    window.locaton.reload()  - 下拉刷新
    loadData   - 上拉加载
- 上拉加载
    moni数据
    截取 5条  splice(0,5)  newData.map(return li).join("")
    提升用户体验
    先记录pos = this.maxScrollY-h
         bscroll.refresh()
         bscroll.scrollTo()


    

