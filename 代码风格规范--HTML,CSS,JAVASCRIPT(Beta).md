## 代码风格规范--HTML,CSS,JAVASCRIPT（Beta)

### 意义

当前项目中，代码风格出现很大的不同，长期累计下来，造成了很多代码的格式和风格混乱。没有统一的风格，一方面会增加团队成员沟通的成本，另一方面增加了代码维护的成本。

此时，我们制定一个代码风格规范，旨在增强团队的开发协作提高代码质量。只有一个好的代码规范，我们才能很好的推进代码Review流程的进行，接下来还可以根据自己的风格选择代码混淆、压缩和变异工具。

代码风格的统一，意义是重大的。Trust is good, control is better.

******
#### 通用规范

##### 文件/资源/变量的命名
    
###### 1. 文件/资源名的命名：以字母开头，用 - 分隔每个单词，且所有的字母都必须是小写。

避免在某些对大小写字母敏感的操作系统中，当文件通过工具压缩混淆后，或者认为修改后，大小写不同而导致引用文件不同的错误，很难被发现。

    不推荐
        MyScript.js
        myCamelCaseName.css
        i_love_underscores.html
        1001-scripts.js

    推荐
        my-script.js
        my-camel-case-name.css
        i-love-underscores.html
        thousand-and-one-scripts.js
    

###### 2. 变量的命名：使用驼峰命名法，一般变量的首字母小写，对象变量首字母大写

    推荐
        var myFirstName;    // 一般变量
        function getFirstName() {} // 一般变量
        function Game() {} // 对象变量

---
##### 缩进

    考虑到目前项目中代码大部分缩进为四个空格，暂定一次缩进为四个空格。待项目大改的时候，再定一次缩进两个空格。

---
##### 注释

    注释是程序员之间的最主要的沟通方式。特别是在写一些看似琐碎的无关紧要的代码时，由于记忆点不深刻，注释就变得尤为重要了。

    代码注释要简单直接，切中要点，必要时写上这段代码“背后的故事”。当然也可以加上所思考问题或是解决方案的链接地址。

    JavaScript注释类型：

    1. 文档注释（文件头注释）

        /**
         * [description]
         * 
         * @author  [author name]
         * @date    [file created date]
         */

    2. 方法注释
        /**
         * [getEle description]
         * @param  {[type]} A [description]
         * @return {[type]}   [description]
         */
        function getEle(A) {
            return B;
        }

    3. 行注释
        // 这是一条行注释 

---
##### 提交代码到SVN时，尽量把单个功能的文件一起提交，并添加提交注释说明提交的内容。

---
#### HTML 规范

##### 文件的引用
    
    <!DOCTYPE html>
    <html>
    <head>
        <title>Test</title>
        <meta charset="utf-8">
        <link rel="stylesheet" href="main.css" >
    </head>
    <body>
        <!-- body goes here -->
        
        <script src="main.js"></script>
    </body>
    </html>

---
##### 标签的语义化

    根据元素被创造出来时的初始意义来使用它。如：用heading元素来定义头部标题，p元素来定义文字段落，用a元素来定义链接锚点，等等。

    有根据有目的的使用HTML元素，对于可访问性、代码重用和代码效率来说意义重大。

---
##### 关注点分离

理解web中如何和为何区分不同的关注点，这很重要。这里的关注点主要指：信息（HTML结构）、外观（CSS）和行为（JavaScript）。为了使他们成为可维护的干净整洁的代码，我们要尽可能的将它们分离开来。

严格地保证结构、表现、行为三者分离，并尽量使三者之间没有太多的交互和联系。就是说，尽量在文档和模板中只包含结构性的HTML；而将所有变现代码，移入样式表中；讲所有动作行为，移入脚本之中。

    清晰的分层意味着：
        * 尽量减少样式表和脚本的引用（即：尽量合并样式表和脚本）
        * 不适用行内样式（<style>.no-goog {}</style>）
        * 不在元素上适用style属性（<hr style="border-top: 5px solid black;"）
        * 不适用行内脚本（<script>alert('no-good')</script>）
        * 不适用表象class名（red,left,center,middle）
    

---
##### HTML 内容至上

不要让非内容信息污染了你的HTML。现在有一种倾向：通过HTML来解决涉及问题，这个显然是不对的。HTML应该只关注内容。

HTML 标签的目的，就是为了不断地展示内容信息。
    * 不要引入一些特定的HTML结构来解决一些视觉设计问题
    * 不要将 img 元素当做专门用来做视觉设计的元素

