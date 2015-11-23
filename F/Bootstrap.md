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
<p>我是普通文本，我不需要强调显示</p>
<p class="lead">这部分内容需要特别的强调，我和别人长得不一样</p>
</body>
</html>
```
###粗体
粗体就是给文本加粗，在普通的元素中我们一般通过font-weight设置为bold关键词给文本加粗。在Bootstrap中，可以使用`<b>`和`<strong>`标签让文本直接加粗。
###斜体
在排版中，除了用加粗来强调突出的文本之外，还可以使用斜体。斜体类似于加粗一样，除了可以给元素设置样式font-style值为italic实现之外，在Bootstrap中还可以通过使用标签`<em>`或`<i>`来实现。
###强调相关的类
在Bootstrap中除了使用标签`<strong>`、`<em>`等说明正文某些字词、句子的重要性，Bootstrap还定义了一套类名，这里称其为强调类名（类似前面说的“.lead”）,这些强调类都是通过颜色来表示强调，具本说明如下：

+   .text-muted：提示，使用浅灰色（#999）
+   .text-primary：主要，使用蓝色（#428bca）
+   .text-success：成功，使用浅绿色(#3c763d)
+   .text-info：通知信息，使用浅蓝色（#31708f）
+   .text-warning：警告，使用黄色（#8a6d3b）
+   .text-danger：危险，使用褐色（#a94442）
举个例子
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>强调相关的类</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<div class="text-muted">.text-muted 效果</div>
<div class="text-primary">.text-primary效果</div>
<div class="text-success">.text-success效果</div>
<div class="text-info">.text-info效果</div>
<div class="text-warning">.text-warning效果</div>
<div class="text-danger">.text-danger效果</div>
<!--下面是任务部分-->
<p class="text-danger">我是一段危险信息，请用Bootstrap框架中的危险风格显示</p>
</body>
</html>
```
###文本对齐风格
在排版中离不开文本的对齐方式。在CSS中常常使用text-align来实现文本的对齐风格的设置。其中主要有四种风格：

  ☑  左对齐，取值left

  ☑  居中对齐，取值center

  ☑  右对齐，取值right

  ☑  两端对齐，取值justify

为了简化操作，方便使用，Bootstrap通过定义四个类名来控制文本的对齐风格：

  ☑   .text-left：左对齐

  ☑   .text-center：居中对齐

  ☑   .text-right：右对齐

  ☑   .text-justify：两端对齐
  特别声明：目前两端对齐在各浏览器下解析各有不同，特别是应用于中文文本的时候。所以项目中慎用。
  举个例子：
  ```
  <!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>文本对齐风格</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<p class="text-left">我居左</p>
<p class="text-center">我居中</p>
<p class="text-right">我居右</p>
<p class="text-justify">There is clearly a need for CSS to be taken seriously by graphic artists. The Zen Garden aims to excite, inspire, and encourage participation. To begin, view some of the existing designs in the list. Clicking on any one will load the style sheet into this very page. The code remains the same, the only thing that has changed is the external .css file. </p>
<!--下面是任务部分-->
<p class="text-right">给我加个类，我就向右对齐。</p>


</body>
</html>
  ```
###列表--简介
在HTML文档中，列表结构主要有三种：有序列表、无序列表和定义列表。具体使用的标签说明如下：
无序列表
```
<ul>
    <li>…</li>
</ul>
```
有序列表
```
<ol>
    <li>…</li>
</ol>
```
定义列表
```
<dl>
    <dt>…</dt>
    <dd>…</dd>
</dl>
```
Bootstrap根据平时的使用情形提供了六种形式的列表：

   ☑  普通列表

   ☑  有序列表

   ☑  去点列表

   ☑  内联列表

   ☑  描述列表

   ☑  水平描述列表
   举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>列表--简介</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<ul>
    <li>无序列表信息1</li>
    <li>无序列表信息2</li>
    <li>无序列表信息3</li>
</ul>
<ol>
    <li>有序列表信息1</li>
    <li>有序列表信息2</li>
    <li>有序列表信息3</li>
