#一、HTML5元素家族

1.新增元素
 
+   用于构建页面的语义元素：`<header>、<footer>、<nav>、<section>、<article>、<aside>、<details>、<hgroup>、<figure>、<figcaption>、<summary>`

+   用于标识文本的语义元素：`<mark>、<time>、<wbr>`

+   Web表单及交互：`<input>、<datalist>、<keygen>、<meter>、<progress>、<command>、<menu>、<output>`

+   音频、视频及插件：`<audio>、<vedio>、<source>、<embed>`

+   Canvas：`<canvas>`

+   非英语支持：`<bdo>、<rp>、<rt>、<ruby>`
   
2.删除元素

+   表现性元素：`<big>、<center>、<font>、<tt>、<strike>`
    
+   不再使用frame框架，只支持iframe：`<frameset>、<frame>、<noframes>`
    
+   只有部分浏览器支持的元素：`<applet>(由<embed>或<object>替代)、<bgsound>(由<audio>替代)、<marquee>、<blink>`
    
+   其他废除的元素：`<acronym>(用<abbr>替代)、<dir>(用<ul>替代)、<rb>(用<ruby>替代)`
  
3.改变元素
  
`<small>`元素不再是减少文本字体的大小，而是表示“附属细则”，只不过字体稍小一点，比如页面底部的那些法律条款。
    
`<hr>`元素表示水平线，h5中表示主题的转换，即从一个主题变为另一个主题。
    
`<strong>`元素表示重要的文本内容，也就是那些需要在周围文本中突出出来的文本。
    
`<b>`元素表示应该用粗体表示的文本，但该文本并不比其他文本更重要。比如，关键字、产品名称等所有需要用粗体表示的文本都可以用这个标签。
    
`<em>`元素表示重读的文本。
    
`<i>`元素表示应该用斜体表示的文本，但该文本并不比其他文本更重要。比如，外文单词、技术术语等所有需要用斜体表示的文本都可以用这个标签。

#二、HTML5的结构

##新增的主题结构元素

+ `<article>`元素表示页面中的一块与上下文不相关的独立内容，譬如博客中的一篇文章或报纸中的一篇文章。HTML4中使用的`<div>`
  
  article元素代表文档、页面或应用程序中独立的、完整的、可以独自被外部引用的内容。它可以是一篇博客或报刊中的文章、一篇论坛帖子、一段用户评论或独立的插件，或其他任何独立的内容。
  
  除了内容部分，一个article元素通常有它自己的标题（一般放在一个header元素里面），有时还有自己的脚注。

  使用article的标准是判断其内的内容是不是可以单独发布或重用。
  
```
<article>
  <header>
  	<h1>苹果</h1>
  	<p>发表日期：<time pubdate="pubdate">2010/10/09</time></p>
  </header>
  <p><b>苹果</b>，植物类水果，多次花果。。。（“苹果”文章正文）</p>
  <footer>
  	<p><small>著作权归***公司所有</small></p>
  </footer>
</article>
```

+ `<section>`元素表示页面中一个内容区块，比如章节、页眉、页脚或页面中的其他部分。它可以与h1、h2、h3、h4、h5、h6等元素结合起来使用，表示文档结构。但section元素并非一个普通的容器元素；当一个容器需要被直接定义样式或通过脚本定义行为时，则推荐使用div而不是section。

以下情况不适合使用section：
1. 不要将section元素用作设置样式的页面容器，那是div的工作
2. 如果article元素、aside元素或nav元素更符合使用条件，不使用section元素
3. 不要为没有标题的内容区块使用section元素

判断使用section元素的标准：所要定义的内容如果需要出现在文档的提纲中是，用section是合适的。但是也不是绝对的。

```
<article>
		<header>
			<hgroup>
				<h1>HTML5移动应用开发</h1>
				<h2>用心写好书</h2>
			</hgroup>
			<p><small>人民英雄文学出版社出版</small></p>
		</header>
		<section class="chapter">
			<h1>第一章</h1>
			<p>移动时代，唯HTML5独尊</p>
		</section>
		<section class="chapter">
			<h1>第二章</h1>
			<p>HTML基础牢实，方能百战不殆</p>
		</section>
		<section class="appendix">
			<h1>附录A：jquery简明教程</h1>
			<p>移动时代，唯HTML5独尊</p>
		</section>
	</article>
```