以下例子展示了误将HTML用来解决设计问题的两种情况：

    不推荐
        <span class="text-box">
            <span class="square"></span>
            See the square next to me?
        </span>
        .text-box > .square {
            display: inline-block;
            width: 1rem;
            height: 1rem;
            background-color: red;
        }

    推荐
        <span class="text-box">
            See the square next to me?
        </span>
        .text-box:before {
            content: "";
            display: inline-block;
            width: 1rem;
            height: 1rem;
            background-color: red;
        }

    不推荐
        <span class="text-box">
            <img src="square.svg" alt="square" />
            See the square next to me?
        </span>

    推荐
        <span class="text-box">
            See the square next to me?
        </span>
        .text-box:before {
            content: "";
            display: inline-block;
            width: 1rem;
            height: 1rem;
            background: url(square.svg) no-repeat;
            background-size: 100%;
        }

---
##### HTML引号：使用双引号（""），而不是单引号（''）

---
#### CSS 规范

##### 合理的避免使用ID

一般情况下ID不应该被应用于样式，ID的样式不能被复用并且每个页面中你只能使用一次ID。使用ID唯一有效的是确定网页或整个站点中的位置。尽管如此，你应该始终考虑使用class，而不是ID，除非只使用一次。
    
    不推荐
        #content .title {
            font-size: 2em;
        }

    推荐
        .content .title {
            font-size: 2em;
        }

---
##### CSS选择器中避免标签名

当构建选择器时应该使用清洗，准确和有语义的class名。不要使用标签选择器。如果只关心class名，而不是你的代码元素，这样会更容易维护。

从分离的角度考虑，在表现层中不应该分配HTML标记/语义。
    
    不推荐
        div.content > header.content-header > h2.title {
            font-size: 2em;
        }

    推荐
        .content > .content-header > .title {
            font-size: 2em;
        }

---
##### 缩写属性

CSS提供了各种缩写属性（如font字体）应该尽可能使用，即使在只设置一个值的情况下。

使用缩写属性对于代码效率和可读性是很有用的。

    不推荐
        border-top-style: none;
        font-family: palatino, georgia, serif;
        font-size: 100%;
        line-height: 1.6;
        padding-bottom: 2em;
        padding-left: 1em;
        padding-right: 1em;
        padding-top: 0;

    推荐
        border-top: 0;
        font: 100%/1.6 palatino,georgia, serif;
        padding: 0 1em 2em;

---
##### 0 和单位

省略 0 值后面的单位。不要在0值后面使用单位，除非有值。

    不推荐
        padding-bottom: 0px;
        margin: 0em;

    推荐
        padding-bottom: 0;
        margin: 0;

---
##### 十六进制表示法

在可能的情况下，使用3个字符的十六进制表示法。3个字符的十六进制表示法更简短。

始终使用小写的十六进制数字。

    不推荐
        color: #FF33AA;

    推荐
        color: #f3a;

---
##### 声明顺序

这是一个选择器内书写CSS属性顺序的大致轮廓。这是为了保证更好的可读性和可扫描性。

作为最佳实践，我们应该遵循以下顺序（应该按照下表的顺序）：

        1. 结构性属性：
            a. display
            b. position, left, top, right etc.
            c. overflow, float, clear etc.
            d. magin, padding
        2. 表现性属性：
            a. background, border etc.
            b. font, text

    不推荐
        .box {
            font-family: 'Arial', sans-serif;
            border: 3px solid #ddd;
            left: 30%;
            position: absolute;
            text-transform: uppercase;
            background-color: #eee;
            right: 30%;
            display: block;
            font-size: 1.5rem;
            overflow: hidden;
            padding: 1em;
            margin: 1em;
        }

    推荐
        .box {
            display: block;
            position:absolute;
            left: 30%;
            right: 30%;
            overflow: hidden;
            margin: 1em;
            padding: 1em;
            background-color: #eee;
            border: 3px solid #ddd;
            font-family: 'Arial', sans-serif;
            font-size: 1.5rem;
            text-transform: uppercase;
        }

---
##### 声明结束和属性名结束

为了保持一致性和可扩展性，每个声明应该用分号结束，每个声明换行。

属性名的冒号后使用一个空格。出于一致性的原因。属性和值（但属性和冒号之间没有空格）的之间始终使用一个空格。

    不推荐
        h3 {
            font-weight:bold;
        }

    推荐
        h3 {
            font-weight: bold;
        }

---
#### JavaScript 规范

##### 提升声明

