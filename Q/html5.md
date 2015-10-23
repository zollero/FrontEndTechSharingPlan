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

+ `<section>`元素表示页面中一个内容区块，比如章节、页眉、页脚或页面中的其他部分。它可以与h1、h2、h3、h4、h5、h6等元素结合起来使用，表示文档结构。HTML4中使用的`<div>`，但section元素并非一个普通的容器元素；当一个容器需要被直接定义样式或通过脚本定义行为时，则推荐使用div而不是section。

以下情况不适合使用section：
1. 不要将section元素用作设置样式的页面容器，那是div的工作
2. 如果article元素、aside元素或nav元素更符合使用条件，不使用section元素
3. 不要为没有标题的内容区块使用section元素

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

+ `<nav>`元素表示页面中导航链接的部分。HTML4中使用的`<ul>` 
```
	<nav>
		<ul>
			<li><a href="#">主页</a></li>
			<li><a href="#">简介</a></li>
		</ul>
	</nav>
```
+ `<aside>`元素表示article元素的内容之外的、与article元素的内容相关的辅助信息。HTML4中使用的`<div>`
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

+ `<figure>`元素表示一段独立的流内容，一般表示文档主体流内容中的一个独立单元。使用figcaption元素为figure元素组添加标题。



##新增的非主题结构元素

+ `<header>`元素表示页面中一个内容区块或整个页面的标题。HTML4中使用的`<div>`
+ `<footer>`元素表示整个页面或页面中一个内容区块的脚注。一般来说，它会包含创作者的姓名、创作日期以及创作者联系信息。HTML4中使用的`<div>`
+ `<hgroup>`元素是将标题及其子标题进行分组的元素。hgroup元素通常会将h1~h6元素进行分组，譬如一个内容区块的标题及其子元素算一组。HTML4中使用的`<div>`
```
	<hgroup>
		<h1>这是一个标题</h1>
		<h2>这是一个子标题</h2>
	</hgroup>
``` 
+	`<address>`元素用来在文档中呈现联系信息，包含文档作者或文档维护者的名字、他们的网站链接、电子邮箱、真实地址、电话号码等。address应该不只用来呈现电子邮箱或真实地址，还用来展示跟文档相关的联系人的所有联系信息。