</ol>
<dl>
    <dt>定义列表标题</dt>
    <dd>定义列表信息1</dd>
    <dd>定义列表信息2</dd>
</dl>
</body>
</html>
```
###列表--去点列表
小伙伴们可以看到，在Bootstrap中默认情况下无序列表和有序列表是带有项目符号的，但在实际工作中很多时候，我们的列表是不需要这个编号的，比如说用无序列表做导航的时候。Bootstrap为众多开发者考虑的非常周道，通过给无序列表添加一个类名“.list-unstyled”,这样就可以去除默认的列表样式的风格。

.list-unstyled {
padding-left: 0;
list-style: none;
}
从示例中可以看出，除了项目编号之外，还将列表默认的左边内距也清０了。
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>去点列表</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<ul class="list-unstyled">
    <li>无序列表1</li>
    <li>无序列表2</li>
    <li>无序列表3</li>
</ul>
<ol class="list-unstyled">
    <li>有序列表1</li>
    <li>有序列表2</li>
    <li>有序列表3</li>
</ol>
</body>
</html>
```
###列表--内联列表
Bootstrap像去点列表一样，通过添加类名“.list-inline”来实现内联列表，简单点说就是把垂直列表换成水平列表，而且去掉项目符号（编号），保持水平显示。也可以说内联列表就是为制作水平导航而生。
源码：
```
.list-inline {
padding-left: 0;
margin-left: -5px;
list-style: none;
}
.list-inline > li {
display: inline-block;
padding-right: 5px;
padding-left: 5px;
}
```
举个例子
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>内联列表</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<ul class="list-inline">
    <li>W3cplus</li>
    <li>Blog</li>
    <li>CSS3</li>
    <li>jQuery</li>
    <li>PHP</li>
</ul>
<!--下面是代码任务部分-->
<p>城市：</p>
<ul class="list-inline">
    <li>北京</li>
    <li>上海</li>
    <li>南京</li>
    <li>厦门</li>
</ul>

</body>
</html>
```
###列表--水平定义列表
水平定义列表就像内联列表一样，Bootstrap可以给`<dl>`添加类名“.dl-horizontal”给定义列表实现水平显示效果。
```
@media (min-width: 768px) {
.dl-horizontal dt {
float: left;
width: 160px;
overflow: hidden;
clear: left;
text-align: right;
text-overflow: ellipsis;
white-space: nowrap;
  }
.dl-horizontal dd {
margin-left: 180px;
  }
}
```
此处添加了一个媒体查询。也就是说，只有屏幕大于768px的时候，添加类名“.dl-horizontal”才具有水平定义列表效果。其实现主要方式：
1、将dt设置了一个左浮动，并且设置了一个宽度为160px
2、将dd设置一个margin-left的值为180px，达到水平的效果
3、当标题宽度超过160px时，将会显示三个省略号
其用法如下：
```
<dl class="dl-horizontal">
    <dt>W3cplus</dt>
    <dd>一个致力于推广国内前端行业的技术博客。它以探索为己任，不断活跃在行业技术最前沿，努力提供高质量前端技术博文</dd>
    <dt>慕课网</dt>
    <dd>一个专业的，真心实意在做培训的网站</dd>
    <dt>我来测试一个标题，我来测试一个标题</dt>
    <dd>我在写一个水平定义列表的效果，我在写一个水平定义列表的效果</dd>
</dl>
```
宽屏下的效果（屏幕大于768px）：
![Alt text](http://img.mukewang.com/53ad0ff90001418208740117.jpg)
当你缩小你的浏览器屏幕时，水平定义列表将回复到原始的状态。
![Alt text](http://img.mukewang.com/53ad10270001db6f06200172.jpg)
###代码（一）
在Bootstrap主要提供了三种代码风格：
1、使用`<code></code>`来显示单行内联代码
2、使用`<pre></pre>`来显示多行块代码
3、使用`<kbd></kbd>`来显示用户输入代码
在使用代码时，用户可以根据具体的需求来使用不同的类型：
1、`<code>`：一般是针对于单个单词或单个句子的代码
2、`<pre>`：一般是针对于多行代码（也就是成块的代码）
3、`<kbd>`:一般是表示用户要通过键盘输入的内容

虽然不同的类型风格不一样，但其使用方法是类似的。
code风格：
```
<div>Bootstrap的代码风格有三种：
  <code>&lt;code&gt;</code>
  <code>&lt;pre&gt;</code>
  <code>&lt;kbd&gt;</code>
