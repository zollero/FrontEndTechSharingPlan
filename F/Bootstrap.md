#Bootstrap 简介

###什么是 Bootstrap？
Bootstrap 是一个用于快速开发 Web 应用程序和网站的前端框架。
Bootstrap 是基于 HTML、CSS、JAVASCRIPT 的。

###历史
Bootstrap 是由 Twitter 的 Mark Otto 和 Jacob Thornton 开发的。
Bootstrap 是 2011 年八月在 GitHub 上发布的开源产品。

###为什么使用 Bootstrap？
移动设备优先：自 Bootstrap 3 起，框架包含了贯穿于整个库的移动设备优先的样式。

###浏览器支持：所有的主流浏览器都支持 Bootstrap。
IE Firefox Opera Chrome Safari

容易上手：只要您具备 HTML 和 CSS 的基础知识，您就可以开始学习 Bootstrap。
响应式设计：Bootstrap 的响应式 CSS 能够自适应于台式机、平板电脑和手机。
更多有关响应式设计的内容详见 Bootstrap 响应式设计。

###响应式设计
它为开发人员创建接口提供了一个简洁统一的解决方案。
它包含了功能强大的内置组件，易于定制。
它还提供了基于 Web 的定制。
它是开源的。

##标题（一）
Bootstrap和普通的HTML页面一样，定义标题都是使用标签`<h1>`到`<h6>`,只不过Bootstrap覆盖了其默认的样式，使用其在所有浏览器下显示的效果一样，具体定义的规则可以如下表所示：
![Alt text](http://img.mukewang.com/53acce330001429807730337.jpg)
通过比较可以发现，Bootstrap标题样式进行了以下显著的优化重置：

1、重新设置了margin-top和margin-bottom的值，  h1~h3重置后的值都是20px；h4~h6重置后的值都是10px。
2、所有标题的行高都是1.1（也就是font-size的1.1倍）,而且文本颜色和字体都继承父元素的颜色和字体。
3、固定不同级别标题字体大小，h1=36px，h2=30px，h3=24px，h4=18px，h5=14px和h6=12px。

标题的具体运用非常简单，和我们平时运用是一样的，使用`<h1>`~`<h6>`标签，分别表示标题一至标题六，h 后面的数字越大，表示级别越小，文本也越小。

在Bootstrap中为了让非标题元素和标题使用相同的样式，还特意定义了.h1~.h6六个类名。

```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>标题（一）</title>
<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<!--Bootstrap中的标题-->
<h1>Bootstrap标题一</h1>
<h2>Bootstrap标题二</h2>
<h3>Bootstrap标题三</h3>
<h4>Bootstrap标题四</h4>
<h5>Bootstrap标题五</h5>
<h6>Bootstrap标题六</h6>

<!--Bootstrap中让非标题元素和标题使用相同的样式-->
<div class="h1">Bootstrap标题一</div>
<div class="h2">Bootstrap标题二</div>
<div class="h3">Bootstrap标题三</div>
<div class="h4">Bootstrap标题四</div>
<div class="h5">Bootstrap标题五</div>
<div class="h6">Bootstrap标题六</div>

<!--任务填写下方-->
<h1>我的第一个bootstrap标题</h1>
    
</body>
</html>
```
对比两个示例的效果图，可以说他们的效果是一模一样的。
##标题（二）
除此之外，我们在Web的制作中，常常会碰到在一个标题后面紧跟着一行小的副标题。在Bootstrap中他也考虑了这种排版效果，使用了`<small>`标签来制作副标题。这个副标题具有其自己的一些独特样式：

1、行高都是1，而且font-weight设置了normal变成了常规效果（不加粗），同时颜色被设置为灰色（#999）。
2、由于`<small>`内的文本字体在h1~h3内，其大小都设置为当前字号的65%；而在h4~h6内的字号都设置为当前字号的75%；
详细代码请参阅bootstrap.css文件中第407行~第443行。
```
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 10px;
  margin-bottom: 10px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
```
来简单看其使用方法与最终效果：如下所示。
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>标题（二）</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>

<!--Bootstrap中使用了<small>标签来制作副标题-->
<h1>Bootstrap标题一<small>我是副标题</small></h1>
<h2>Bootstrap标题二<small>我是副标题</small></h2>
<h3>Bootstrap标题三<small>我是副标题</small></h3>
<h4>Bootstrap标题四<small>我是副标题</small></h4>
<h5>Bootstrap标题五<small>我是副标题</small></h5>
<h6>Bootstrap标题六<small>我是副标题</small></h6>

<!--任务填写处-->

<div class="h1">孤儿院无私奉献30年 <div class="small"> 一曲人性的赞歌</div></div>
<div class="h1">孤儿院无私奉献30年 <small> 一曲人性的赞歌</small></div>
<h1>孤儿院无私奉献30年 <small> 一曲人性的赞歌</small></h1>
</body>
</html>
```
##段落（正文文本）
段落是排版中另一个重要元素之一。在Bootstrap中为文本设置了一个全局的文本样式（这里所说的文本是指正文文本）：

1、全局文本字号为14px(font-size)。

2、行高为1.42857143（line-height），大约是20px(大家看到一串的小数或许会有疑惑，其实他是通过LESS编译器计算出来的，当然Sass也有这样的功能)。

3、颜色为深灰色（#333）；

4、字体为"Helvetica Neue", Helvetica, Arial, sans-serif;（font-family），或许这样的字体对我们中文并不太合适，但在实际项目中，大家可以根据自己的需求进行重置，在此我们不做过多阐述，我们回到这里。该设置都定义在<body>元素上，由于这几个属性都是继承属性，所以Web页面中文本（包括段落p元素）如无重置都会具有这些样式效果。

```

body {
font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
font-size: 14px;
line-height: 1.42857143;
color: #333;
background-color: #fff;
}
```
另外在Bootstrap中，为了让段落p元素之间具有一定的间距，便于用户阅读文本，特意设置了p元素的margin值（默认情况之下，p元素具有一个上下外边距，并且保持一个行高的高度）：
```
p {
 margin: 0 0 10px;
}
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>段落（正文文本）</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<p>超酷的互联网、IT技术免费学习平台，创新的网络一站式学习、实践体验；服务及时贴心，内容专业、有趣易学。专注服务互联网工程师快速成为技术高手！</p>
<p>超酷的互联网、IT技术免费学习平台，创新的网络一站式学习、实践体验；服务及时贴心，内容专业、有趣易学。专注服务互联网工程师快速成为技术高手！</p>
<!--下面是代码任务部分-->
<p>我是一个段落，你猜我在Bootstrap是以什么样的风格显示。</p>
</body>
</html>
```
##强调内容
在实际项目中，对于一些重要的文本，希望突出强调的部分都会做另外的样式处理。Bootstrap同样对这部分做了一些轻量级的处理。

如果想让一个段落p突出显示，可以通过添加类名“.lead”实现，其作用就是增大文本字号，加粗文本，而且对行高和margin也做相应的处理。用法如下：

“.lead”对应的样式如下：
```
.lead {
margin-bottom: 20px;
font-size: 16px;
font-weight: 200;
line-height: 1.4;
}
@media (min-width: 768px) {/*大中型浏览器字体稍大*/
.lead {
font-size: 21px;
  }
}
```
除此之外，Bootstrap还通过元素标签:`<small>`、`<strong>`、`<em>`和`<cite>`给文本做突出样式处理。
```
b,strong {
  font-weight: bold; /*文本加粗*/
}
```
```
small,.small {
  font-size: 85%; /*标准字体的85%,也就是14px * 0.85px，差不多12px*/
}
```
```
cite {
font-style: normal;
}
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>强调内容</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<p>我是普通文本，我的样子长成这样我是普通文本，我的样子长成这样我是普通文本，</p>
<p class="lead">我是特意要突出的文本，我的样子成这样。我是特意要突出的文本，我的样子长成这样。</p>
</body>
</html>
```
