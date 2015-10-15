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

注意：当实例上存在与原型崇明的属性是，实例的属性会屏蔽掉原型的属性。因为要先查看实例中有无该属性，
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