JavaScript会把声明语句向外提升，统一把声明语句放到作用域的最上方，可以避免变量和方法定义被自动提升造成误解，降低代码的风险。也就是说，所有的变量和方法应当定义在function内的首行。

只用一个 var 关键字声明，多个变量用逗号分隔。

    不推荐
        (function(log) {
            "use strict";

            var a = 10;
            var b = 10;

            for(var i = 0; i < 10; i++) {
                var c = a * b * i;
            }
            function f() {

            }
            var d = 100;
            var x = function() {
                return d * d;
            };
            log(x());
        }(window.console.log));

    推荐
        (function() {
            "use strict";

            var a = 10,
                b = 10,
                i,
                c,
                d,
                x;

            function f() {

            }

            for(i = 0; i < 10; i++) {
                c = a * b *i;
            }

            d = 100;
            x = function() {
                return d * d;
            };
            log(x());
        }(window.console.log));

---
##### 总是使用带类型判断的比较判断

总是使用 === 精确的比较操作符，避免在判断的过程中，由JavaScript的强制类型转换所造成的困扰。如果你使用 === 操作符，那比较的双发必须是同一类型为前提的条件下才会有效。

在只使用 == 的情况下，JavaScript所带来的强制类型转换使得判断结果跟踪变得复杂，下面的例子可以看出这样的结果又多怪了：

        (function(log) {
            "use strict";

            log('0' == 0);  //true
            log('' == false);   //true
            log('1' == true);   //true
            log(null == undefined); //true

            var x = {
                valueOf: function() {
                    return "X";
                }
            }
            log(x == "X");  // ??
        }(window.console.log));

---
##### 变量赋值时的逻辑操作

逻辑操作符 || 和 && 也被用来返回布尔值。如果操作对象是非 boolean 对象，那每个表达式将会被自左向右地做真假判断。基于此操作，最终总有一个表达式被返回回来。这在变量赋值时，是可以用来简化你的代码的。

    不推荐
        if(!x) {
            if(!y) {
                x = 1;
            } else {
                x = y;
            }
        }

    推荐
        x = x || y || 1;

这个小技巧通常用来给方法或变量设置默认的参数。

---
##### 分号

总是使用分号，因为隐式的代码嵌套会引发难以察觉的问题。当然我们要从根本上杜绝这些问题。下面看两个例子：

        //1.
        MyClass.property.myMethod = function() {
            return 42;
        }   //这儿没有分号
        
        (function() {
            
        })();
        
        //2.
        var x = {
            'i': 1,
            'j': 2
        }   //这儿没有分号
        
        // Trying to do one thing on IE and anthor on Firefox.
        // I know you'd never write code like this, but throw me a bone.
        [ffVersion, ieVersion][isIE]();

        //3.
        var THINGS_TO_EAT = [apples,oysters]    //No semicolon here.

        -1 == resultOfOperation() || die();

JavaScript中语句要以分号结束，否则它将会继续执行下去，不管换不换行。以上的每一个实例中，函数声明或对象或数组，都变成了再一句语句体内。

---
###### 澄清：分号和函数

分号需要用在表达式的结尾，而非函数声明的结尾。用下面的例子区分它们：

        var foo = function() {
            return true;
        };  // semicolon here.

        function foo() {
            return true;
        }   // no semicolon here.

---
##### 首选函数式风格

函数式变成让你可以简化代码并缩减维护陈本，因为它容易复用，又适当地解耦和更少的依赖。如下面的例子：
    
    不推荐
        (function(log) {
            "use strict";
            var arr = [10, 3, 7, 9, 100, 20],
                sum = 0,
                i;
            for(i = 0; i < arr.length; i++) {
                sum += arr[i];
            }
            log('The sum of array ' + arr + " is: " + sum);
        }(window.console.log));

    推荐
        (function(log) {
            "use strict";
            var arr = [10, 3, 7, 9, 100, 20],
                sum;

            sum = arr.reduce(function(preValue, currentValue) {
                return preValue + currentValue;
            }, 0);
            
            log('The sum of array ' + arr + " is: " + sum);
        }(window.console.log));

---
##### 不要使用 switch

switch 在所有的编程语言中都是个非常错误的难以控制的语句，建议用 if else 来替换它。

---
##### 进行多层属性调用时，要有必要的判断，杜绝出现异常报错。

---
##### 提交代码前，删除掉console.log() 和 alert()等多余无用的代码。

---
##### 代码逻辑要尽可能地简洁明了，有较高的可读性。

---
###### （完）
###### Hua Z