+ `<nav>`元素是一个可以用作页面导航的连接组，其中的导航元素链接到其他页面或当前页面的其他部分，主要用来放置页面上相对重要的导航链接区块。这就意味着并不是所有的导航链接都需要放在nav里面，只需要将主要的、基本的链接放置nav中即可。

例如：很多页面都会在footer里面放一些版权声明、用户协议和联系信息等的链接，对于这些链接，虽然可以使用nav，但由于footer元素本身已经足够表达“底部”这样的信息，因此nav元素会显得不是很必要。

nav的应用场景：+  传统导航条
               +  侧边栏导航
               +  页面导航
               +  翻页操作

```
	<nav>
		<ul>
			<li><a href="#">主页</a></li>
			<li><a href="#">简介</a></li>
		</ul>
	</nav>
```

+ `<aside>`元素用来表示当前页面或文章的附属信息部分，它可以包含与当前页面或主要内容相关的引用、侧边栏、广告、导航条，以及其他类似的有区别于主要内容的部分。是用来定义和aside周围的内容相关的内容———即你需要定义和你当前已有内容相关的内容时，用aside。需要注意的是，aside里的内容要和它所相关联的内容相互独立，也就是说，他们虽然相关，但是关系不太密切，谁缺了谁都不会影响各自文本含义的理解。
```
	<article>
		<h1>语法</h1>
		<p>文章的正文。。。</p>
		<aside>
			<h1>名词解释</h1>
			<p>......</p>
		</aside>
	</article>
	<aside>
		<nav>
			<h2>评论</h2>
			<ul>
				<li><a href="#">20102023</a></li>
				<li><a href="#">小明：。。。。</a></li>
			</ul>
		</nav>
	</aside>
```


##新增的非主题结构元素

+ `<header>`元素表示页面中一个内容区块或整个页面的标题。
+ `<footer>`元素表示整个页面或页面中一个内容区块的脚注。一般来说，它会包含创作者的姓名、创作日期以及创作者联系信息。
+ `<hgroup>`元素是将标题及其子标题进行分组的元素。hgroup元素通常会将h1~h6元素进行分组，譬如一个内容区块的标题及其子元素算一组。即用于组合标题，只在区块需要有多个级别的标题时使用————副标题和标语等。
```
<hgroup>
	<h1>这是一个标题</h1>
	<h2>这是一个子标题</h2>
</hgroup>
```

+  `<address>`元素用来在文档中呈现联系信息，包含文档作者或文档维护者的名字、他们的网站链接、电子邮箱、真实地址、电话号码等。address应该不只用来呈现电子邮箱或真实地址，还用来展示跟文档相关的联系人的所有联系信息。

![如何选择区块内容](如何选择区块元素.png)

#三、HTML5的多媒体元素

>为了解决使用插件才能播放视频和音频，html5新增了video和audio两个元素

##audio元素

使用```<audio>```标签来定义声音，```<source>```规定多媒体资源，播放格式与编码方式可以是多个以确保浏览器可以从中选择一种自己支持的播放格式进行播放，浏览器选择顺序为代码中的书写顺序。controls属性供添加播放、暂停和音量控件。

```
	<audio controls="controls">
			<source src="http://demo/test.mp3">
			<source src="http://demo/test.ogg">
			您的浏览器不支持
	</audio>
```

##video元素

使用```<video>```标签来定义声音，其他和audio一样，只是可以设置长宽属性来展示视频的可视大小。
```
	<video controls="controls" width="500" height="300">
			<source src="http://demo/test.mp4">
			<source src="http://demo/test.ogg">
			您的浏览器不支持
	</video>
```
audio元素与video元素所具有的属性大致相同：
###属性
+	src：在该属性中指定媒体数据的URL地址。
+	autoplay：在该属性中指定媒体是否在页面加载后自动播放。
	
```
	<video src="sample".mov" autoplay></video>
```
+	preload：在该属性中指定视频或音频数据是否预加载。如果使用预加载，浏览器会预先将视频或音频数据进行缓冲，这样可以加快播放的速度，因为播放时数据已经预先缓冲完毕。该属性有3个可选值：none（表示不进行预加载）、metadata（表示只预加载每天的元数据【媒体字节数、第一帧、播放列表、持续时间等】）与auto（表示预加载全部视频或音频），默认值是auto。
+	poster(video元素独有属性)：当视频不可用时，可以使用该元素向用户展示一幅替代用的图片。当视频可用时，最好使用该属性，以免展示视频的区域中出现一片空白。

