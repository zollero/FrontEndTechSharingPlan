# Object 对象

## 概述

对象是JavaScript的基本数据类型，经常使用的变量和Function也都是JavaScript对象。

> JavaScript共有6种基本数据类型：underfined, null, number, string, boolean, object。

>尽管字符串，数字和布尔值不是对象，但它们的行为
和不可变对象非常类似。

对象最常见的用法是：创建（create），设置（set），查找（query），删除（delete），检测（test）和枚举（enumerate）它的属性。

对象除了有属性之外，每个对象还拥有三个相关的对象属性（object attribute）：
* 对象的原型（prototype）  指向另外一个对象，本对象的属性继承自它的原型对象。
* 对象的类（class） 是一个标识对象类型的字符串。
* 对象的扩展标记（extensible flag）指明了（ECMAScript 5）是否可以向该对象添加新属性。

************************

## 创建对象

创建对象的方法有四种：

+ 对象直接量：{}
+ 通过new 创建对象
+ 原型模式
+ Object.create()  （ECMAScript 5）

### 1. 对象直接量

创建对象最简单的方式就是在JavaScript代码中使用对象直接量。对象直接量是由若干名/值对组成的映射表，名/值对中间用冒号分隔，
名/值对之间用逗号分隔，整个映射表用花括号括起来。

    var Person = {
      name: "Kevin",
      "age": 18,
      sayHello: function() {
        alert("Hi, I am " + this.name);
      }
    }
    
    Person.age -->  18
    Person.sayHello()   -->弹出 Hi, I am Kevin


属性名可以是JavaScript标识符也可以是字符串直接量，且可以是空字符串。如下例子：

    > var a = {"":1};
    < undefined
    > a[""];
    < 1


优缺点：

    说明：对象直接量是一个表达式，每次执行都会创建并初始化一个新对象。
    优点：简单，直接
    缺点：批量创建时很麻烦，代码都是写死的。且不能用 instanceof 确定对象的类型（都会返回object）。

### 2. 使用 new 创建对象

关键字 new 后跟随一个构造函数，创建并初始化一个新对象。

JavaScript内置了一些原始类型的构造函数.如:

    var o = new Object(); //创建一个空对象，和直接量的写法 {} 一样
    var a = new Array();  //创建一个空数组，和 [] 一样
    var d = new Date(); //创建一个标识当前时间的Date对象
    var r = new RegExp("js"); //创建一个正则表达式对象，和 /js/ 一样

也可以自定义一些对象的构造方法，并通过 new 的方式创建这些对象。如：

    var Person = function(name, age) {
      this.name = name,
      this.age = age,
      this.sayHello = function() {
        alert("Hi, I am " + this.name + ", my age is " + this.age + ".");
      }
    }
    
    var Kevin = new Person("Kevin", 18);
    Kevin.sayHello();  //弹出  Hi, I am Kevin, my age is 18.

优缺点：

    优点：代码灵活，可以创建不同属性值的同类对象。
    缺点：通常，同个对象的实例方法都是一样的，造成了冗余。

### 3. 原型模式

原型模式很好的解决上马的封装性问题，默认情况下，每个对象和它的实例都共用一个原型。对象可以通过 .prototype 访问原型。

上面的方法改用原型写时：

        var Person = function() {};
        Person.prototype.name = "Kevin";
        Person.prototype.age = "19";
        Person.prototype.sayHi = function() {
            alert("Hi, I am " + this.name + ".");
        };
        
        var person1 = new Person();
        person1.sayHi();    //Hi, I am Kevin.
        
        var person2 = new Person();
        person2.sayHi();    //Hi, I am Kevin.
        
        alert(person1.sayHi == person2.sayHi);  //true

上例中，person1 和 person2 共用Person的原型。当Person的原型改变时，person1 和 person2的引用会跟着改变。

        Person.prototype.sayHi = function() {
            alert("hi");
        };
        
        person1.sayHi();    //hi
        person2.sayHi();    //hi

