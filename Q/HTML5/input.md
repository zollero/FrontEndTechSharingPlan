#表单

##一、表单新增属性

1.form属性：HTML4表单内的从属元素必须写在表单内部，但是在HTML5中，从属元素可以写在页面的任何地方，只需要为该元素添加form属性，属性值为该表单的id。

	<form id="testform">
		<input type="text">
	</form>
	<textarea form="testform"></textarea>

2.formaction属性：HTML中，一个表单内的所有元素都只能通过表单的action属性统一提交到统一提交到另一个页面，但是在HTML5中可以给所有的提交按钮，诸如`<input type="submit">`、`<input type="image">`、`<button type="submit">`都增加不同的formaction属性，使得点击不同的按钮，可以将表单提交到不同的页面。

	<form action="serve.jsp" id="testform">
		<input type="submit" name="s1" value="v1" formaction="s1.jsp">提交到s1
		<input type="submit" name="s2" value="v2" formaction="s2.jsp">提交到s2
		<input type="submit" name="s3" value="v3" formaction="s3.jsp">提交到s3
		<input type="submit">
	</form>

3.formmethod属性：在HTML4中，一个表单内只有一个action属性来对表单内所有元素统一指定提交页面，所以每个表单内也只有一个method属性来统一指定提交方法。但在HTML5中，可以使用formaction属性来对每个表单元素分别指定不同的提交页面，同时也可以使用formmethod属性来对每个表单元素分别指定不同的提交方法。

	<form action="serve.jsp" id="testform">
	<input type="submit" name="s1" value="v1" formaction="s1.jsp" formmethod="post">提交到s1
	<input type="submit" name="s2" value="v2" formaction="s2.jsp" formmethod="get">提交到s2
	</form>

4.placeholder属性：placeholder是指当文本框（`<input type="text">`或`<textarea>`）处于未输入状态时文本框中显示的输入提示。

	<input type="text" placeholder="input me">

5.autofocus属性：给文本框、选择框或按钮控件加上该属性，当画面打开时，该控件自动获得光标焦点。之前都是使用JavaScript实现，譬如“control.focus()”。

	<input type="text" autofocus>

一个页面上只能有一个控件具有该属性。不能滥用该属性，一般搜索框使用

6.list属性：在HTML5中，为单行文本框（`<input type="text">`）增加了一个list属性，该属性的值为某个datalist元素的id。datalist元素也是HTML5新增元素，该元素类似于选择框（`<select>`）,但是当用户想要设定的值不在选择列表之内时，允许其自行输入。该元素本身并不显示，而是当文本框获得焦点时以提示输入的方式显示。为了避免在没有支持该元素的浏览器上出现显示错误，可以用CSS等将它设定为不显示。

	<form action="">
		<input type="text" name="greeting" list="greetings">
		<datalist id="greetings" style="display:none;">
			<option value="HTML5学习">HTML5学习</option>
			<option value="CSS3学习">CSS3学习</option>
			<option value="Android学习">Android学习</option>
			<option value="IOS学习">IOS学习</option>
		</datalist>
	</form>

7.文本框的autocomplete属性：帮助输入所用的自动完成功能，是一个既节省输入时间又十分方便的功能。在HTML5之前，因为谁都可以看见输入的值，所以在安全方面存在缺陷，只要使用该属性，安全方面可以得到很好的控制

	<input type="text" name="greeting" autocomplete="on" list="greetings">
	<datalist id="greetings" style="display:none;">
		<option value="HTML5学习">HTML5学习</option>
		<option value="CSS3学习">CSS3学习</option>
		<option value="Android学习">Android学习</option>
		<option value="IOS学习">IOS学习</option>
	</datalist>


##二、input新增种类

1.url类型：url类型的input元素是一种专门用来输入url地址的文本框。提交时如果该文本框中内容不是url地址格式的文字，则不允许提交。

	<input type="url" value="http://www.baidu.com">

2.Email类型：email类型的input元素是一种专门用来输入email地址的文本框。提交时如果该文本框中内容不是email地址格式的文字，则不允许提交，但是它并不检查该email地址是否存在。提交时该文本框可以为空，除非加上了required属性。

	<input type="email" value="qinwen8627@163.com">

3.date类型：date类型的input元素以日历的形式方便用户输入

	<input type="date" name="date" value="2010-10-30">

4.time类型：time类型的input元素是一种专门用来输入时间的文本框 ，并在提交时会对输入时间的有效性进行检查。

	<input type="time" name="time" value="10:00">

5.datetime类型：datetime类型的input元素是一种专门用来输入UTC日期和时间的文本框，并且在提交时会对输入的日期和时间进行有效性检查。

	<input type="datetime" name="datetime" value="">

6.datetime-local类型：datetime-local类型的input元素是一种专门用来输入本地日期和时间的文本框，并且在提交时会对输入的日期和时间进行有效性检查。

	<input type="datetime-local" name="datetime-local" value="">

7.month类型：month类型的input元素是一种专门用来输入月份的文本框，并且在提交时会对输入的月份进行有效性检查。

	<input type="month" name="month" value="2010-10">

8.week类型：week类型的input元素是一种专门用来输入周号的文本框，并且在提交时会对输入的周号进行有效性检查。“2010-W07”代表201年第7周。

	<input type="week" name="week" value="2010-W40">

9.number类型：number类型的input元素是一种专门用来输入数字的文本框，并且在提交时会检查其中的内容是否为数字。它有min、max、step属性。

	<input type="number" name="number" value="15" min="5" max="100" step="5">