```
	<video src="sample/mov" poster="1.jpg"></video>
```
+	loop：在该属性中指定是否循环播放视频或音频。
+	controls：在该属性中指定是否为视频或音频添加浏览器自带的播放用的控制条。控制条中具有播放、暂停等按钮。
+	width和height（video元素独有属性）：在该属性中指定视频的宽度与高度（以像素为单位）。
+	currentTime属性、startTime属性与duration属性：可以使用video元素或audio元素的currentTime属性来读取媒体的当前播放位置，也可以通过修改currentTime属性来修改当前播放位置。

	可以使用video元素或audio元素的startTime属性来读取媒体播放的开始时间，通常为0。

	可以使用video元素或audio元素的duration属性来读取媒体文件总的播放时间。单位均为秒，currentTime为可读写属性，其余两个为只读属性。
+	play属性、paused属性、ended属性：可以使用video元素或audio元素的paly属性来返回一个TimeRange对象，从该对象中可以读取媒体文件的已播放部分的时间段。开始时间为已播放部分的开始时间，结束时间为已播放部分的结束时间。

	可以使用video元素或audio元素的paused属性来返回一个布尔值，表示是否处于暂停播放中，true表示媒体暂停播放，false表示媒体正在播放。
	
	可以使用video元素或audio元素的ended属性来返回一个布尔值，表示是否播放完毕，true表示媒体播放完毕，false表示还没有播放完毕。
三个均是只读属性。
+	defaultPlaybackRate属性和palybackRate属性：可以使用video元素或audio元素的defaultPlaybackRate属性读取或修改媒体默认的播放速率。
	
	可以使用video元素或audio元素的palybackRate属性读取或修改媒体当前的播放速率。
+	volume属性与muted属性：可以使用video元素或audio元素的volume属性读取或修改媒体的播放音量，范围为0到1,0为静音，1为最大音。

	可以使用video元素或audio元素的muted属性读取或修改媒体的静音状态，该值为布尔值，true表示处于静音状态，false表示处于非静音状态。

###方法

video和audio元素都具有以下四种方法：
+	play方法：使用该方法来播放媒体，自动将元素的paused属性设为false。
+	pause方法：使用该方法来暂停播放，自动将元素的paused属性设为true。
+	load方法：使用该方法来重新载入媒体进行播放，自动将元素的playbackRate属性值变为defaultPlaybackRate属性的值，自动将元素的error的值变为null。
+	canPlayType方法：使用该方法用来测试浏览器是否支持指定的媒体类型。

	该方法的定义方式：var support = videoElement.canPalyType(type);
	
	videoElement表示页面上的video元素或audio元素。type用播放文件的MIME类型来指定，可以在指定的字符串中加上表示媒体编码格式的codes参数。
	
	该方法返回3个可能值：
	
	1.	空字符串：表示浏览器不支持此种媒体类型。
	2.	maybe：表示浏览器可能支持此种媒体类型。
	3.	probably：表示浏览器确定支持此种媒体类型。
	
			     
###事件

>在利用video元素或audio元素读取或播放媒体数据的时候，会触发一系列的事件，用js捕捉这些事件就可以对这些事件进行处理。

捕捉事件的方式：

1.	监听的方式：videoElement.addEventListener(type,listener,useCapture);
	
videoElement表示页面上的video元素或audio元素。type为事件名称，listener表示绑定的函数，useCapture是一个布尔值，表示该事件的响应顺序,该值如果为true，则浏览器采用capture响应方式（即捕获：由document向下传播至事件作用的元素），如果为false，浏览器采用bubbing响应方式（即冒泡：由事件作用的元素开始一直传播至document）。默认是false。
										
```
	video.addEventListener("error",function(){
	.....
	},false);
```
				
2.JavaScript脚本中常见的获取事件句柄的方式：
								
```
  <video id="video1" src="sample.mov" onplay="begin_playing();"></video>
  function begin_playing(){...}
```




	<meta name="viewport" content="initial-scale=1, maximum-scale=1, minimum-scale=1, user-scalable=no"/>