注意：当实例上存在与原型同名的属性时，实例的属性会屏蔽掉原型的属性。因为要先查看实例中有无该属性，
没有找到才会去原型中查找。

所以，对象可以重写原型，但此时已创建的实例依然指向旧原型。

优缺点：

        优点：共用原型减少了冗余。
        缺点：在原型上的改变会影响到所有的实例，于是实例没有了独立性。

####原型模式还有很多演变，并可以和构造函数组合使用。下面使用例子：

        var Person = function(name, age) {
            this.name = name;
            this.age = age;
            this.friends = ["KK", "CC"]
        }
        
        Person.prototype = {
            constructor: Person,
            sayHi: function() {
                alert("Hi, I am " + this.name);
            }
        }
        
        var person1 = new Person("Kevin", 18);
        var person2 = new Person("Mark", 20);
        
        person1.friends.push("BB");
        alert(person1.friends);     //KK, CC, BB
        alert(person2.friends);     //KK, CC
        alert(person1.friends === person2.friends);     //false
        alert(person1.sayHi === person2.sayHi);     //true

优缺点：

        优点：结合了构造函数模式和原型模式的优点。
        缺点：代码没有很好的封装起来。

### 4. Object.create()  （ECMAScript 5）

写法：Object.create(proto, [ propertiesObject ])

该方法是个静态函数。

> proto 是一个对象，作为新创建对象的原型。
    
> propertiesObject  可选。该参数对象是一组属性与值，该对象的属性名称将是新创建的对象的属性名称（如：可写性，可枚举行和可配置性等）。


        //若传入 null ，则新创建对象不继承任何原型，甚至不包括基础方法，如toString()，即不能和“ + ” 运算符一起正常工作。
        var o1 = Object.create(null);
        
        //如果想创建一个空对象（如通过 {} 和 new Object()创建的对象），需要传入Object.prototype
        var o2 = Object.create(Object.prototype);



## 对象的操作

### 属性的查询和设置

#### 1. 查询

对象可以通过点（.）或方括号（[]）运算符来获取属性的值。运算符左侧应该是一个表达式，它返回一个对象。
> 对应点（.）来说，右侧必须是一个以属性名称命名的简单标识符。
> 对于方括号（[]）来说，方括号内必须是一个计算结果为字符串的表达式，这个字符串就是属性的名字。

        var author = book.author;   //得到book的"author"属性
        var name = author.surname;  //得到author的"surname"属性
        var title = book["main title"]; //得到book的"main title"属性

用点（.）和方括号（[]）的区别：
> 1. 点的右侧必须是满足命名规则的标识符，如：不能有空格，不能数字开头；方括号中的表达式要返回一个计算结果是字符串。
> 2. 点的右侧的标识符不能是保留字（ECMAScript 5 中点右侧可以使用关键字，ECMAScript 3中不可以），如：class等；方括号中可以使用关键字和保留字。

#### 2. 设置

和查询属性值的写法一样，通过点和方括号也可以创建属性或给属性赋值，但需要把它们放在赋值表达式的左侧：

        book.edition = 6;   //给book创建一个名为edition的属性
        book["main title"] = "ECMAScript";  //给"main title"属性赋值

#### 3. 属性访问错误

属性访问并不一定返回或设置一个值。

查询一个不存在的属性并不会报错，如果在对象 o 自身的属性或继承的属性中均未找到属性 x ，属性访问表达式返回 underfined。

        o.x = underfined;

但是，若对象不存在，那么视图查询这个不存在的对象的属性就会报错。null 和 underfined 都没有属性，因此查询这些值的属性会报错。如下：

        var len = o.x.length;   //抛出异常：underfined 没有 length 属性

##### 避免出错的两种方法

        //No. 1 冗余但易懂的方法
        var len = underfined;
        if (o) {
            if (o.x) len = o.x.length;
        }
        
        //No.2 更简练的常用方法，获取的值是 x 的 length 属性 或 underfined
        var len = o && o.x && o.x.length;


