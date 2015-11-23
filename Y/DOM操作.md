##DOM操作
###DOM基础

与dom模型密不可分的就是JavaScript脚本技术，so,JavaScript技术是掌握dom对象的一个重要条件。

####一、元素操作
主要有三个：获取 设置 删除操作

获取：attr(name)  获取元素属性

设置：attr(key,value) 设置元素属性

删除：removeAttr(name) 删除元素属性

例：$("img").attr("title");//获取标题

####二、元素内容操作

html(val) text(val)  获取/设置元素值

####三 获取设置元素值
val(val)

css(name.value)  元素样式操作

addClass(class)  添加元素类别

toggleClass(class) 类别切换

removeClass(class)  

append() 创建节点元素

$() 动态创建页面元素

####三 节点操作
插入节点又分内部和外部插入
######内部插入
append(function(index,html)) 最新插法必须返回一个字符串 此处也可是content

appendTo(content) content表示被追加的内容

prepend(content) content表示插入目标元素内部前面的内容

prepend(function(index,html))

prependTo(content) content表示用于选择元素的jQuery表达式

例:

	$("div").append(retHtml);
	function reHtml(){
		var str = "<h1>write less do more</h1>";
		return str;
	}

######外部插入

after(content) after(function) content表示插入目标元素外部后面的内容

before(content) before(function) content表示插入目标元素外部前面的内容

insertAfter(content) insertBefore(content) content插入目标元素外部前面/后面的内容

例:

	$("div").after(retHtml);
	function reHtml(){
		var str = "<h1>write less do more</h1>";
		return str;
	}

######复制节点
clone() 复制的只有元素本身，复制后的元素不具有任何元素行为。

注意：如果要元素在复制后具有元素的全部行为，可以通过clone(true)实现

例:

	<span><img src="aaa.png"></span>
	$("img").click(function(){
		$(this).clone(true).appendTo("span");
	});


######替换节点

我们不仅可以插入复制节点 而且可以替换节点
replaceWith(content)  replaceAll()


######包裹节点
略

######遍历元素

each()

例:

	<span>
		<img src="aaa.png">
		<img src="aaa.png">
		<img src="aaa.png">
		<img src="aaa.png">
	</span>
	$("img").each(function(index){
			this.title = "第" +index;
		});
######删除元素
remove() empty()

注意:empty()并非真正的删除节点