10.range类型：range类型的input元素是一种只允许输入一段范围内数值的文本框，它具有min属性与max属性，可以设定最小值与最大值（默认0和100），还有step属性，可以指定每次拖动的步幅。

	<input type="range" name="range" value="25" min="0" max="100" step="10">

11.search类型：search类型的input元素是一种专门用来输入搜索关键字的文本框。search类型与text类型仅仅在外观上在有些浏览器上有区别。但是search类型有删除的按钮。

	<input type="search" name="search" value="">

12.tel类型：tel类型的input元素被设计为用来输入电话号码的专用文本框。它没有特殊的校验规则，不强制输入数字（因为许多电话号码通常都带有其他文字，比如-），但是可以通过pattern属性来指定对于输入的电话号码格式的验证。

	<input type="tel" name="tel" value="">

13.color类型：color类型的input元素用来选取元素，它提供一个颜色选取器。

	<input type="color" name="color" onchange="document.body.style.backgroundColor=this.value;">

##三、表单验证

1.required属性：HTML5中新增的required属性可以应用在大多数输入元素上（除了隐藏元素、图片元素按钮上）。在提交时，如果元素中内容为空白，则不允许提交，同时在浏览器中显示信息提示文字，提示用户这个元素中必须输入内容。

2.pattern属性：在HTML5中，对input元素使用pattern属性，并且将属性值设为某个格式的正则表达式，在提交时会针对这些进行检查，检查其内容是否符合给定格式。当输入的内容不符合给定格式时，则不允许提交，同时在浏览器中显示信息提示文字，提示输入的内容必须符合给定格式。

	<form action="xxx.jsp">
		请输入：
		<input type="text" pattern="[A-Z]{3}" name="pattern" placeholder="输入内容：3个大写字母">
		<input type="submit" value="提交">
	</form>






标签的control属性：在HTML5中，可以再标签内部放置一个表单元素，并且通过该标签的control属性来访问该表单元素

	<form action="">
		<label id="label1">
			邮编：
			<input type="text" id="txt_zip" maxlength="6">
			<small>请输入6位数字</small>
		</label>
		<input type="button" value="设置默认值" onclick="setValue()">
	</form>
	<br>


	文本框的pattern属性：在HTML5中，对input元素使用pattern属性，并且将属性值设为某个格式的正则表达式，在提交时会针对这些进行检查，检查其内容是否符合给定格式。当输入的内容不符合给定格式时，则不允许提交，同时在浏览器中显示信息提示文字，提示输入的内容必须符合给定格式。
	<form action="xxx.jsp">
		请输入：
		<input type="text" pattern="[A-Z]{3}" name="pattern">
		<input type="submit" value="提交">
	</form>
	<br>

	 文本框的SelectionDirection属性：这对input元素与textarea元素，HTML5增加了SelectionDirection属性。当用户在这两个元素中用鼠标选取部分文字时，可以使用该属性来获取选取方向。当用户正向选取文字时，改属性值为“forward”，当用户反向选取文字时，该属性值为“backward”。当用户没有选取任何文字时，该属性值为“forward”。 chorme不支持
	<form action="">
		<input type="text">
		<input type="button" value="点击我" onclick="click()">
	</form>
	<br>

	复选框的indeterminate属性：对于复选框checkbox元素来说，过去只是选取与非选取这两种状态。在HTML5中，可以再JavaScript脚本代码中对该元素使用indeterminate属性，以说明复选框处于“尚未明确是否选取”状态。
	<input type="checkbox" indeterminate id="ck">
	<br>

	image提交按钮的height属性与width属性：针对类型为image的input元素，HTML5新增了两个属性，height、width分别用来指定图片按钮的高度和宽度
	<form action="test.jsp" method="post">
		姓名：<input type="text" name="name">
		<input type="image" src="img/1.1.jpg" alt="编辑" width="50" height="50">
	</form>
	<br>		
###增強的頁面元素

+ figure元素以及figcaption元素 ：figure元素用來表示网页上独立、被主要内容引用的部分，可以用来定义插图注释、图标、照片和代码列表等，通常会配合figcaption元素定义其标题或者说明。figcaption元素从属于figure元素，一个figure元素中只能有一个figcaption元素
```
	<figure>
		<img src="img/1.1.jpg" alt="">
		<img src="img/1.2.jpg" alt="">
		<figcaption>风景</figcaption>
	</figure>
```

+ details元素以及summary元素：details元素有一个open属性
```
	<details>
		<summary>html5</summary>
		<p>这是一段文字</p>
	</details>
```

+ mark元素
```
	<p>这是一段<mark>文字</mark></p>
```

+ progress元素和meter元素:meter元素用来定义度量衡的工具。且仅用于已知最大和最小值的度量。比较常见的使用场景有磁盘使用量、内存占用量、匹配程度和投票率等。progress元素用来表示进度。
```
	<section>
		<h2>progress元素的使用</h2>
		<p>完成的百分比<progress max="100" id="progress" style="background:green"><span>0</span>%</progress></p>
		<input type="button" value="点击" onclick="btn()">
	</section>
	function btn(){
		var i=0;
		function thread_one(){
			if(i<=100){
				i++;
				updateProgress(i);
			}
		}
		setInterval(thread_one,500);
	}
	function updateProgress(newValue){
		var progressBar = document.getElementById('progress');
		progressBar.value = newValue;
		progressBar.getElementsByTagName('span')[0].textContent = newValue;
	}

	<meter value="40" min="0" max="100" low="10" high="90" optimum="80"></meter>
```

+	cite元素表示作品的标题

	dsmkfcjd

```			
	<p>我最喜欢的电影是<cite>速度与激情</cite></p>
```

+ small元素用来标识小字印刷体的元素
```
	<small>版权</small>
```