</div>
```
pre风格：
```
<div>
<pre>
&lt;ul&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;li&gt;...&lt;/li&gt;
&lt;/ul&gt;
</pre>
</div>
```
kbd风格：
```
<div>请输入<kbd>ctrl+c</kbd>来复制代码，然后使用<kbd>ctrl+v</kbd>来粘贴代码</div>
```
不管使用哪种代码风格，在代码中碰到小于号（<）要使用硬编码`“&lt;”`来替代，大于号(>)使用`“&gt;”`来替代。而且对于`<pre>`代码块风格，标签前面留多少个空格，在显示效果中就会留多少个空格。建议在编写HTML标签时，就控制好。
###代码（二）
正如前面所示，`<pre>`元素一般用于显示大块的代码，并保证原有格式不变。但有时候代码太多，而且不想让其占有太大的页面篇幅，就想控制代码块的大小。Bootstrap也考虑到这一点，你只需要在pre标签上添加类名“.pre-scrollable”，就可以控制代码块区域最大高度为340px，一旦超出这个高度，就会在Y轴出现滚动条。
源码如下：
```
.pre-scrollable {
max-height: 340px;
overflow-y: scroll;
}
```
举个例子：
```
<body>
高度超出340px，就会在Y轴出现滚动条
<!--下面是代码任务部分-->
<pre class="pre-scrollable">
<ol>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
    <li>....</li>
</ol>
</pre>
</body>
```
##表格
表格是Bootstrap的一个基础组件之一，Bootstrap为表格提供了1种基础样式和4种附加样式以及1个支持响应式的表格。在使用Bootstrap的表格过程中，只需要添加对应的类名就可以得到不同的表格风格，在接下来的内容中，我们会详细介绍Bootstrap的表格使用。

刚已经说了，Bootstrap为表格不同的样式风格提供了不同的类名，主要包括：

  ☑  .table：基础表格

  ☑  .table-striped：斑马线表格

  ☑  .table-bordered：带边框的表格

  ☑  .table-hover：鼠标悬停高亮的表格

  ☑  .table-condensed：紧凑型表格

  ☑  .table-responsive：响应式表格
  举个例子：
  ```
  <!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>基础表格</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<h1>基础表格</h1>
<table class="table">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
<h1>斑马线表格</h1>
<table class="table table-striped">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
<h1>带边框的表格</h1>
 <table class="table table-bordered">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
<h1>鼠标悬浮高亮的表格</h1>
<table class="table table-striped table-bordered table-hover">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
 <h1>紧凑型表格</h1>
  <table class="table table-condensed">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
 <h1>响应式表格</h1>
 <div class="table-responsive">
   <table class="table table-bordered">
   <thead>
     <tr>
       <th>表格标题</th>
       <th>表格标题</th>
       <th>表格标题</th>
     </tr>
   </thead>
   <tbody>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
     <tr>
       <td>表格单元格</td>
       <td>表格单元格</td>
       <td>表格单元格</td>
     </tr>
   </tbody>
 </table>
</div>
</body>
</html>
```
###表格--表格行的类
Bootstrap还为表格的行元素`<tr>`提供了五种不同的类名，每种类名控制了行的不同背景颜色，具体说明如下表所示：
![Alt text](http://img.mukewang.com/53ad213f0001b08807340508.jpg)
其使用非常的简单，只需要在`<tr>`元素中添加上表对应的类名，就能达到你自己需要的效果：
```
<tr class="active">
    <td>…</td>
</tr>
```
特别提示：除了”.active”之外，其他四个类名和”.table-hover”配合使用时，Bootstrap针对这几种样式也做了相应的悬浮状态的样式设置，所以如果需要给tr元素添加其他颜色样式时，在”.table-hover”表格中也要做相应的调整。

注意要实现悬浮状态，需要在`<table>`标签上加入table-hover类。

如下代码：
```
<table class="table-hover">
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>表格行的类</title>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>

