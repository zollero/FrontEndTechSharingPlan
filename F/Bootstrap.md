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
###表单控件(输入框input)
每一个表单都是由表单控件组成。离开了控件，表单就失去了意义。接下来的我们简单的来了解Bootstrap框架中表单控件的相关知识。

单行输入框，常见的文本输入框，也就是input的type属性值为text。在Bootstrap中使用input时也必须添加type类型，如果没有指定type类型，将无法得到正确的样式，因为Bootstrap框架都是通过input[type=“?”](其中?号代表type类型，比如说text类型，对应的是input[type=“text”])的形式来定义样式的。

为了让控件在各种表单风格中样式不出错，需要添加类名“form-control”，如：
```
<form role="form">
<div class="form-group">
<input type="email" class="form-control" placeholder="Enter email">
</div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b2571700018ab503070043.jpg)
###表单控件(下拉选择框select)
Bootstrap框架中的下拉选择框使用和原始的一致，多行选择设置multiple属性的值为multiple。Bootstrap框架会为这些元素提供统一的样式风格。如：
```
<form role="form">
<div class="form-group">
  <select class="form-control">
    <option>1</option>
    <option>2</option>
    <option>3</option>
    <option>4</option>
    <option>5</option>
  </select>
  </div>
  <div class="form-group">
  <select multiple class="form-control">
    <option>1</option>
    <option>2</option>
    <option>3</option>
    <option>4</option>
    <option>5</option>
  </select>
</div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b257ea000136bd02570072.jpg)
###表单控件(文本域textarea)
文本域和原始使用方法一样，设置rows可定义其高度，设置cols可以设置其宽度。但如果textarea元素中添加了类名“form-control”类名，则无需设置cols属性。因为Bootstrap框架中的“form-control”样式的表单控件宽度为100%或auto。
```
<form role="form">
  <div class="form-group">
    <textarea class="form-control" rows="3"></textarea>
  </div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b25d4d0001dbb503010055.jpg)
###表单控件(复选框checkbox和单选择按钮radio)
Bootstrap框架中checkbox和radio有点特殊，Bootstrap针对他们做了一些特殊化处理，主要是checkbox和radio与label标签配合使用会出现一些小问题（最头痛的是对齐问题）。使用Bootstrap框架，开发人员无需考虑太多，只需要按照下面的方法使用即可。
```
<form role="form">
<div class="checkbox">
<label>
<input type="checkbox" value="">
记住密码
</label>
</div>
<div class="radio">
<label>
<input type="radio" name="optionsRadios" id="optionsRadios1" value="love" checked>
喜欢
</label>
</div>
<div class="radio">
<label>
<input type="radio" name="optionsRadios" id="optionsRadios2" value="hate">
不喜欢
</label>
</div>
</form>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b25edb0001faae02520102.jpg)
从上面的示例，我们可以得知：
1、不管是checkbox还是radio都使用label包起来了
2、checkbox连同label标签放置在一个名为“.checkbox”的容器内
3、radio连同label标签放置在一个名为“.radio”的容器内
在Bootstrap框架中，主要借助“.checkbox”和“.radio”样式，来处理复选框、单选按钮与标签的对齐方式。
###表单控件(复选框和单选按钮水平排列)
有时候，为了布局的需要，将复选框和单选按钮需要水平排列。Bootstrap框架也做了这方面的考虑：
1、如果checkbox需要水平排列，只需要在label标签上添加类名“checkbox-inline”
2、如果radio需要水平排列，只需要在label标签上添加类名“radio-inline”
如下所示：
```
<form role="form">
  <div class="form-group">
    <label class="checkbox-inline">
      <input type="checkbox"  value="option1">游戏
    </label>
    <label class="checkbox-inline">
      <input type="checkbox"  value="option2">摄影
    </label>
    <label class="checkbox-inline">
    <input type="checkbox"  value="option3">旅游
    </label>
  </div>
  <div class="form-group">
    <label class="radio-inline">
      <input type="radio"  value="option1" name="sex">男性
    </label>
    <label class="radio-inline">
      <input type="radio"  value="option2" name="sex">女性
    </label>
    <label class="radio-inline">
      <input type="radio"  value="option3" name="sex">中性
    </label>
  </div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b2649f00011bae01920069.jpg)
###表单控件(按钮)
按钮也是表单重要控件之一,制作按钮通常使用下面代码来实现：

  ☑  input[type=“submit”]

  ☑  input[type=“button”]

  ☑  input[type=“reset”]

  ☑  <button>

在Bootstrap框架中的按钮都是采用`<button>`来实现。

有关于Bootstrap中按钮如何制作，在这里不做过多阐述，因为按钮也是Bootstrap框架中核心部分之一，后面我们专门有一节内容来介绍Bootstrap的按钮。

这里先让大家看看Bootstrap的按钮长成什么样：
![Alt text](http://img.mukewang.com/53b266f800010e4703160035.jpg)
举个例子：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>表单控件状态——焦点状态</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<table class="table table-bordered table-striped">  
    <thead>  
      <tr>  
        <th>Button</th>  
        <th>class=""</th>  
        <th>Description</th>  
      </tr>  
    </thead>  
    <tbody>  
      <tr>  
        <td><button class="btn" href="#">Default</button></td>  
        <td><code>btn</code></td>  
        <td>Standard gray button with gradient</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-primary" href="#">Primary</button></td>  
        <td><code>btn btn-primary</code></td>  
        <td>Provides extra visual weight and identifies the primary action in a set of buttons</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-info" href="#">Info</button></td>  
        <td><code>btn btn-info</code></td>  
        <td>Used as an alternative to the default styles</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-success" href="#">Success</button></td>  
        <td><code>btn btn-success</code></td>  
        <td>Indicates a successful or positive action</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-warning" href="#">Warning</button></td>  
        <td><code>btn btn-warning</code></td>  
        <td>Indicates caution should be taken with this action</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-danger" href="#">Danger</button></td>  
        <td><code>btn btn-danger</code></td>  
        <td>Indicates a dangerous or potentially negative action</td>  
      </tr>  
      <tr>  
        <td><button class="btn btn-inverse" href="#">Inverse</button></td>  
        <td><code>btn btn-inverse</code></td>  
        <td>Alternate dark gray button, not tied to a semantic action or use</td>  
      </tr>  
    </tbody>  
  </table>    
</body>
</html>
```
###表单控件大小
前面看到的表单控件都正常的大小。可以通过设置控件的height，line-height，padding和font-size等属性来实现控件的高度设置。不过Bootstrap框架还提供了两个不同的类名，用来控制表单控件的高度。这两个类名是：
1、input-sm:让控件比正常大小更小
2、input-lg:让控件比正常大小更大

这两个类适用于表单中的input，textarea和select控件，具体使用如下：
```
<input class="form-control input-lg" type="text" placeholder="添加.input-lg，控件变大">
<input class="form-control" type="text" placeholder="正常大小">
<input class="form-control input-sm" type="text" placeholder="添加.input-sm，控件变小">
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b269860001e43f02260101.jpg)
不管是“input-sm”还是“input-lg”仅对控件高度做了处理。但往往很多时候，我们需要控件宽度也要做一定的变化处理。这个时候就要借住Bootstrap框架的网格系统。所以你要控制表单宽度，可以像下面这样使用：
```
<form role="form" class="form-horizontal">
  <div class="form-group">
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  </div>
    …
</form>
```
注：网格布局在后面章节中会进行详细讲解。

运行效果如下:
![Alt text](http://img.mukewang.com/53b26a6a00018cba02420078.jpg)
前面介绍水平表单时说过，如果表单使用了类名“form-horizontal”，其中“form-group”就相当于网格系统中的“row”。换句话说，如果没有这样做，要通过网格系统来控制表单控件宽度，就需要这样使用：
```
<div class="row">
<div class="col-xs-4">
<input class="form-control input-lg" type="text" placeholder=".col-xs-4">
</div>
<div class="col-xs-4">
<input class="form-control input-lg" type="text" placeholder=".col-xs-4">
</div>
<div class="col-xs-4">
<input class="form-control input-lg" type="text" placeholder=".col-xs-4">
</div>
</div>
```
###表单控件状态(焦点状态)
表单主要用来与用户沟通，好的表单就能更好的与用户进行沟通，而好的表单一定离不开表单的控件状态。

表单状态的作用：

每一种状态都能给用户传递不同的信息，比如表单有焦点的状态可以告诉用户可以输入或选择东西，禁用状态可以告诉用户不可以输入或选择东西，还有就是表单控件验证状态，可以告诉用户的操作是否正确等。那么在Bootstrap框架中的表单控件也具备这些状态。

焦点状态是通过伪类“:focus”来实现。Bootstrap框架中表单控件的焦点状态删除了outline的默认样式，重新添加阴影效果。
要让控件在焦点状态下有样式效果，需要给控件添加类名“form-control”：
```
<form role="form" class="form-horizontal">
  <div class="form-group">
    <div class="col-xs-6">
      <input class="form-control input-lg" type="text" placeholder="不是焦点状态下效果">
    </div>
    <div class="col-xs-6">
      <input class="form-control input-lg" type="text" placeholder="焦点点状态下效果">
    </div>
  </div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b271e700018f8a02780042.jpg)
（鼠标单击输入框，使其获得焦点就可以看到加入蓝色边框效果）
在Bootstrap框架中，file、radio和checkbox控件在焦点状态下的效果也与普通的input控件不太一样，主要是因为Bootstrap对他们做了一些特殊处理。
###表单控件状态(禁用状态)
Bootstrap框架的表单控件的禁用状态和普通的表单禁用状态实现方法是一样的，在相应的表单控件上添加属性“disabled”。和其他表单的禁用状态不同的是，Bootstrap框架做了一些样式风格的处理：
源码如下：
```
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
cursor: not-allowed;
background-color: #eee;
opacity: 1;
}
```
使用方法为：只需要在需要禁用的表单控件上加上“disabled”即可：
```
<input class="form-control" type="text" placeholder="表单已禁用，不能输入" disabled>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b27abf00013e5f03360048.jpg)
在使用了“form-control”的表单控件中，样式设置了禁用表单背景色为灰色，而且手型变成了不准输入的形状。如果控件中不使用类名“form-control”，禁用的控件只会有一个不准输入的手型出来。
在Bootstrap框架中，如果fieldset设置了disabled属性，整个域都将处于被禁用状态。
```
<form role="form">
<fieldset disabled>
  <div class="form-group">
  <label for="disabledTextInput">禁用的输入框</label>
    <input type="text" id="disabledTextInput" class="form-control" placeholder="禁止输入">
  </div>
  <div class="form-group">
  <label for="disabledSelect">禁用的下拉框</label>
    <select id="disabledSelect" class="form-control">
  	<option>不可选择</option>
    </select>
  </div>
  <div class="checkbox">
  <label>
    <input type="checkbox">无法选择
  </label>
  </div>
  <button type="submit" class="btnbtn-primary">提交</button>