#### 4. 删除属性

delete 运算符可以删除对象的属性。它的操作数应当是一个属性访问表达式。delete 只能删除自有属性，不能删除继承属性。要删除继承属性必须从定义这个属性的原型对象删除它，而且这会影响到所有继承自这个原型的对象。
> 意外的是，delete只是断开属性和宿主对象的联系，而不会去操作属性中的属性。

        delete book.author;     //book不再有属性 author
        delete book["main title"];  //book也不再有 main title 属性


##### delete 返回值

1. 当delete表达式删除成功或没有任何副作用（比如删除不存在的属性）时，它返回true。如果delete后不是一个属性访问表达式，同样返回true。

        o = {x: 1};     //o有个属性x，并继承属性toString
        delete o.x;     //删除x，返回true
        delete o.x;     //什么都没做（x已经不存在了），返回true
        delete o.toString;      //什么都没做（toString是继承来的），返回true
        delete 1;       //无意义，返回true

2. delete不能删除那些可配置型为false的属性。某些内置对象的属性是不可配置的，比如通过变量声明和函数什么创建的全局对象的属性。正在严格模式中，删除一个不可配置属性会报一个类型错误。在非严格模式中，在下面这些情况下delete回返回false：

        delete Object.prototype;    //不能删除，属性是不可配置的
        var x = 1;      //声明一个全局变量
        delete this.x;      //不能删除这个属性
        function f() {};        //声明一个全局函数
        delete this.f;      //也不能删除全局函数


3. 当在非严格模式中删除全局对象的可配置属性时，可以省略对全局对象的引用，直接在delete后跟随要删除的属性名即可：

        this.x = 1;     //创建一个可配置的全局属性（没有用var）
        delete x;       //将它删除

4. 然而在严格模式中，delete后跟随一个非法的操作数（比如x），则会报一个语法错误，因此必须显示指定对象及其属性：

        delete x;       //在严格模式下报语法错误
        delete this.x;      //正常工作


#### 4. 检测属性

检测对象中是否有某个属性的方法：

##### 1. in 运算符

in运算符左侧是属性名（字符串），右侧是对象。如果对象的自由属性或继承属性中包含这个属性则返回true：

        var o = {x: 1};
        "x" in o;       //true
        "y" in o;       //false
        "toString" in o;    //true，o继承toString属性

##### 2. hasOwnProperty()

对象的hasOwnProperty() 方法用来检测给点的名字是否是对象的自由属性。对应继承属性它将返回false：

        var o = {x: 1};
        o.hasOwnProperty("x");  //true
        o.hasOwnProperty("y");  //false
        o.hasOwnProperty("toString");   //false

##### 3. propertyIsEnumerable()

propertyIsEnumerable() 是hasOwnProperty()的增强版，只有检测到时自由属性且这个属性的可枚举性（enumerable attribute）为true时才返回true。

        var o = inherit({y:2});
        o.x = 1;
        o.propertyIsEnumerable("x");    //true
        o.propertyIsEnumerable("y");    //false

##### 4. 使用!== "underfined"

还有一个更简便的方法是使用 ”!==“判断一个属性是否是underfined。不管是自由属性还是继承属性，都返回true。

        var o = {x:1};
        o.x !== "underfined";       //true
        o.y !== "underfined";       //false
        o.toString !== "underfined";        //true


和 in 运算符的区别：
>  in 可以区分不存在的属性和存在但值为underfined的属性，而!==不能。如下：
>>  var o = {x: underfined};

>>  o.x !== "underfined";       //false：属性存在，但值为underfined

>>  o.y !== "underfined";       //false：属性不存在

>>  "x" in o        //true

>>  "y" in o        //false

>>  delete o.x        //删除属性x

>>  "x" in o        //false：属性不再存在


上述代码中使用的是 !== 运算符，而不是 != 。!== 可以区分 underfined 和 null。有时则不必作这种区分。

