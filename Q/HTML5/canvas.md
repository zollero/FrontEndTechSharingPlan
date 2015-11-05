#Canvas

>canvas元素是HTML5新增的一个重要元素，专门用来绘制图形。canvas元素就是一块画布，只需要给它指定3个属性即可：id、width和height。在其中利用JavaScript进行绘画。

绘制矩形：

1.  取得canvas元素

2.  取得上下文(context):绘图上下文是一个封装了很多绘图功能的对象。需要使用canvas对象的getContext方法来获得图形上下文，其中的参数只有2d。

3.  填充与绘制边框：用canvas元素绘制图形时，有两种方式——填充(fill)与绘制边框(stroke)。填充指填充图形内部；绘制边框是指不填满图形内部，只绘制图形的外框。

4.  设定绘制样式：绘图的样式，只要是针对图形的颜色而言的，但是并不限于图形的颜色。例如：

    * 设定填充图形的样式：fillStyle属性————填充的样式，在该属性中填入填充的颜色值。
    * 设定图形边框的样式：strokeStyle属性————图形边框的样式，在该属性中填入边框的颜色值。

5.  指定线宽：使用图形上下文对象的lineWidth属性设置图形边框的宽度。

6.  指定颜色值：绘制时填充的颜色或边框的颜色分别通过fillStyle属性与strokeStyle属性来指定。

7.  绘制矩形：分别使用fillRect方法与strokeRect方法来填充矩形或绘制矩形边框。这两个方法的定义如下所示。

        context.fillRect(x,y,width,height)
        context.strokeRect(x,y,width,height)
        contex.clearRect(x,y,width,height)    用于擦除指定的矩形区域中的图形，使得矩形区域中的颜色全部变为透明

  x是指矩形起点的横坐标，y是指矩形起点的纵坐标，坐标原点为canvas画布的最左上角，width是指矩形的长度，height是指矩形的高度。
  
具体绘制矩形的代码：
        
        <canvas id="canvas" width="500" height="400"></canvas>
        
        var canvas = document.getElementById('canvas');
	    var context = canvas.getContext("2d");
	    context.fillStyle = "#eeeeff";
	    context.fillRect(0,0,200,200);
    	context.fillStyle = "red";
    	context.strokeStyle = "blue";
    	context.lineWidth = 1;
    	context.fillRect(50,50,100,100);
    	context.strokeRect(50,50,100,100);



###ddd