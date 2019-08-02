> HTML5 中提供了直接拖放的 API，极大的方便我们实现拖放效果，不需要去写一大堆的 js，只需要通过监听元素的拖放事件就能实现各种拖放功能。 
>想要拖放某个元素，==必须设置该元素的 draggable 属性为 true==，当该属性为 false 时，将不允许拖放。而 img 元素和 a 元素都默认设置了 draggable 属性为 true，可直接拖放，如果不想拖放这两个元素，把属性设为 false 即可。

### 拖放事件
- 被拖放的元素称为源对象
- 经过的元素称为过程对象
- 到达的元素称为目标对象

##### 源对象
- dragstart：源对象开始拖放。
- drag：源对象拖放过程中。
- dragend：源对象拖放结束。
##### 过程对象
- dragenter：源对象开始进入过程对象范围内
- dragover：源对象在过程对象范围内移动。
- dragleave：源对象离开过程对象的范围。
##### 目标对象
- drop：源对象被释放时触发。
==凡是在页面内都认为是过程对象，所以要阻止document的dragover的默认行为==


---
### dataTransfer 对象
在所有拖放事件中提供了一个数据传递对象 dataTransfer，用于在源对象和目标对象间传递数据。
==dataTransfer 对象不支持IE==

##### setData()

该方法向 dataTransfer 对象中存入数据。接收两个参数，第一个表示要存入数据种类的字符串，现在支持有以下几种：

text/plain：文本文字。

text/html：HTML文字。

text/xml：XML文字。

text/uri-list：URL列表，每个URL为一行。

第二个参数为要存入的数据。


```
event.dataTransfer.setData('text/plain','Hello World');
```

##### getData()

该方法从 dataTransfer 对象中读取数据。参数为在 setData 中指定的数据种类。

```
event.dataTransfer.getData('text/plain');
```

##### clearData()

该方法清除 dataTransfer 对象中存放的数据。参数可选，为数据种类。若参数为空，则清空所有种类的数据
```
event.dataTransfer.clearData();
```
##### setDragImage()

该方法通过用img元素来设置拖放图标。接收三个参数，第一个为图标元素，第二个为图标元素离鼠标指针的X轴位移量，第三个为图标元素离鼠标指针的Y轴位移量。

##### effectAllowed 和 dropEffect 属性
这两个属性结合起来设置拖放的视觉效果。