<body>
<table class="table table-bordered">
  <thead>
    <tr>
      <th>类名</th>
      <th>描述</th>
    </tr>
  </thead>
  <tbody>
    <tr class="active">
      <td>.active</td>
      <td>表示当前活动的信息</td>
    </tr>
    <tr class="success">
      <td>.success</td>
      <td>表示成功或者正确的行为</td>
    </tr>
    <tr class="info">
      <td>.info</td>
      <td>表示中立的信息或行为</td>
    </tr>
    <tr class="warning">
      <td>.warning</td>
      <td>表示警告，需要特别注意</td>
    </tr>
    <tr class="danger">
      <td>.danger</td>
      <td>表示危险或者可能是错误的行为</td>
    </tr>
  </tbody>
</table> 
</body>
</html>
```
###表格--基础表格
大家对表格并不太陌生，但对于Bootstrap中的表格如何使用，或许还有点陌生，接下来的内容，将根据不同的表格类型向大家介绍Bootstrap表格的实际使用方法。
对表格的结构，跟我们平时使用表格是一样的：
```
<table>
<thead>
<tr>
<th>表格标题</th>
…
</tr>
</thead>
<tbody>
<tr>
<td>表格单元格</td>
…
</tr>
     …
</tbody>
</table>
```
如无特别声明，下面介绍表格类型的时候，结构都是类似上面的代码。
基础表格
在Bootstrap中，对于基础表格是通过类名“.table”来控制。如果在`<table>`元素中不添加任何类名，表格是无任何样式效果的。想得到基础表格，我们只需要在`<table>`元素上添加“.table”类名，就可以得到Bootstrap的基础表格：
```
<table class="table">
…
</table>
```
Bootstrap的基础表格，大致长得像下图所示的样子：
![Alt text](http://img.mukewang.com/53c617ea0001a48108560141.jpg)
“.table”主要有三个作用：

  ☑  给表格设置了margin-bottom:20px以及设置单元内距

  ☑  在thead底部设置了一个2px的浅灰实线

  ☑  每个单元格顶部设置了一个1px的浅灰实线
###表格--斑马线表格
有时候为了让表格更具阅读性，需要将表格制作成类似于斑马线的效果。简单点说就是让表格带有背景条纹效果。在Bootstrap中实现这种表格效果并不困难，只需要在`<table class="table">`的基础上增加类名“.table-striped”即可：
```
<table class="table table-striped">
…
</table>
```
其效果与基础表格相比，仅是在tbody隔行有一个浅灰色的背景色。其实现原理也非常的简单，利用CSS3的结构性选择器“:nth-child”来实现，所以对于IE8以及其以下浏览器，没有背景条纹效果。
效果如下所示：
![Alt text](http://img.mukewang.com/53c61d630001779e08680204.jpg)
###表格--带边框的表格
基础表格仅让表格部分地方有边框，但有时候需要整个表格具有边框效果。Bootstrap出于实际运用，也考虑这种表格效果，即所有单元格具有一条1px的边框。
Bootstrap中带边框的表格使用方法和斑马线表格的使用方法类似，只需要在基础表格`<table class="table">`基础上添加一个“.table-bordered”类名即可：
```
<table  class="table table-bordered">
  …
