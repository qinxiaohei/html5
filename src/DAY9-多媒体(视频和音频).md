[toc]
# audio
>该标签往页面插入音频标签
## 语法
```
<audio src="song.mp3" controls="controls" loop="loop" autoplay="autoplay">亲 您的浏览器不支持html5的audio标签</audio>

```
>拥有两份源文件的音频播放器
```
<audio controls>
   <source src="horse.ogg" type="audio/ogg">
   <source src="horse.mp3" type="audio/mpeg">
 Your browser does not support the audio element.
 
</audio> 
```
## 音频的兼容性

浏览器 | 版本 | 支持格式
---|---|---
Internet Explorer | 9.0+ | MP3, AAC
Chrome | 6.0+ |  Ogg Vorbis, MP3, WAV（9.0+）
Firefox | 3.6+ | Ogg Vorbis, WAV
Safari | 5.0+ | MP3, AAC, WAV
Opera | 10.0+ | Ogg Vorbis, WAV

>大约有80%的浏览器支持HTML5的`audio`标签，但是并没有一种统一的音频格式。从支持的格式来看，要让所有的浏览器可以播放audio元素上的音频，最佳的方式是提供MP3和Ogg两种格式，兼容代码如下：
```
<audio controls>

    <source src="elvis.mp3" type='audio/mpeg; codecs="mp3"'>

    <source src="elvis.oga" type='audio/ogg; codecs="vorbis"'>

    <!-- 向后兼容代码：如，显示提示信息、提供下载链接使用flash播放器等 -->

    浏览器不支持<code>audio</code>标签

</audio>
```


## 视频的兼容性

浏览器 | 版本 | 支持格式
---|---|---
Internet Explorer | 9.0+ | MP4
Chrome | 6.0+ |  MP4,WebM,Ogg
Firefox | 3.6+ | WebM,Ogg
Safari | 5.0+ | MP4
Opera | 10.0+ | WebM,Ogg

>从浏览器支持的视频格式来看，最佳的方式是提供WebM和MP4两种格式的视频。兼容代码如下：

```
<video controls>    

    <source src=video.webm type=video/webm>    

    <source src=video.mp4 type=video/mp4>      

    <!—向后兼容代码: -->      

    <iframe width="480" height="360" src="http://www.youtube.com/embed/xzMUyqmaqcw?rel=0" frameborder="0" allowfullscreen></iframe>  

</video>
```

## 属性

名称 | 说明
---|---
src | 歌曲的路径
controls | 设置或返回音频/视频是否显示控件（比如播放/暂停等）
loop | 设置或返回音频/视频是否应在结束时重新播放
autoplay | 当歌曲加载后自动播放，但是只有pc端可以实现,移动端不行
currentTime | 指示音频/视频播放的当前位置（以秒计）
playbackRate | 设置或返回音频/视频播放的速度
duration | 返回当前音频/视频的长度（以秒计）
ended | 返回音频/视频的播放是否已结束
muted | 设置或返回音频/视频是否静音
paused | 设置或返回音频/视频是否暂停
volume | 设置或返回音频/视频的音量


## 方法

名称 | 说明
---|---
load()  | 重新加载音频/视频元素
play() | 开始播放音频/视频
pause() | 暂停当前播放的音频/视频


## 事件

名称 | 说明
---|---
canplaythrough  | 当浏览器可在不因缓冲而停顿的情况下进行播放时
ended | 当目前的播放列表已结束时
timeupdate | 当目前的播放位置已更改时

