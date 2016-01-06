### CANVAS 
##### methods
* beginPath(): 方法开始一条路径，或重置当前的路径；

```
var canvas = document.getElementById('canvas');
var ctx = canvas.getContext('2d');
ctx.beginPath();
```

* strokeStyle: 属性设置或返回用于笔触的颜色、渐变或模式;

    context.strokeStyle=color|gradient|pattern;

* lineCap: 属性设置或返回线条末端线帽的样式。
  
    context.lineCap="butt|round|square";

* closePath():方法创建从当前点到开始点的路径。

* fill(): 方法填充当前的图像（路径）
  
    如果路径未关闭，那么 fill() 方法会从路径结束点到开始点之间添加一条线，以关闭该路径，然后填充该路径。

* lineWidth：属性设置或返回当前线条的宽度，以像素计。