</table>
```
样式如下图所示：
![Alt text](http://img.mukewang.com/53c6218300019ab105870211.jpg)
###表格--鼠标悬浮高亮的表格
当鼠标悬停在表格的行上面有一个高亮的背景色，这样的表格让人看起来就是舒服，时刻告诉用户正在阅读表格哪一行的数据。Bootstrap的确没有让你失望，他也考虑到这种效果，其提供了一个“.table-hover”类名来实现这种表格效果。
鼠标悬停高亮的表格使用也简单，仅需要`<table class="table">`元素上添加类名“table-hover”即可：
```
<table class="table table-hover">
…
</table>
```
效果图如下：
![Alt text](http://img.mukewang.com/53c6224a0001ec1608570206.jpg)
从效果图中可以看出，当你鼠标悬浮在某一单元格上时，单元格所在行的背景色都会变成浅灰色。

鼠标悬浮高亮的效果主要是通过“hover”事件来实现，设置了“tr:hover”时的th、td的背景色为新颜色。
源码如下：
```
.table-hover > tbody > tr:hover > td,
.table-hover > tbody > tr:hover > th {
background-color: #f5f5f5;
}
```
注：其实，鼠标悬浮高亮表格，可以和Bootstrap其他表格混合使用。简单点说，只要你想让你的表格具备悬浮高亮效果，你只要给这个表格添加“table-hover”类名就好了。例如，将前面介绍的几种表格结合使用：
```
<table class="table table-striped table-bordered table-hover">
…
</table>
```
###表格--紧凑型表格
何谓紧凑型表格，简单理解，就是单元格没内距或者内距较其他表格的内距更小。换句话说，要实现紧凑型表格只需要重置表格单元格的内距padding的值。那么在Bootstrap中，通过类名“table-condensed”重置了单元格内距值。
紧凑型表格的运用，也只是需要在`<table class="table">`基础上添加类名“table-condensed”：
```
<table class="table table-condensed">
…
</table>
```
效果图如下：
![Alt text](http://img.mukewang.com/53c62647000158e708620159.jpg)
从上面效果图可以看出，Bootstrap中紧凑型的表格与基础表格差别不大，因为只是将单元格的内距由8px调至5px。

源码请看:
```
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
padding: 5px;
}
```
正如上一小节中悬浮高亮表格中所讲解的，在Bootstrap中制作表格中，可以将上面几种表格样式结合在一起使用，从而制作出更为精美的表格。结合的方法也很简单，就是在`<table class="table">`基础上添加你需要的表格样式类型。

另外从上面的示例中大家可能也发现了，不管制作哪种表格都离不开类名“table”。所以大家在使用Bootstrap表格时，千万注意，你的`<table>`元素中一定不能缺少类名“table”。
###表格--响应式表格
随着各种手持设备的出现，要想让你的Web页面适合千罗万像的设备浏览，响应式设计的呼声越来越高。在Bootstrap中也为表格提供了响应式的效果，将其称为响应式表格。
Bootstrap提供了一个容器，并且此容器设置类名“.table-responsive”,此容器就具有响应式效果，然后将`<table class="table">`置于这个容器当中，这样表格也就具有响应式效果。
Bootstrap中响应式表格效果表现为：当你的浏览器可视区域小于768px时，表格底部会出现水平滚动条。当你的浏览器可视区域大于768px时，表格底部水平滚动条就会消失。示例如下：
```
<div class="table-responsive">
<table class="table table-bordered">
   …
</table>
</div>
```
运行效果如下：
宽屏效果![Alt text](http://img.mukewang.com/53ad2eab0001c55105540130.jpg)
窄屏效果![Alt text](http://img.mukewang.com/53ad2f540001847402420197.jpg)
##基础表单
表单主要功能是用来与用户做交流的一个网页控件，良好的表单设计能够让网页与用户更好的沟通。表单中常见的元素主要包括：文本输入框、下拉选择框、单选按钮、复选按钮、文本域和按钮等。其中每个控件所起的作用都各不相同，而且不同的浏览器对表单控件渲染的风格都各有不同。

同样，表单也是Bootstrap框架中的核心内容，下面向大家介绍Bootstrap框架中表单的制作。
对于基础表单，Bootstrap并未对其做太多的定制性效果设计，仅仅对表单内的fieldset、legend、label标签进行了定制。如：
```
fieldset {
min-width: 0;
padding: 0;
margin: 0;
border: 0;
}
legend {
display: block;
width: 100%;
padding: 0;
margin-bottom: 20px;
font-size: 21px;
line-height: inherit;
color: #333;
border: 0;
border-bottom: 1px solid #e5e5e5;
}