</fieldset>
</form>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b27b2200010df702890118.jpg)
据说对于整个禁用的域中，如果legend中有输入框的话，这个输入框是无法被禁用的。我们一起来验证一下：
```
<form role="form">
<fieldset disabled>
<legend><input type="text" class="form-control" placeholder="显然我颜色变灰了，但是我没被禁用，不信？单击试一下" /></legend>
    …
</fieldset>
</form>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b27bc30001113302720144.jpg)
###表单控件状态(验证状态)
在制作表单时，不免要做表单验证。同样也需要提供验证状态样式，在Bootstrap框架中同样提供这几种效果。
1、.has-warning:警告状态（黄色）
2、.has-error：错误状态（红色）
3、.has-success：成功状态（绿色）
使用的时候只需要在form-group容器上对应添加状态类名。
```
<form role="form">
<div class="form-group has-success">
  <label class="control-label" for="inputSuccess1">成功状态</label>
  <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态" >
</div>
<div class="form-group has-warning">
  <label class="control-label" for="inputWarning1">警告状态</label>
  <input type="text" class="form-control" id="inputWarning1" placeholder="警告状态">
</div>
<div class="form-group has-error">
  <label class="control-label" for="inputError1">错误状态</label>
  <input type="text" class="form-control" id="inputError1" placeholder="错误状态">
</div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b27e170001133702870115.jpg)
从效果可以看出，三种状态下效果都是一样的，只是颜色不一样而以。

其他两种状态省略源码不在此展示。
很多时候，在表单验证的时候，不同的状态会提供不同的 icon，比如成功是一个对号（√），错误是一个叉号（×）等。在Bootstrap框中也提供了这样的效果。如果你想让表单在对应的状态下显示 icon 出来，只需要在对应的状态下添加类名“has-feedback”。请注意，此类名要与“has-error”、“has-warning”和“has-success”在一起：
```
<form role="form">
<div class="form-group has-success has-feedback">
  <label class="control-label" for="inputSuccess1">成功状态</label>
  <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态" >
  <span class="glyphiconglyphicon-ok form-control-feedback"></span>
</div>
<div class="form-group has-warning has-feedback">
  ......
</div>
<div class="form-group has-error has-feedback">
  ......
</div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b27e8600013fdf02910117.jpg)
从效果图中可以看出，图标都居右。在 Bootstrap 的小图标都是使用@font-face来制作（后面的内容中将会着重用一节内容来介绍）。而且必须在表单中添加了一个 span 元素：
```
<span class="glyphiconglyphicon-warning-sign form-control-feedback"></span>
```
###表单提示信息
平常在制作表单验证时，要提供不同的提示信息。在Bootstrap框架中也提供了这样的效果。使用了一个"help-block"样式，将提示信息以块状显示，并且显示在控件底部。
```
<form role="form">
<div class="form-group has-success has-feedback">
  <label class="control-label" for="inputSuccess1">成功状态</label>
  <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态" >
  <span class="help-block">你输入的信息是正确的</span>
  <span class="glyphiconglyphicon-ok form-control-feedback"></span>
</div>
  …
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b2829200018aaf02180116.jpg)
具体样式代码如下：
```
.help-block {
display: block;
margin-top: 5px;
margin-bottom: 10px;
color: #737373;
}
```
在Bootstrap V2.x版本中还提供了一个行内提示信息，其使用了类名“help-inline”。一般让提示信息显示在控件的后面，也就是同一水平显示。如果你想在BootstrapV3.x版本也有这样的效果，你可以添加这段代码：
```
.help-inline{
  display:inline-block;
  padding-left:5px;
  color: #737373;
}
```
如果你不想为bootstrap.css增加自己的代码，而且设计又有这种样的需求，那么只能借助于Bootstrap的网格系统。(网格系统在后面的章节中会详细讲解)
```
<form role="form">
<div class="form-group">
<label class="control-label" for="inputSuccess1">成功状态</label>
<div class="row">
<div class="col-xs-6">
<input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态" >
</div>
<span class="col-xs-6 help-block">你输入的信息是正确的</span>
</div>
</div>
</form>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b283010001402902670049.jpg)
结束语：有关于Bootstrap框架中表单的运用除了按钮部分，到此就算是介绍完了。如果你觉得这样的表单效果并不是你需要的，你完全可以通过forms.less或者_forms.scss文件进行定制，然后重新编译就可以得到你需要的表单效果。在接下来的一节中，我们Bootstrap框架中另一个核心内容——按钮。
##按钮
按钮也是Bootstrap框架核心内容之一。因为按钮是Web制作中不可缺少的东西。而且不同的Web页面具有不同的按钮风格，甚至说同一个Web网站或应用程序具有多种按钮风格，比如说不同的按钮颜色、大小和状态等。那么Bootstrap框架也考虑了这些因素，接下来的内容我们一起来探讨Bootstrap框架中的另一核心部分内容——按钮。
举个例子：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>定制风格</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
   <button class="btn" type="button">基础按钮.btn</button>  
   <button class="btn btn-default" type="button">默认按钮.btn-default</button> 
   <button class="btn btn-primary" type="button">主要按钮.btn-primary</button> 
   <button class="btn btn-success" type="button">成功按钮.btn-success</button> 
   <button class="btn btn-info" type="button">信息按钮.btn-info</button> 
   <button class="btn btn-warning" type="button">警告按钮.btn-warning</button> 
   <button class="btn btn-danger" type="button">危险按钮.btn-danger</button> 
   <button class="btn btn-link" type="button">链接按钮.btn-link</button> 
</body>
</html>
```
###基本按钮
Bootstrap框架V3.x版本的基本按钮和V2.x版本的基本按钮一样，都是通过类名“btn”来实现。不同的是在V3.x版本要简约很多，去除了V2.x版本中的大量的CSS3中的部分特效，比如说文本阴影（text-shadow）、渐变背景（background-image）、边框阴影（box-shadow）等。
难能可贵的是，Bootstrap框架中的考虑了不同浏览器的解析差异，进行了比较安全的兼容性处理，使按钮效果在不同的浏览器中所呈现的效果基本相同。
Bootstrap框架的按钮使用非常的简单，使用方式如下：
```
<button class="btn" type="button">我是一个基本按钮</button>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b28609000143a602800084.jpg)
###默认按钮
Bootstrap框架首先通过基础类名“.btn”定义了一个基础的按钮风格，然后通过“.btn-default”定义了一个默认的按钮风格。默认按钮的风格就是在基础按钮的风格的基础上修改了按钮的背景颜色、边框颜色和文本颜色。
源码:
```
.btn-default {
color: #333;
background-color: #fff;
border-color: #ccc;
}
```
使用默认按钮风格也非常的简单，只需要在基础按钮“btn”的基础上增加类名“btn-default”即可：
```
<button class="btn btn-default" type="button">默认按钮</button>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b287170001023501820104.jpg)
###多标签支持
一般制作按钮除了使用`<button>`标签元素之外，还可以使用`<input type="submit">`和`<a>`标签等。同样，在Bootstrap框架中制作按钮时，除了刚才所说的这些标签元素之外，还可以使用在其他的标签元素上，唯一需要注意的是，要在制作按钮的标签元素上添加类名“btn”。如果不添加是不会有任何按钮效果。

我们一起来看看其他标签制作的基本按钮效果：
```
<button class="btn btn-default" type="button">button标签按钮</button>
<input type="submit" class="btn btn-default" value="input标签按钮"/>
<a href="##" class="btn btn-default">a标签按钮</a>
<span class="btn btn-default">span标签按钮</span>
<div class="btn btn-default">div标签按钮</div>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b287f800014bc402460068.jpg)
注意：虽然在Bootstrap框架中使用任何标签元素都可以实现按钮风格，但个人并不建议这样使用，为了避免浏览器兼容性问题，个人强烈建议使用button或a标签来制作按钮。
###定制风格
在介绍按钮开篇就说过，Web页面可能会有不同的按钮风格。那么在Bootstrap框架也考虑了。在Bootstrap框架中除了默认的按钮风格之外，还有其他六种按钮风格，每种风格的其实都一样，不同之处就是按钮的背景颜色、边框颜色和文本颜色。

在Bootstrap框架中不同的按钮风格都是通过不同的类名来实现，在使用过程中，开发者只需要选择不同的类名即可：
![Alt text](http://img.mukewang.com/53b367bd0001d59c07530312.jpg)
![Alt text](http://img.mukewang.com/53b367d10001846a08020810.jpg)
使用起来就很简单，就像前面介绍的默认按钮一样的使用方法，只需要在基础按钮“.btn”基础上追加对应的类名，就可以得到需要的按钮风格。如：
```
<button class="btn" type="button">基础按钮.btn</button>
<button class="btn btn-default" type="button">默认按钮.btn-default</button>
<button class="btn btn-primary" type="button">主要按钮.btn-primary</button>
<button class="btn btn-success" type="button">成功按钮.btn-success</button>
<button class="btn btn-info" type="button">信息按钮.btn-info</button>
<button class="btn btn-warning" type="button">警告按钮.btn-warning</button>
<button class="btn btn-danger" type="button">危险按钮.btn-danger</button>
<button class="btn btn-link" type="button">链接按钮.btn-link</button>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b368510001fe2701800274.jpg)
###按钮大小
上一节介绍了按钮的定制风格，也就是如何实现Web页面中多种风格按钮。在Bootstrap框架中，对于按钮的大小，也是可以定制的。类似于input一样，通过在基础按钮“.btn”的基础上追加类名来控制按钮的大小。