label {
display: inline-block;
margin-bottom: 5px;
font-weight: bold;
}
```
主要将这些元素的margin、padding和border等进行了细化设置。

当然表单除了这几个元素之外，还有input、select、textarea等元素，在Bootstrap框架中，通过定制了一个类名`form-control`，也就是说，如果这几个元素使用了类名“form-control”，将会实现一些设计上的定制效果。

1、宽度变成了100%

2、设置了一个浅灰色（#ccc）的边框

3、具有4px的圆角

4、设置阴影效果，并且元素得到焦点之时，阴影和边框效果会有所变化

5、设置了placeholder的颜色为#999
举个例子：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	<title>基础表单</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<form role="form">
  <div class="form-group">
    <label for="exampleInputEmail1">邮箱：</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="请输入您的邮箱地址">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">密码</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="请输入您的邮箱密码">
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> 记住密码
    </label>
  </div>
  <button type="submit" class="btn btn-default">进入邮箱</button>
</form>	
</body>
</html>
```
###水平表单
Bootstrap框架默认的表单是垂直显示风格，但很多时候我们需要的水平表单风格（标签居左，表单控件居右）见下图。
![Alt text](http://img.mukewang.com/53d07cb5000111c403540091.jpg)
在Bootstrap框架中要实现水平表单效果，必须满足以下两个条件：
1、在`<form>`元素是使用类名“form-horizontal”。
2、配合Bootstrap框架的网格系统。（网格布局会在以后的章节中详细讲解）

在`<form>`元素上使用类名“form-horizontal”主要有以下几个作用：
1、设置表单控件padding和margin值。
2、改变“form-group”的表现形式，类似于网格系统的“row”。
举个例子：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	<title>水平表单</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<form class="form-horizontal" role="form">
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-2 control-label">邮箱</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail3" placeholder="请输入您的邮箱地址">
    </div>
  </div>
  <div class="form-group">
    <label for="inputPassword3" class="col-sm-2 control-label">密码</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword3" placeholder="请输入您的邮箱密码">
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <div class="checkbox">
        <label>
          <input type="checkbox"> 记住密码
        </label>
      </div>
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <button type="submit" class="btn btn-default">进入邮箱</button>
    </div>
  </div>
</form>
</body>
</html>
```
###内联表单
有时候我们需要将表单的控件都在一行内显示，类似这样的：
![Alt text](http://img.mukewang.com/53b2532a000107b003190032.jpg)
在Bootstrap框架中实现这样的表单效果是轻而易举的，你只需要在`<form>`元素中添加类名“form-inline”即可。
内联表单实现原理非常简单，欲将表单控件在一行显示，就需要将表单控件设置成内联块元素（display:inline-block）。
如果你要在input前面添加一个label标签时，会导致input换行显示。如果你必须添加这样的一个label标签，并且不想让input换行，你需要将label标签也放在容器“form-group”中，如：
```
<div class="form-group">
    <label class="sr-only" for="exampleInputEmail2">Email address</label>
</div>
<div class="form-group">
    <input type="email" class="form-control" id="exampleInputEmail2" placeholder="Enter email">
</div>
```
接下来，我们还是以实例说话：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	<title>内联表单</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<form class="form-inline" role="form">
  <div class="form-group">
    <label class="sr-only" for="exampleInputEmail2">邮箱</label>
    <input type="email" class="form-control" id="exampleInputEmail2" placeholder="请输入你的邮箱地址">
  </div>
  <div class="form-group">
    <label class="sr-only" for="exampleInputPassword2">密码</label>
    <input type="password" class="form-control" id="exampleInputPassword2" placeholder="请输入你的邮箱密码">
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> 记住密码
    </label>
  </div>
  <button type="submit" class="btn btn-default">进入邮箱</button>
</form>  
</body>
</html>
```
回过头来看示例，你或许会问，为什么添加了label标签，而且没有放置在”form-group”这样的容器中，input也不会换行；还有label标签怎么没显示出来。如果你仔细看，在label标签运用了一个类名“sr-only”，标签没显示就是这个样式将标签隐藏了。
注意：那么Bootstrap为什么要这么做呢？这样不是多此一举吗？其实不是的，如果没有为输入控件设置label标签，屏幕阅读器将无法正确识别。这也是Bootstrap框架另一个优点之处，为残障人员进行了一定的考虑。