在Bootstrap框架中提供了三个类名来控制按钮大小：
![Alt text](http://img.mukewang.com/53b36a7600014af106910605.jpg)
从上表中不难发现，在Bootstrap框架中控制按钮的大小都是通过修改按钮的padding、line-height、font-size和border-radius几个属性。
那么在实际使用中，这几个类名可以配合按钮中其他颜色类名一起使用，但唯一一点不能缺少“.btn”类名：
```
<button class="btn btn-primary btn-lg" type="button">大型按钮.btn-lg</button>
<button class="btn btn-primary" type="button">正常按钮</button>
<button class="btn btn-primary btn-sm" type="button">小型按钮.btn-sm</button>
<button class="btn btn-primary btn-xs" type="button">超小型按钮.btn-xs</button>
```
效果如下图:
![Alt text](http://img.mukewang.com/53b36b220001f92302370097.jpg)
###块状按钮
从前面几节的内容中，大家可能发现了，每个示例中的按钮宽度都是依靠按钮文本和padding的值来决定。但有时候在制作按钮的时候需要按钮宽度充满整个父容器（width:100%），特别是在移动端的制作中。那么前面的方法我们都无法很好的实现，除非重新定义按钮的宽度。其实在Bootstrap中并不需要这样做，Bootstrap框架中提供了一个类名“btn-block”。按钮使用这个类名就可以让按钮充满整个容器，并且这个按钮不会有任何的padding和margin值。在实际当中，常把这种按钮称为块状按钮。
使用方法和前面的类似，只需要在原按钮类名上添加“.btn-block”类名，当然“.btn”类名是不可或缺的：
```
<button class="btn btn-primary btn-lg btn-block" type="button">大型按钮.btn-lg</button>
<button class="btn btn-primary btn-block" type="button">正常按钮</button>
<button class="btn btn-primary btn-sm btn-block" type="button">小型按钮.btn-sm</button>
<button class="btn btn-primary btn-xs btn-block" type="button">超小型按钮.btn-xs</button>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53b36c2b000130f202260110.jpg)
###按钮状态——活动状态
Bootstrap框架针对按钮的状态做了一些特殊处理。在Bootstrap框架中针对按钮的状态效果主要分为两种：活动状态和禁用状态。

Bootstrap按钮的活动状态主要包括按钮的悬浮状态(:hover)，点击状态(:active)和焦点状态（:focus）几种。
而且不同风格下的按钮都具有这几种状态效果，只是颜色做了一定的调整，我们以默认风格（btn-default）为例：
源码:
```
.btn-default:hover,
.btn-default:focus,
.btn-default:active,
.btn-default.active,
.open .dropdown-toggle.btn-default {
color: #333;
background-color: #ebebeb;
border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open .dropdown-toggle.btn-default {
background-image: none;
}
```
当按钮处理正在点击状态（也就是鼠标按下的未松开的状态），对于`<button>`元素是通过“:active”伪类实现，而对于`<a>`这样的标签元素则是通过添加类名“.active”来实现。
观察按钮悬浮状态、点击状态和焦点状态的样式变化。
###按钮状态——禁用状态
和input等表单控件一样，在Bootstrap框架的按钮中也具有禁用状态的设置。禁用状态与其他状态按钮相比，就是背景颜色的透明度做了一定的处理，opcity的值从100%调整为65%。

在Bootstrap框架中，要禁用按钮有两种实现方式：

方法1：在标签中添加disabled属性

方法2：在元素标签中添加类名“disabled”

两者的主要区别是：
“.disabled”样式不会禁止按钮的默认行为，比如说提交和重置行为等。如果想要让这样的禁用按钮也能禁止按钮的默认行为，则需要通过JavaScript这样的语言来处理。对于`<a>`标签也存在类似问题，如果通过类名“.disable”来禁用按钮，其链接行为是无法禁止。而在元素标签中添加“disabled”属性的方法是可以禁止元素的默认行为的。

下面是两种方法的举例：
```
<button class="btn btn-primary btn-lg btn-block" type="button" disabled="disabled">通过disabled属性禁用按钮</button>
<button class="btn btn-primary btn-block disabled" type="button">通过添加类名disabled禁用按钮</button>
<button class="btn btn-primary btn-sm btn-block" type="button">未禁用的按钮</button>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b36e9d0001132e02690107.jpg)
到此有关于按钮的基础知识就算是介绍完了，同样的，大家可以通过buttons.less或者_buttons.scss来自定义按钮风格。
###图像
图像在网页制作中也是常要用到的元素，在Bootstrap框架中对于图像的样式风格提供以下几种风格：

1、img-responsive：响应式图片，主要针对于响应式设计
2、img-rounded：圆角图片
3、img-circle：圆形图片
4、img-thumbnail：缩略图片

使用方法：

使用方法非常简单，只需要在<img>标签上添加对应的类名，如下代码：
```
<img  alt="140x140" src="http://placehold.it/140x140">
<img  class="img-rounded" alt="140x140" src="http://placehold.it/140x140">
<img  class="img-circle" alt="140x140" src="http://placehold.it/140x140">
<img  class="img-thumbnail" alt="140x140" src="http://placehold.it/140x140">
<img  class="img-responsive" alt="140x140" src="http://placehold.it/140x140">
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b36fc300017b1e02980139.jpg)
设置图片大小：

由于样式没有对图片做大小上的样式限制，所以在实际使用的时候，需要通过其他的方式来处理图片大小。比如说控制图片容器大小。（注意不可以通过css样式直接修改img图片的大小，这样操作就不响应了）

注意：

对于圆角图片和圆形图片效果，因为是使用了CSS3的圆角样式来实现的，所以注意对于IE8以及其以下版本不支持，是没有圆角效果的。

Bootstrap框架为了大家更好的维护图像的样式，同样将这部分样式独立出来：
1、LESS版本，可以查阅scaffolding.less
2、Sass版本，可以查阅_scaffolding.scss
大家可以修改其中之一，重新编译就可以得到自己需要的图片样式效果。
举个例子：
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	<title>图像</title>
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
  <div class="row">
    <div class="col-sm-4">
      <img   alt="140x140" src="http://placehold.it/140x140">
        <div>默认图片</div>
    </div>
    <div class="col-sm-4">
      <img  class="img-rounded" alt="140x140" src="http://placehold.it/140x140"> 
        <div>圆角图片</div>
    </div>
    <div class="col-sm-4">
      <img  class="img-circle" alt="140x140" src="http://placehold.it/140x140">
        <div>圆形图片</div>
    </div>
      <div class="row">
        <div class="col-sm-6">
          <img  class="img-thumbnail" alt="140x140" src="http://placehold.it/140x140"> 
            <div>缩略图</div>
        </div>
        <div class="col-sm-6">
          <img  class="img-responsive" alt="140x140" src="http://placehold.it/140x140" /> 
          <div>响应式图片</div>
        </div>
      </div>
  </div>
</div> 
</body>
</html>
```
###图标（一）
200个icon：

这里说的图标就是Web制作中常看到的小icon图标，可以说这些小icon图标是一个优秀Web中不可缺少的一部分，起到画龙点睛的效果。在Bootstrap框架中也为大家提供了近200个不同的icon图片，而这些图标都是使用CSS3的@font-face属性配合字体来实现的icon效果。
![Alt text](http://img.mukewang.com/53db0e5b0001aff810560855.jpg)
放心使用：

在具体介绍Bootstrap的icon图标之前，我们首先要感谢glyphicons.com网站，因为Bootstrap框架中图标都是glyphicons.com这个商业网站提供的，并且免费授权给Bootstrap框架使用，所以大家可以放心使用在自己的项目当中。

Bootstrap框架将内部样式也提取出来：
1、LESS版本：对应源文件为glyphicons.less文件
2、Sass版本：对应源文件为_glyphicons.scss文件
原理分析：

Bootstrap框架中的图标都是字体图标，其实现原理就是通过@font-face属性加载了字体。
源码:
```
@font-face {
font-family: 'Glyphicons Halflings';
src: url('../fonts/glyphicons-halflings-regular.eot');
src: url('../fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../fonts/glyphicons-halflings-regular.woff') format('woff'), url('../fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
```
大家或许会问，这些字体我去哪里获取。如果你是从前面一直阅读过来，我们在介绍文件结构那一节就已介绍过。在Bootstrap框架中有一个fonts的目录，这个目录中提供的字体文件就是用于制作icon的字体文件。
自定义完字体之后，需要对icon设置一个默认样式，在Bootstrap框架中是通过给元素添加“glyphicon”类名来实现，然后通过伪元素“:before”的“content”属性调取对应的icon编码.
###图标（二）
在网页中使用图标也非常的简单，在任何内联元素上应用所对应的样式即可：
```
<span class="glyphicon glyphicon-search"></span>
<span class="glyphicon glyphicon-asterisk"></span>
<span class="glyphicon glyphicon-plus"></span>
<span class="glyphicon glyphicon-cloud"></span>
```
运行效果如下:
![Alt text](http://img.mukewang.com/53b371270001aff102680096.jpg)
所有icon都是以”glyphicon-”前缀的类名开始，然后后缀表示图标的名称。具体说明如下：
![Alt text](http://img.mukewang.com/53da0a7e0001300509180435.jpg)
所有名称查看：

请点击：http://getbootstrap.com/components/#glyphicons 链接查阅
特别说明：

除了使用glyphicon.com提供的图标之外，还可以使用第三方为Bootstrap框架设计的图标字体，如Font Awesome(http://www.bootcss.com/p/font-awesome/)。使用方法和上面介绍的一样，不过记得将字体下载到你本地。 感兴趣的可以阅读官网相关介绍。

#网格系统
###实现原理
网格系统的实现原理非常简单，仅仅是通过定义容器大小，平分12份(也有平分成24份或32份，但12份是最常见的)，再调整内外边距，最后结合媒体查询，就制作出了强大的响应式网格系统。Bootstrap框架中的网格系统就是将容器平分成12份。

在使用的时候大家可以根据实际情况重新编译LESS（或Sass）源码来修改12这个数值（也就是换成24或32，当然你也可以分成更多，但不建议这样使用）。
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>实现原理</title>
<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
<link rel="stylesheet" href="style.css">
</head>

<body>
<div class="container">
  <div class="row">
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
  </div>
  <div class="row">
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
  </div>
    <div class="row">
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
    <div class="col-md-1">.col-md-1</div>
  </div>
</div>
</body>
</html>
```
###工作原理
Bootstrap框架的网格系统工作原理如下：

1、数据行(.row)必须包含在容器（.container）中，以便为其赋予合适的对齐方式和内距(padding)。如：
```
<div class="container">
<div class="row"></div>
</div>
```
2、在行(.row)中可以添加列(.column)，但列数之和不能超过平分的总列数，比如12。如：
```
<div class="container">
<div class="row">
  <div class="col-md-4"></div>
  <div class="col-md-8"></div>
</div>
</div>
```
3、具体内容应当放置在列容器（column）之内，而且只有列（column）才可以作为行容器(.row)的直接子元素
4、通过设置内距（padding）从而创建列与列之间的间距。然后通过为第一列和最后一列设置负值的外距（margin）来抵消内距(padding)的影响

为了更好的理解Bootstrap框架的网格系统工作原理，我们来看一张草图：
![Alt text](http://img.mukewang.com/53b0f9c000018b9305540282.jpg)
简单对图解释一下：

1、最外边框，带有一大片白色区域，就是相当于浏览器的可视区域。在Bootstrap框架的网格系统中带有响应式效果，其带有四种类型的浏览器（超小屏，小屏，中屏和大屏），其断点（像素的分界点）是768px、992px和1220px。

2、第二个边框(1)相当于容器(.container)。针对不同的浏览器分辨率，其宽度也不一样：自动、750px、970px和1170px。在bootstrap.css的第736行～第756行进行设置：
源码：
```
.container {
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
  @media (min-width: 768px) {
  .container {
    width: 750px;
  }
  @media (min-width: 992px) {
  .container {
    width: 970px;
  }
  @media (min-width: 1200px) {
  .container {
    width: 1170px;
  }
  ```
  3、２号横条阐述的是，将容器的行（.row）平分了12等份，也就是列。每个列都有一个“padding-left:15px”(图中粉红色部分)和一个“padding-right:15px”(图中紫色部分)。这样也导致了第一个列的padding-left和最后一列的padding-right占据了总宽度的30px，从而致使页面不美观，当然，如果你需要留有一定的间距，这个做法是不错的。
源码：
```
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-right: 15px;
  padding-left: 15px;
}
```
4、３号横条就是行容器(.row),其定义了“margin-left”和”margin-right”值为”-15px”，用来抵消第一个列的左内距和最后一列的右内距。
源码：
```
.row {
  margin-right: -15px;
  margin-left: -15px;
}
```
5、将行与列给合在一起就能看到横条4的效果。也就是我们期望看到的效果，第一列和最后一列与容器（.container）之间没有间距。

横条５只是想向大家展示，你可以根据需要，任意组合列与列，只是他们的组合数之和不要超过总列数。
注：如果每行网格数超过12会换行
###基本用法
网格系统用来布局，其实就是列的组合。Bootstrap框架的网格系统中有四种基本的用法。由于Bootstrap框架在不同屏幕尺寸使用了不同的网格样式，在这一节中所涉及到的示例，我们都以中屏（970px）为例进行介绍，其他屏幕的使用也类似这一种。关于屏幕尺寸如下图：
![Alt text](http://img.mukewang.com/53e483500001c7f408770494.jpg)
1、列组合

列组合简单理解就是更改数字来合并列（原则：列总和数不能超12），有点类似于表格的colspan属性，例如：
```
<div class="container">
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-8">.col-md-8</div>
  </div>
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4">.col-md-4</div>
  </div>
  <div class="row">
    <div class="col-md-3">.col-md-3</div>
    <div class="col-md-6">.col-md-6</div>
    <div class="col-md-3">.col-md-3</div>
 </div>
</div>
```
使用上面的结构，你将看到下图的效果：
![Alt text](http://img.mukewang.com/53b0fbdc00015f2805540051.jpg)
实现列组合方式非常简单，只涉及两个CSS两个特性：浮动与宽度百分比。
确保所有列左浮动:
```
.col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
 }
```
定义每个列组合的宽度（使用的百分比）:
```
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
```
###列偏移
有的时候，我们不希望相邻的两个列紧靠在一起，但又不想使用margin或者其他的技术手段来。这个时候就可以使用列偏移（offset）功能来实现。使用列偏移也非常简单，只需要在列元素上添加类名“col-md-offset-*”(其中星号代表要偏移的列组合数)，那么具有这个类名的列就会向右偏移。例如，你在列元素上添加“col-md-offset-4”，表示该列向右移动4个列的宽度。
```
<div class="container">
<div class="row">
<div class="col-md-4">.col-md-4</div>
<div class="col-md-2 col-md-offset-4">列向右移动四列的间距</div>
<div class="col-md-2">.col-md-3</div>
</div>
<div class="row">
<div class="col-md-4">.col-md-4</div>
<div class="col-md-4 col-md-offset-4">列向右移动四列的间距</div>
</div>
</div>
```
上面的示例代码，得到的效果如下:
![Alt text](http://img.mukewang.com/53b0fe8d00018ca605530045.jpg)
实现原理非常简单，就是利用十二分之一（1/12）的margin-left。然后有多少个offset，就有多少个margin-left。在bootstrap.css中第1205行～1241行所示：
```
  .col-md-offset-12 {
   margin-left: 100%;
}
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0;
  }
```
  注意：

不过有一个细节需要注意，使用”col-md-offset-*”对列进行向右偏移时，要保证列与偏移列的总数不超过12，不然会致列断行显示，如：
```
<div class="row">
  <div class="col-md-3">.col-md-3</div>
  <div class="col-md-3 col-md-offset-3">col-md-offset-3</div>
  <div class="col-md-4">col-md-4</div>
</div>
```
上面代码中列和偏移列总数为3+3+3+4 = 13>12，所以发生了列断行。
如上面的示例代码，得到的效果如下:
![Alt text](http://img.mukewang.com/53b0ff3f00015e2f05530050.jpg)
###列排序
列排序其实就是改变列的方向，就是改变左右浮动，并且设置浮动的距离。在Bootstrap框架的网格系统中是通过添加类名“col-md-push-*”和“col-md-pull-*” (其中星号代表移动的列组合数)。

我们来看一个简单的示例：
```
<div class="container">
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-8">.col-md-8</div>
  </div>
</div>
```
默认情况之下，上面的代码效果如下：
![Alt text](http://img.mukewang.com/53b10a400001af8005540037.jpg)
“col-md-4”居左，“col-md-8”居右，如果要互换位置，需要将“col-md-4”向右移动８个列的距离，也就是8个offset ,也就是在“`<div class=“col-md-4”>`”添加类名“col-md-push-8”，调用其样式。
![Alt text](http://img.mukewang.com/53b10a79000152b805540042.jpg)
也要将“col-md-8”向左移动４个列的距离，也就是4个offset，在“<div class=”col-md-8”>”上添加类名“col-md-pull-4”：
![Alt text](http://img.mukewang.com/53b10aa80001687005530038.jpg)
Bootstrap仅通过设置left和right来实现定位效果。在boostrap.css文件的第1127行~第1204行可以看到具体的代码：
```
.col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }

  .col-md-pull-4 {
    right: 33.33333333%;
  }

  .col-md-pull-3 {
    right: 25%;
  }

  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: 0;
  }

  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: 0;
  }
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>列排序</title>
<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
<link rel="stylesheet" href="common.css">
</head>

<body>
<div class="container">
    <div class="row">
        <div class="col-xs-4">.col-xs-4</div>
        <div class="col-xs-8">.col-xs-8</div>
    </div>
</div>
</body>
</html>
```
###列的嵌套
Bootstrap框架的网格系统还支持列的嵌套。你可以在一个列中添加一个或者多个行（row）容器，然后在这个行容器中插入列（像前面介绍的一样使用列）。但在列容器中的行容器（row），宽度为100%时，就是当前外部列的宽度。来看一个简单示例：
```
<div class="container">
    <div class="row">
        <div class="col-md-8">
        我的里面嵌套了一个网格
            <div class="row">
            <div class="col-md-6">col-md-6</div>
            <div class="col-md-6">col-md-6</div>
          </div>
        </div>
    <div class="col-md-4">col-md-4</div>
    </div>
    <div class="row">
        <div class="col-md-4">.col-md-4</div>
    <div class="col-md-8">
    我的里面嵌套了一个网格
        <div class="row">
          <div class="col-md-4">col-md-4</div>
          <div class="col-md-4">col-md-4</div>
          <div class="col-md-4">col-md-4</div>
        </div>
    </div>
    </div>
</div>
```
效果如下：
![Alt text](http://img.mukewang.com/53b10c9e0001e28b05540070.jpg)
注意：嵌套的列总数也需要遵循不超过12列。不然会造成末位列换行显示。
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>列的嵌套</title>
<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
<link rel="stylesheet" href="style.css">
</head>

<body>
<div class="container">
  <div class="row">
    <div class="col-sm-8">
      我的里面嵌套了一个网格
      <div class="row">
        <div class="col-sm-6">col-sm-6</div>
        <div class="col-sm-6">col-sm-6</div>
      </div>
    </div>
    <div class="col-sm-4">col-sm-4</div>
  </div>
  <div class="row">
    <div class="col-sm-4">.col-sm-4</div>
    <div class="col-sm-8">
      我的里面嵌套了一个网格
      <div class="row">
        <div class="col-sm-4">col-sm-4</div>
        <div class="col-sm-4">col-sm-4</div>
        <div class="col-sm-4">col-sm-4</div>
      </div>
    </div>
  </div>
  <div class="row">
      <div class="col-sm-8">.col-sm-8
          <div class="row">
              <div class="col-sm-8">.col-sm-8</div>
              <div class="col-sm-4">.col-sm-4</div>
          </div>
      </div>
      <div class="col-sm-4">.col-sm-4
        <div class="row">
          <div class="col-sm-9">.col-sm-9</div>
          <div class="col-sm-3">.col-sm-3</div>
        </div>
      </div>
  </div>
</div>


</body>
</html>
```
##下拉菜单（基本用法）
小伙伴们注意，在Bootstrap框架中的下拉菜单组件是一个独立的组件，根据不同的版本，它对应的文件：

  ☑  LESS版本：对应的源码文件为 dropdowns.less

  ☑  Sass版本：对应的源码文件为 _dropdowns.scss

  ☑  编译后的Bootstrap版本：查看bootstrap.css文件第3004行～第3130行
  
在使用Bootstrap框架的下拉菜单时，必须调用Bootstrap框架提供的bootstrap.js文件。当然，如果你使用的是未编译版本，在js文件夹下你能找到一个名为“dropdown.js”的文件。你也可以调用这个js文件。不过在我们的教程中，我们统一调用压缩好的“bootstrap.min.js”文件：
```
<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script>
```
特别声明：因为Bootstrap的组件交互效果都是依赖于jQuery库写的插件，所以在使用bootstrap.min.js之前一定要先加载jquery.min.js才会生效果。

我们先来看官网上一个简单的示例：
```
<div class="dropdown">
<button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
下拉菜单
<span class="caret"></span>
</button>
<ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
   <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
   …
   <li role="presentation" class="divider"></li>
   <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
</ul>
</div>
```
使用方法：

在使用Bootstrap框架中的下拉菜单组件时，其结构运用的正确与否非常的重要，如果结构和类名未使用正确，直接影响组件是否能正常运用。我们来简单的看看：

1、使用一个名为“dropdown”的容器包裹了整个下拉菜单元素，示例中为:
```
<div class="dropdown"></div>
```
2、使用了一个<button>按钮做为父菜单，并且定义类名“dropdown-toggle”和自定义“data-toggle”属性，且值必须和最外容器类名一致，此示例为:
```
data-toggle="dropdown"
```
3、下拉菜单项使用一个ul列表，并且定义一个类名为“dropdown-menu”，此示例为:
```
<ul class="dropdown-menu">
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>下拉菜单</title>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="style.css">
</head>
<body>

 <div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
    下拉菜单
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
  </ul>
</div> 
<div class="dropdown">
    <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown">
        选择你喜欢的水果
        <span class="caret"></span>
    </button>
    <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu2">
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">苹果</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">香蕉</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">梨</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">桃</a></li>
    </ul>
</div>
  <script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
  <script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 
</body>
</html>
```
###下拉菜单（原理分析）
Bootstrap框架中的下拉菜单组件，其下拉菜单项默认是隐藏的，如下所示：
![Alt text](http://img.mukewang.com/53e1f1850001230803900164.jpg)
因为“dropdown-menu”默认样式设置了“display:none”
当用户点击父菜单项时，下拉菜单将会被显示出来，如下所示：
![Alt text](http://img.mukewang.com/53e1f3dc0001c10204150412.jpg)
当用户再次点击时，下拉菜单将继续隐藏，如下所示：
![Alt text](http://img.mukewang.com/53e1f1850001230803900164.jpg)
原理分析：

现在我们来分析一下实现原理，非常简单，通过js技术手段，给父容器“div.dropdown”添加或移除类名“open”来控制下拉菜单显示或隐藏。也就是说，默认情况，“div.dropdown”没有类名“open”，当用户第一次点击时，“div.dropdown”会添加类名“open”；当用户再次点击时，“div.dropdown”容器中的类名“open”又会被移除。我们可以通过浏览器的firebug查看整个过程：

默认情况：
![Alt text](http://img.mukewang.com/53e314020001537208700352.jpg)
用户第一次点击：
![Alt text](http://img.mukewang.com/53e314360001a81808720333.jpg)
用户再次点击：
![Alt text](http://img.mukewang.com/53e31461000180e608710333.jpg)
###下拉菜单（下拉分隔线）
在Bootstrap框架中的下拉菜单还提供了下拉分隔线，假设下拉菜单有两个组，那么组与组之间可以通过添加一个空的`<li>`，并且给这个`<li>`添加类名“divider”来实现添加下拉分隔线的功能。对应的样式代码：
```
.dropdown-menu .divider {
  height: 1px;
  margin: 9px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
```
效果如下：
![Alt text](http://img.mukewang.com/53e346260001aed304220432.jpg)
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>下拉分隔线</title>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="style.css">
</head>

<body>
 <div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
    下拉菜单
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    <li role="presentation" class="divider"></li>
    <li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
  </ul>
</div>
<div class="dropdown">
    <button class="btn btn-default dropdown-toggle" type="button" data-toggle="dropdown" id="food">
        食物
        <span class="caret"></span>
    </button>
    <ul class="dropdown-menu" role="menu" aria-labelledby="food">
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">苹果</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">香蕉</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">梨</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">桃</a></li>
        <li role="presentation" class="divider"></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">芹菜</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">萝卜</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">茄子</a></li>
        <li role="presentation" class="divider"></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">米饭</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">馒头</a></li>
        <li role="presentation"><a role="menuitem" tabindex="-1" href="#">面条</a></li>
    </ul>
</div>
  <script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
  <script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 
</body>
</html>
```
###下拉菜单（菜单标题）
上一小节讲解通过添加“divider”可以将下拉菜单分组，为了让这个分组更明显，还可以给每个组添加一个头部（标题）。如下：
```
<div class="dropdown">
<button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
下拉菜单
<span class="caret"></span>
</button>
<ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
<li role="presentation" class="dropdown-header">第一部分菜单头部</li>
<li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
…
<li role="presentation" class="divider"></li>
<li role="presentation" class="dropdown-header">第二部分菜单头部</li>
…
<li role="presentation"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
</ul>
</div>
```
对应的样式如下：

/*查看bootstrap.css文件第3090行～第3096行*/
```
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #999;
}
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e34b1e0001ccdd07440651.jpg)
###下拉菜单（对齐方式）
实现右对齐方法：

Bootstrap框架中下拉菜单默认是左对齐，如果你想让下拉菜单相对于父容器右对齐时，可以在“dropdown-menu”上添加一个“pull-right”或者“dropdown-menu-right”类名，如下所示：
```
<div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
  下拉菜单
  <span class="caret"></span>
  </button>
  <ul class="dropdown-menu pull-right" role="menu" aria-labelledby="dropdownMenu1">
   …
  </ul>
</div>
```
上面代码中的“pull-right”类可以用“dropdown-menu-right”代替，两个类的作用是一样的，可从下面的源代码中看出。
实现原理：

对应的样式如下：

源码请查看bootstrap.css文件第3030行～第3033行和3082行～第3085行
```
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu-right {
  right: 0;
  left: auto;
}
```
同时一定要为.dropdown添加float:leftcss样式。
```
.dropdown{
  float: left;
}
```
运行效果如下所示：
![Alt text](http://img.mukewang.com/53e34c370001522204970469.jpg)
下拉菜单与父容器左边对齐:

与此同时，还有一个类名刚好与“dropdown-menu-right”相反的类名“dropdown-menu-left”，其效果就是让下拉菜单与父容器左边对齐，其实就是默认效果。

请查看bootstrap.css文件第3086行～第3089行
```
.dropdown-menu-left {
  right: auto;
  left: 0;
}
```
###下拉菜单（菜单项状态）
下拉菜单项的默认的状态（不用设置）有悬浮状态（:hover）和焦点状态（:focus）：

查看bootstrap.css文件第3049行～第3054行
```
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  color: #262626;
  text-decoration: none;
  background-color: #f5f5f5;
}
```
下拉菜单项除了上面两种状态，还有当前状态（.active）和禁用状态（.disabled）。这两种状态使用方法只需要在对应的菜单项上添加对应的类名：
```
<div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
  下拉菜单
  <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
    <li role="presentation" class="active"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
    ….
    <li role="presentation" class="disabled"><a role="menuitem" tabindex="-1" href="#">下拉菜单项</a></li>
  </ul>
</div>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e44d0d000131d208720446.jpg)
##按钮（按钮组）
单个按钮在Web页面中的运用有时候并不能满足我们的业务需求，常常会看到将多个按钮组合在一起使用，比如富文本编辑器里的一组小图标按钮等。那么在这一节中，我们主要向大家介绍Bootstrap框架为大家提供的按钮组组件。

源码查询：

按钮组也是一个独立的组件，所以可以找到对应的源码文件：

  ☑  LESS版本：对应的源文件为buttons.less

  ☑  Sass版本：对应的源文件为_buttons.scss

  ☑  CSS版本：对应bootstrap.css文件第3131行～第3291行
使用方法：

按钮组和下拉菜单组件一样，需要依赖于button.js插件才能正常运行。不过我们同样可以直接只调用bootstrap.js文件。因为这个文件已集成了button.js插件功能。
对于结构方面，非常的简单。使用一个名为“btn-group”的容器，把多个按钮放到这个容器中。如下所示：
```
<div class="btn-group">
  <button type="button" class="btn btn-default">
     <span class="glyphicon glyphicon-step-backward"></span>
  </button>
   …
  <button type="button" class="btn btn-default">
     <span class="glyphicon glyphicon-step-forward"></span>
  </button>
</div>
```
运行效果如下所示：
![Alt text](http://img.mukewang.com/53e458d10001af8808310131.jpg)
除了可以使用<button>元素之外，还可以使用其他标签元素，比如`<a>`标签。唯一要保证的是：不管使用什么标签，“.btn-group”容器里的标签元素需要带有类名“.btn”。
###按钮（按钮工具栏）
在富文本编辑器中，将按钮组分组排列在一起，比如说复制、剪切和粘贴一组；左对齐、中间对齐、右对齐和两端对齐一组，如下图所示：
![Alt text](http://img.mukewang.com/53e45edc00019ad308600101.jpg)
那么Bootstrap框架按钮工具栏也提供了这样的制作方法，你只需要将按钮组“btn-group”按组放在一个大的容器“btn-toolbar”中，如下所示：
```
<div class="btn-toolbar">
  <div class="btn-group">
    …
  </div>
  <div class="btn-group">
    …
  </div>
  <div class="btn-group">
    …
  </div>
  <div class="btn-group">
    …
  </div>
</div>
```
实现原理主要是让容器的多个分组“btn-group”元素进行浮动，并且组与组之前保持5px的左外距。代码如下：

源码请查阅bootstrap.css文件第3162行～第3173行
```
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
```
注意在”btn-toolbar”上清除浮动。

源码请查阅bootstrap.css文件第5062行
```
.btn-toolbar:before,
.btn-toolbar:after｛
　display: table;
content: " ";
｝
.btn-toolbar:after{
  clear: both;
}
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e462020001bd2e08240084.jpg)
按钮组大小设置

在介绍按钮一节中，我们知道按钮是通过btn-lg、btn-sm和btn-xs三个类名来调整padding、font-size、line-height和border-radius属性值来改变按钮大小。那么按钮组的大小，我们也可以通过类似的方法：

  ☑  .btn-group-lg:大按钮组

  ☑  .btn-group-sm:小按钮组

  ☑  .btn-group-xs:超小按钮组
只需要在“.btn-group”类名上追加对应的类名，就可以得到不同大小的按钮组。如下所示：
```
<div class="btn-toolbar">
  <div class="btn-group btn-group-lg">
    …
  </div>
  <div class="btn-group">
    …
  </div>
  <div class="btn-group btn-group-sm">
    …
  </div>
  <div class="btn-group btn-group-xs">
   …
  </div>
</div>
```
运行效果如下所示：
![Alt text](http://img.mukewang.com/53e4632b0001bb2808230100.jpg)
###按钮（嵌套分组）
很多时候，我们常把下拉菜单和普通的按钮组排列在一起，实现类似于导航菜单的效果。如下所示：
![Alt text](http://img.mukewang.com/53e466ac0001273008410307.jpg)
使用的时候，只需要把当初制作下拉菜单的“dropdown”的容器换成“btn-group”，并且和普通的按钮放在同一级。如下所示：
```
<div class="btn-group">
<button class="btnbtn-default" type="button">首页</button>
<button class="btnbtn-default" type="button">产品展示</button>
<button class="btnbtn-default" type="button">案例分析</button>
<button class="btnbtn-default" type="button">联系我们</button>
<div class="btn-group">
   <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">关于我们<span class="caret"></span></button>
   <ul class="dropdown-menu">
         <li><a href="##">公司简介</a></li>
         <li><a href="##">企业文化</a></li>
         <li><a href="##">组织结构</a></li>
         <li><a href="##">客服服务</a></li>
    </ul>
</div>
</div>
```
###按钮（垂直分组）
前面看到的示例，按钮组都是水平显示的。但在实际运用当中，总会碰到垂直显示的效果。在Bootstrap框架中也提供了这样的风格。我们只需要把水平分组的“btn-group”类名换成“btn-group-vertical”即可。如下所示：
```
<div class="btn-group-vertical">
<button class="btnbtn-default" type="button">首页</button>
<button class="btnbtn-default" type="button">产品展示</button>
<button class="btnbtn-default" type="button">案例分析</button>
<button class="btnbtn-default" type="button">联系我们</button>
<div class="btn-group">
   <button class="btnbtn-default dropdown-toggle" data-toggle="dropdown" type="button">关于我们<span class="caret"></span></button>
   <ul class="dropdown-menu">
      <li><a href="##">公司简介</a></li>
      <li><a href="##">企业文化</a></li>
      <li><a href="##">组织结构</a></li>
      <li><a href="##">客服服务</a></li>
</ul>
</div>
</div>
```
运行的效果如下：
![Alt text](http://img.mukewang.com/53e85b8f0001cfd001870309.jpg)
和水平分组按钮不一样的是：

  ☑  水平分组按钮第一个按钮左上角和左下角具有圆角以及最后一个按钮右上角和右下角具有圆角

  ☑  垂直分组按钮第一个按钮左上角和右上角具有圆角以及最后一个按钮左下角和右下角具有圆角
###按钮（等分按钮）
等分按钮的效果在移动端上特别的实用。整个按钮组宽度是容器的100%，而按钮组里面的每个按钮平分整个容器宽度。例如，如果你按钮组里面有五个按钮，那么每个按钮是20%的宽度，如果有四个按钮，那么每个按钮是25%宽度，以此类推。

等分按钮也常被称为是自适应分组按钮，其实现方法也非常的简单，只需要在按钮组“btn-group”上追加一个“btn-group-justified”类名，如下所示：
```
<div class="btn-wrap">
<div class="btn-group btn-group-justified">
  <a class="btnbtn-default" href="#">首页</a>
  <a class="btnbtn-default" href="#">产品展示</a>
  <a class="btnbtn-default" href="#">案例分析</a>
  <a class="btnbtn-default" href="#">联系我们</a>
</div>
</div>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e46af60001ab0306850099.jpg)
实现原理非常简单，把“btn-group-justified”模拟成表格（display:table），而且把里面的按钮模拟成表格单元格（display:table-cell）。具体样式代码如下：

源码请查看bootstrap.css文件第3277行～第3291行
```
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  display: table-cell;
  float: none;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
```
特别声明：在制作等分按钮组时，请尽量使用`<a>`标签元素来制作按钮，因为使用`<button>`标签元素时，使用display:table在部分浏览器下支持并不友好。
###按钮下拉菜单
按钮下拉菜单仅从外观上看和上一节介绍的下拉菜单效果基本上是一样的。不同的是在普通的下拉菜单的基础上封装了按钮（.btn）样式效果。简单点说就是点击一个按钮，会显示隐藏的下拉菜单。

按钮下拉菜单其实就是普通的下拉菜单，只不过把“`<a>`”标签元素换成了“<button>”标签元素。唯一不同的是外部容器“div.dropdown”换成了“div.btn-group”。如下所示：
```
<div class="btn-group">
      <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">按钮下拉菜单<span class="caret"></span></button>
      <ul class="dropdown-menu">
          <li><a href="##">按钮下拉菜单项</a></li>
          <li><a href="##">按钮下拉菜单项</a></li>
          <li><a href="##">按钮下拉菜单项</a></li>
          <li><a href="##">按钮下拉菜单项</a></li>
      </ul>
</div>
```
实现样式代码如下：
查看bootstrap.css文件第3204行～第3223行
```
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-right: 8px;
  padding-left: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-right: 12px;
  padding-left: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, .125);
          box-shadow: inset 0 3px 5px rgba(0, 0, 0, .125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
          box-shadow: none;
}
```
运行的效果如下：
![Alt text](http://img.mukewang.com/53e9be8300019b2a02020189.jpg)
###
按钮的向下向上三角形
按钮的向下三角形，我们是通过在`<button>`标签中添加一个“`<span>`”标签元素，并且命名为“caret”:
```
<button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">按钮下拉菜单<span class="caret"></span></button>
```
这个三角形完全是通过CSS代码来实现的：

源码请查看bootstrap.css文件第2994行～第3003行
```
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px solid;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
```
另外在按钮中的三角形“caret”做了一定的样式处理：

源码查看bootstrap.css文件第3224行～第3233行
```
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
```
有的时候我们的下拉菜单会向上弹起（接下来一个小节会介绍），这个时候我们的三角方向需要朝上显示，实现方法：需要在“.btn-group”类上追加“dropup”类名（这也是做向上弹起下拉菜单要用的类名）。

源码请查看bootstrap.css文件第3109行～第3114行
```
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  content: "";
  border-top: 0;
  border-bottom: 4px solid;
}
```
上面代码中可以看出，向上三角与向下三角的区别：其实就是改变了一个border-bottom的值。

下面是向上弹起菜单的例子：
```
<div class="btn-group dropup">
  <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">按钮下拉菜单<span class="caret"></span></button>
  <ul class="dropdown-menu">
        <li><a href="##">按钮下拉菜单项</a></li>
        <li><a href="##">按钮下拉菜单项</a></li>
        <li><a href="##">按钮下拉菜单项</a></li>
        <li><a href="##">按钮下拉菜单项</a></li>
  </ul>
</div>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e8651e0001c0a102900141.jpg)
###向上弹起的下拉菜单
有些菜单是需要向上弹出的，比如说你的菜单在页面最底部，而这个菜单正好有一个下拉菜单，为了让用户有更好的体验，不得不让下拉菜单向上弹出。在Bootstrap框架中专门为这种效果提代了一个类名“dropup”。使用方法正如前面所示，只需要在“btn-group”上添加这个类名（当然，如果是普通向上弹出下拉菜单，你只需要在“dropdown”类名基础上追加“dropup”类名即可）。
```
<div class="btn-group dropup">
    <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">按钮下拉菜单<span class="caret"></span></button>
    <ul class="dropdown-menu">
         <li><a href="##">按钮下拉菜单项</a></li>
         <li><a href="##">按钮下拉菜单项</a></li>
         <li><a href="##">按钮下拉菜单项</a></li>
         <li><a href="##">按钮下拉菜单项</a></li>
    </ul>
</div>
```
运行的效果如下：
![Alt text](http://img.mukewang.com/53e868aa0001399d01890186.jpg)
源码请查阅bootstrap.css文件第3115行～第3120行
```
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 1px;
}
```
从上面的例子中可以看出，实现方法为：主要将“dropdown-menu”的top值变成了auto，而把bottom值换成了100%：
###导航（基础样式）
导航对于一位前端人员来说并不陌生。可以说导航是一个网站重要的元素组件之一，可以便于用户查找网站所提供的各项功能服务。导航的制作方法也是千奇百怪，五花八门。在这一节中将向大家介绍如何使用Bootstrap框架制作各式各样的导航。

在Bootstrap框架将导航独立出来成为一个导航组件，根据不同的版本，可以找到对应的源码：

   ☑ LESS版本：对应的源文件是navs.less

   ☑ Sass版本：对应的源文件是_navs.scss

   ☑ 编译后版本：对应源码是bootstrap.css文件第3450行～第3641行

导航基础样式
Bootstrap框架中制作导航条主要通过“.nav”样式。默认的“.nav”样式不提供默认的导航样式，必须附加另外一个样式才会有效，比如“nav-tabs”、“nav-pills”之类。比如下面就有一个tab导航条的例子，他的实现方法就是为ul标签加入.nav和nav-tabs两个类样式。
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>导航(基础样式)</title>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="style.css">
</head>
<body>
<ul class="nav nav-tabs">
    <li><a href="##">Home</a></li>
    <li><a href="##">CSS3</a></li>
    <li><a href="##">Sass</a></li>
    <li><a href="##">jQuery</a></li>
    <li><a href="##">Responsive</a></li>
</ul>
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 
</body>
</html>
```
###导航（标签形tab导航）
标签形导航，也称为选项卡导航。特别是在很多内容分块显示的时，使用这种选项卡来分组十分适合。

标签形导航是通过“nav-tabs”样式来实现。在制作标签形导航时需要在原导航“nav”上追加此类名，如：
```
<ul class="nav nav-tabs">
     <li><a href="##">Home</a></li>
     <li><a href="##">CSS3</a></li>
     <li><a href="##">Sass</a></li>
     <li><a href="##">jQuery</a></li>
     <li><a href="##">Responsive</a></li>
</ul>
```
运行的效果如下所示：
![Alt text](http://img.mukewang.com/53e86aa60001805308940091.jpg)
实现原理非常的简单，将菜单项（li）按块显示，并且让他们在同一水平上排列，然后定义非高亮菜单的样式和鼠标悬浮效果。
其实上例的效果和我们平时看到的选项卡效果并不一致。一般情况之下，选项卡教会有一个当前选中项。其实在Bootstrap框架也相应提供了。假设我们想让“Home”项为当前选中项，只需要在其标签上添加类名“class="active"”即可：
```
<ul class="nav nav-tabs">
    <li class="active"><a href="##">Home</a></li>
    …
</ul>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e86b7700019e0308540121.jpg)
除了当前项之外，有的选项卡还带有禁用状态，实现这样的效果，只需要在标签项上添加“class="disabled"”即可：
```
<ul class="nav nav-tabs">
     <li class="active"><a href="##">Home</a></li>
     …
     <li class="disabled"><a href="##">Responsive</a></li>
</ul>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e86c8b00015ca208550155.jpg)
注意：我们看到的选项卡效果，点击菜单项就可以切换内容，如果要实现这样的效果需要配合js插件，这部分将在后面的教程中会介绍。
###导航（胶囊形(pills)导航）
胶囊形（pills）导航听起来有点别扭，因为其外形看起来有点像胶囊形状。但其更像我们平时看到的大众形导航。当前项高亮显示，并带有圆角效果。其实现方法和“nav-tabs”类似，同样的结构，只需要把类名“nav-tabs”换成“nav-pills”即可：
```
<ul class="nav nav-pills">
      <li class="active"><a href="##">Home</a></li>
      <li><a href="##">CSS3</a></li>
      <li><a href="##">Sass</a></li>
      <li><a href="##">jQuery</a></li>
      <li class="disabled"><a href="##">Responsive</a></li>
</ul>
```
![Alt text](http://img.mukewang.com/53e86ee60001711e08160307.jpg)
###导航（垂直堆叠的导航）
在实际运用当中，除了水平导航之外，还有垂直导航，就类似前面介绍的垂直排列按钮一样。制作垂直堆叠导航只需要在“nav-pills”的基础上添加一个“nav-stacked”类名即可：
```
<ul class="nav nav-pills nav-stacked">
     <li class="active"><a href="##">Home</a></li>
     <li><a href="##">CSS3</a></li>
     <li><a href="##">Sass</a></li>
     <li><a href="##">jQuery</a></li>
     <li class="disabled"><a href="##">Responsive</a></li>
</ul>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e871a2000102b707240444.jpg)
垂直堆叠导航与胶囊形导航相比，主要是让导航项不浮动，让其垂直排列，然后给相邻导航项留有一定的间距：

源码请查阅bootstrap.css文件第3578行～第3584行
```
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
```
大家是否还记得，在下拉菜单一节中，下拉菜单组与组之间有一个分隔线。其实在垂直堆叠导航也具有这样的效果，只需要添加在导航项之间添加“`<li class=”nav-divider”></li>`”即可：
```
<ul class="nav nav-pills nav-stacked">
    <li class="active"><a href="##">Home</a></li>
    <li><a href="##">CSS3</a></li>
    <li><a href="##">Sass</a></li>
    <li><a href="##">jQuery</a></li>
   <li class="nav-divider"></li>
    <li class="disabled"><a href="##">Responsive</a></li>
</ul>
```
实现样式：

源码请查阅bootstrap.css文件第3485行～3490行
```
.nav .nav-divider {
height: 1px;
margin: 9px 0;
overflow: hidden;
background-color: #e5e5e5;
}
```
或许你会问，如果我在”nav-tabs”上添加“nav-stacked”是不是也能实现垂直的标签选项导航呢？答案是：在bootstrap V2.x版本可以，但在Bootstrap V3.x版本将这个效果取消了，可能作者觉得垂直选择项并不太常见，也不美观吧。
###自适应导航（使用）
自适应导航指的是导航占据容器全部宽度，而且菜单项可以像表格的单元格一样自适应宽度。自适应导航和前面使用“btn-group-justified”制作的自适应按钮组是一样的。只不过在制作自适应导航时更换了另一个类名“nav-justified”。当然他需要和“nav-tabs”或者“nav-pills”配合在一起使用。如：
```
<ul class="nav nav-tabs nav-justified">
     <li class="active"><a href="##">Home</a></li>
     <li><a href="##">CSS3</a></li>
     <li><a href="##">Sass</a></li>
     <li><a href="##">jQuery</a></li>
     <li><a href="##">Responsive</a></li>
</ul>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53ed99aa00016bcb08630061.jpg)
###自适应导航（实现原理）
实现原理并不难，列表（`<ul>`）上设置宽度为“100%”，然后每个菜单项(`<li>`)设置了“display:table-cell”，让列表项以模拟表格单元格的形式显示：
源码请查阅bootstrap.css文件第3585行～第3607行
```
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  margin-bottom: 5px;
  text-align: center;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
  display: table-cell;
  width: 1%;
  }
  .nav-justified > li > a {
  margin-bottom: 0;
  }
}
```
这里有一个媒体查询条件：“@media (min-width:768px){…}”表示自适应导航仅在浏览器视窗宽度大于768px才能按上图风格显示。当你的浏览器视窗宽度小于768px的时候，将会按下图的风格展示：
![Alt text](http://img.mukewang.com/53e874f70001bacb06150786.jpg)
从上图效果可以得知，“nav-tabs”和“nav-justified”配合在一起使用，也就是自适应选项卡导航，浏览器视窗宽度小于768px时，在样式上做了另外的处理。
###导航加下拉菜单（二级导航）
前面介绍的都是使用Bootstrap框架制作一级导航，但很多时候，在Web页面中是离不开二级导航的效果。那么在Bootstrap框架中制作二级导航就更容易了。只需要将li当作父容器，使用类名“dropdown”，同时在li中嵌套另一个列表ul，使用前面介绍下拉菜单的方法就可以：
```
<ul class="nav nav-pills">
     <li class="active"><a href="##">首页</a></li>
     <li class="dropdown">
        <a href="##" class="dropdown-toggle" data-toggle="dropdown">教程<span class="caret"></span></a>
        <ul class="dropdown-menu">
            <li><a href="##">CSS3</a></li>
            …
       </ul>
     </li>
     <li><a href="##">关于我们</a></li>
</ul>
```
运行效果如下：
![Alt text](http://img.mukewang.com/53e877e700014b0104150304.jpg)
通过浏览器调试工具，不难发现，点击有二级导航的菜单项，会自动添加“open”类名，再次点击就会删除添加的“open”类名：
![Alt text](http://img.mukewang.com/53e878580001e0b307120404.jpg)
简单点来说，就是依靠这个类名来控制二级导航显示与否，并且设置了背景色和边框
大家回忆一下，在制作下拉菜单时，可以用分隔线，那么在二级导航中是否可以呢？我们一起来看看：

不用再说太多，只需要添加“`<li class=”nav-divider”></li>`”这样的一个空标签就可以了。

运行效果如下：
![Alt text](http://img.mukewang.com/53e878b600013f7d04750337.jpg)
###面包屑式导航
面包屑(Breadcrumb)一般用于导航，主要是起的作用是告诉用户现在所处页面的位置（当前位置）。在Bootstrap框架中面包屑也是一个独立模块组件：

LESS版本：对应源文件breadcrumbs.less
Sass版本：对应源文件_breadcrumbs.scss
编译出来的版本：源码对应bootstrap.css文件第4112行～第4129行
使用方法：
使用方式就很简单，为ol加入breadcrumb类：
```
<ol class="breadcrumb">
  <li><a href="#">首页</a></li>
  <li><a href="#">我的书</a></li>
  <li class="active">《图解CSS3》</li>
</ol>
```
实现原理：
看来不错吧！作者是使用li+li:before实现li与li之间的分隔符，所以这种方案在IE低版本就惨了（不支持）。
##导航条基础
导航条（navbar）和上一节介绍的导航（nav），就相差一个字，多了一个“条”字。其实在Bootstrap框架中他们还是明显的区别。在导航条(navbar)中有一个背景色、而且导航条可以是纯链接（类似导航），也可以是表单，还有就是表单和导航一起结合等多种形式。在这一节中将一起探讨Bootstrap框架中导航条的使用。

导航条和导航一样，在Bootstrap框架中是一个独立组件，所以你也可以根据自己的需求使用不同的版本：

LESS版本：对应的源文件navbar.less
Sass版本：对应的源文件_navbar.scss
编译后的版本：查看bootstrap.css文件第3642行～第4111行（注意这个所说的Bootstrap版本是3.1.1，其它版本位置是不一致的），这五百多行代码已从原文中节取出来，放在右侧代码顶部“bootstrap.css”文件中，小伙伴们可以查看。
###基础导航条
在Bootstrap框中，导航条和导航从外观上差别不是太多，但在实际使用中导航条要比导航复杂得多。我们先来看导航条中最基础的一个——基础导航条。

使用方法：

在制作一个基础导航条时，主要分以下几步：
第一步：首先在制作导航的列表(`<ul class=”nav”>`)基础上添加类名“navbar-nav”

第二步：在列表外部添加一个容器（div），并且使用类名“navbar”和“navbar-default”
“.navbar”样式的主要功能就是设置左右padding和圆角等效果，但他和颜色相关的样式没有进行任何的设置。其主要源码如下：

源码查看bootstrap.css文件第3642行～第3647行
```
.navbar {
  position: relative;
  min-height: 50px;
  margin-bottom: 20px;
  border: 1px solid transparent;
}
```
原理分析：

而导航条的颜色都是通过“.navbar-default”来进行控制：

源码查看bootstrap.css文件第3940行～第3943行
```
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
```
navbar-nav样式是在导航.nav的基础上重新调整了菜单项的浮动与内外边距。同时也不包括颜色等样式设置，源码请查看bootstrap.css文件第3785行～第3830行
而颜色和其他样式是通过配合父容器“navbar-default”来一起实现
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>基本导航条</title>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
</head>

<body>
<!--代码-->
<div class="navbar navbar-default" role="navigation">
     <ul class="nav navbar-nav">
	 	<li class="active"><a href="##">网站首页</a></li>
        <li><a href="##">系列教程</a></li>
        <li><a href="##">名师介绍</a></li>
        <li><a href="##">成功案例</a></li>
        <li><a href="##">关于我们</a></li>
	 </ul>
</div>
<!--代码-->
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 

</body>
</html>
```
###为导航条添加标题、二级菜单及状态
加入导航条标题

在Web页面制作中，常常在菜单前面都会有一个标题（文字字号比其它文字稍大一些），其实在Bootstrap框架也为大家做了这方面考虑，其通过“navbar-header”和“navbar-brand”来实现，示例查看代码编辑器（11-22）。

原理分析：

此功能主要起一个提醒功能，当然改良一下可以当作是logo(此处不做过多阐述)。其样式主要是加大了字体设置，并且设置了最大宽度
同样在默认导航条（navbar-default）下，对navbar-brand也做了颜色处理
导航条状态、二级菜单

同样的，在基础导航条中对菜单提供了当前状态，禁用状态，悬浮状态等效果，而且也可以带有二级菜单的导航条
效果图如下：
![Alt text](http://img.mukewang.com/53f55cad00018e8008660190.jpg)
###带表单的导航条
有的导航条中会带有搜索表单，比如新浪微博的导航条：
![Alt text](http://img.mukewang.com/53edcf9d00013cf506950056.jpg)
在Bootstrap框架中提供了一个“navbar-form”，使用方法很简单，在navbar容器中放置一个带有navbar-form类名的表单
```
<body>
<!--代码-->
<div class="navbar navbar-default" role="navigation">
  　<div class="navbar-header">
  　    <a href="##" class="navbar-brand">慕课网</a>
  　</div>
    <ul class="nav navbar-nav">
       <li class="active"><a href="##">网站首页</a></li>
       <li class="dropdown">
          <a href="##" data-toggle="dropdown" class="dropdown-toggle">系列教程<span class="caret"></span></a>
          <ul class="dropdown-menu">
        	<li><a href="##">CSS3</a></li>
        	<li><a href="##">JavaScript</a></li>
        	<li class="disabled"><a href="##">PHP</a></li>
          </ul>
      </li>
      <li><a href="##">名师介绍</a></li>
      <li><a href="##">成功案例</a></li>
      <li><a href="##">关于我们</a></li>
	 </ul>
     <form action="##" class="navbar-form navbar-left" rol="search">
   	    <div class="form-group">
   		   <input type="text" class="form-control" placeholder="请输入关键词" />
   	    </div>
        <button type="submit" class="btn btn-default">搜索</button>
     </form>
</div>
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 

</body>
```
在上面的示例中，大家看到了“navbar-left”让表单左浮动，更好实现对齐。在Bootstrap框架中，还提供了“navbar-right”样式，让元素在导航条靠右对齐。

源码请查看bootstrap.css文件第3831行～第3838行
```
@media (min-width: 768px) {
 .navbar-left {
 float: left !important;
}
.navbar-right {
 float: right !important;
 }
}
```
注意：这里有一个条件，只有当浏览器视窗宽度大于768px生效。
###导航条中的按钮、文本和链接
Bootstrap框架的导航条中除了使用navbar-brand中的a元素和navbar-nav的ul和navbar-form之外，还可以使用其他元素。框架提供了三种其他样式：

1、导航条中的按钮navbar-btn

2、导航条中的文本navbar-text

3、导航条中的普通链接navbar-link
但这三种样式在框架中使用时受到一定的限制，需要和navbar-brand、navbar-nav配合起来使用。而且对数量也有一定的限制，一般情况在使用一到两个不会有问题，超过两个就会有问题。
我们来看一下navbar-text的一个简单应用:
```
<div class="navbar navbar-default" role="navigation">
  　<div class="navbar-header">
  　    <a href="##" class="navbar-brand">慕课网</a>
  　</div>
	 <ul class="nav navbar-nav">
	 	<li><a href="##" class="navbar-text">Navbar Text</a></li>
	 	<li><a href="##" class="navbar-text">Navbar Text</a></li>
	 	<li><a href="##" class="navbar-text">Navbar Text</a></li>
	 </ul>
</div>
```
在结果窗口中查看效果，可以看出明显的存在问题，通过浏览器调试工具，可以看到a标签有margin-top和margin-bottom的值为15px，欲将其对齐，我们将上面的结构做一定的调整：
```
<div class="navbar navbar-default" role="navigation">
　<div class="navbar-header">
　    <a href="##" class="navbar-brand">慕课网</a>
　</div>
  <div class="nav navbar-nav">
      <a href="##" class="navbar-text">Navbar Text</a>
      <a href="##" class="navbar-text">Navbar Text</a>
      <a href="##" class="navbar-text">Navbar Text</a>
  </div>
</div>
```
换换标签就OK了。
###固定导航条
很多情况之一，设计师希望导航条固定在浏览器顶部或底部，这种固定式导航条的应用在移动端开发中更为常见。Bootstrap框架提供了两种固定导航条的方式：

   ☑  .navbar-fixed-top：导航条固定在浏览器窗口顶部

   ☑  .navbar-fixed-bottom：导航条固定在浏览器窗口底部

使用方法很简单，只需要在制作导航条最外部容器navbar上追加对应的类名即可：
```
<div class="navbar navbar-default navbar-fixed-top" role="navigation">
　…
</div>
<div class="content">我是内容</div>
<div class="navbar navbar-default navbar-fixed-bottom" role="navigation">
　…
</div>
```
实现原理：
实现原理很简单，就是在navbar-fixed-top和navbar-fixed-bottom使用了position：fixed属性，并且设置navbar-fixed-top的top值为0,而navbar-fixed-bottom的bottom值为0。具体的源码如下：

源码请查看bootstrap.css文件第3717 行～第3738行
```
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 768px) {
.navbar-fixed-top,
.navbar-fixed-bottom {
  border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
```
存在bug及解决方法:

从运行效果中大家不难发现，页面主内容顶部和底部都被固定导航条给遮住了。为了避免固定导航条遮盖内容，我们需要在body上做一些处理：
```
body {
  padding-top: 70px;/*有顶部固定导航条时设置*/
  padding-bottom: 70px;/*有底部固定导航条时设置*/
}
```
因为固定导航条默认高度是50px，我们一般设置padding-top和padding-bottom的值为70px，当然有的时候还是需要具体情况具体分析。
第二种解决这个bug方法：

其实除了这种解决方案之外，我们还有其他的解决方法，把固定导航条都放在页面内容前面：
```
<div class="navbar navbar-default navbar-fixed-top" role="navigation">
　…
</div>
<div class="navbar navbar-default navbar-fixed-bottom" role="navigation">
　…
</div>
<div class="content">我是内容</div>
```
在文件中添加下列样式代码：
```
.navbar-fixed-top ~ .content {
   padding-top: 70px;
}
.navbar-fixed-bottom ~ .content {
  padding-bottom: 70px;
}
```
当然，这种方法有的时候也是需要具体情况具体分析的。
###响应式导航条
如今浏览Web页面的终端不在是一尘不变了，前面示例实现的导航条仅能适配于大屏幕的浏览器，但当浏览器屏幕变小的时候，就不适合了。因此响应式设计也就随之而来。那么在一个响应式的Web页面中，对于响应式的导航条也就非常的重要。例如Bootstrap框架官网的导航条：
![Alt text](http://img.mukewang.com/53eded3b0001db2a06970046.jpg)
（宽屏时效果）
![Alt text](http://img.mukewang.com/53f580af00017ef408720073.jpg)
（中屏时效果）
![Alt text](http://img.mukewang.com/53f580e30001bba208690079.jpg)
（窄屏时效果）
如何使用Bootstrap框架实现响应式导航条效果？
先来看HTML结构见右侧代码区。

使用方法：

1、保证在窄屏时需要折叠的内容必须包裹在带一个div内，并且为这个div加入collapse、navbar-collapse两个类名。最后为这个div添加一个class类名或者id名。

2、保证在窄屏时要显示的图标样式（固定写法）：
```
<button class="navbar-toggle" type="button" data-toggle="collapse">
  <span class="sr-only">Toggle Navigation</span>
  <span class="icon-bar"></span>
  <span class="icon-bar"></span>
  <span class="icon-bar"></span>
</button>
```
3、并为button添加data-target=".类名/#id名"，究竞是类名还是id名呢？由需要折叠的div来决定。如：

需要折叠的div代码段：
```
<div class="collapse navbar-collapse" id="example">
      <ul class="nav navbar-nav">
      …
      </ul>
</div>
```
窄屏时显示的图标代码段：
```
<button class="navbar-toggle" type="button" data-toggle="collapse" data-target="#example">
  ...
</button>
```
也可以这么写，需要折叠的div代码段：
```
<div class="collapse navbar-collapse example" >
      <ul class="nav navbar-nav">
      …
      </ul>
</div>
```
窄屏时要显示的图标：
```
<button class="navbar-toggle" type="button" data-toggle="collapse" data-target=".example">
  ...
</button>
```
举个例子：
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>响应式导航条</title>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<style type="text/css">
    body{padding:50px 0 0 0;}
</style>
</head>

<body>
<!--代码-->
<div class="navbar navbar-default" role="navigation">
  <div class="navbar-header">
     　<!-- .navbar-toggle样式用于toggle收缩的内容，即nav-collapse collapse样式所在元素 -->
       <button class="navbar-toggle" type="button" data-toggle="collapse" data-target=".navbar-responsive-collapse">
         <span class="sr-only">Toggle Navigation</span>
         <span class="icon-bar"></span>
         <span class="icon-bar"></span>
         <span class="icon-bar"></span>
       </button>
       <!-- 确保无论是宽屏还是窄屏，navbar-brand都显示 -->
       <a href="##" class="navbar-brand">慕课网</a>
  </div>
  <!-- 屏幕宽度小于768px时，div.navbar-responsive-collapse容器里的内容都会隐藏，显示icon-bar图标，当点击icon-bar图标时，再展开。屏幕大于768px时，默认显示。 -->
  <div class="collapse navbar-collapse navbar-responsive-collapse">
    	<ul class="nav navbar-nav">
      		<li class="active"><a href="##">网站首页</a></li>
      		<li><a href="##">系列教程</a></li>
      		<li><a href="##">名师介绍</a></li>
      		<li><a href="##">成功案例</a></li>
      		<li><a href="##">关于我们</a></li>
	 	</ul>
  </div>
</div>

<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 

</body>
</html>
```
###反色导航条
反色导航条其实是Bootstrap框架为大家提供的第二种风格的导航条，与默认的导航条相比，使用方法并无区别，只是将navbar-deafult类名换成navbar-inverse。其变化只是导航条的背景色和文本做了修改。如下：
```
<div class="navbar  navbar-inverse" role="navigation">
<div class="nav bar-header">
      <a href="##" class="navbar-brand">慕课网</a>
</div>
<ul class="nav navbar-nav">
      <li class="active"><a href="">首页</a></li>
      <li><a href="">教程</a></li>
      <li><a href="">关于我们</a></li>
</ul>
</div>
```
###分页导航（带页码的分页导航）
分页导航几乎在哪个网站都可见。好的分页导航能给用户带来更好的用户体验。在Bootstrap框架中提供了两种分页导航：

   ☑   带页码的分页导航

   ☑   带翻页的分页导航

带页码的分页导航

带页码的分页导航，可能是最常见的一种分页导航，特别是在列表页内容超多的时候，会给用户提供分页的导航方式。在Bootstrap框架为开发者提供不同的版本
使用方法：

平时很多同学喜欢用div>a和div>span结构来制作带页码的分页导航。不过，在Bootstrap框架中使用的是ul>li>a这样的结构，在ul标签上加入pagination方法：
```
<ul class="pagination">
   <li><a href="#">&laquo;</a></li>
   <li><a href="#">1</a></li>
   <li><a href="#">2</a></li>
   <li><a href="#">3</a></li>
   <li><a href="#">4</a></li>
   <li><a href="#">5</a></li>
   <li><a href="#">&raquo;</a></li>
</ul>
```
运行效果：
![Alt text](http://img.mukewang.com/53f5972900018aa605480162.jpg)
实现原理：

从效果中可以看出，当前状态页码会高亮显示，而且不能点击。而最后一页是禁用状态，也不能点击。实现样式：
```
.pagination> .active > a,
.pagination> .active > span,
.pagination> .active >a:hover,
.pagination> .active >span:hover,
.pagination> .active >a:focus,
.pagination> .active >span:focus {
z-index: 2;
color: #fff;
cursor: default;
background-color: #428bca;
border-color: #428bca;
}
.pagination> .disabled > span,
.pagination> .disabled >span:hover,
.pagination> .disabled >span:focus,
.pagination> .disabled > a,
.pagination> .disabled >a:hover,
.pagination> .disabled >a:focus {
color: #999;
cursor: not-allowed;
background-color: #fff;
border-color: #ddd;
}
```
注意：要禁用当前状态和禁用状态不能点击，我们还要依靠js来实现，或者将这两状态下的a标签换成span标签。
大小设置：

在Bootstrap框架中，也可以通过几个不同的情况来设置其大小。类似于按钮一样：

1、通过“pagination-lg”让分页导航变大；

2、通过“pagination-sm”让分页导航变小：
```
<ul class="pagination pagination-lg">
 …
</ul>
<ul class="pagination">
 …
</ul>
<ul class="pagination pagination-sm">
 …
</ul>
```
大小设置实现原理：

其实就是通增加相应的padding大小、font-size大小和圆角大小
###
