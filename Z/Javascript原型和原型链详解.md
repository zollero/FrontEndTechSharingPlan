
每一个Javascript 对象都有三个属性：原型（prototype）、类（class）和可扩展性（extensible）。这里我们首先讲解原型的原理和运行机制。

***

学东西要带着问题，下面我们通过三个问题来学习原型。

### 1. 什么是原型？什么是原型链？

#### 普通对象和函数对象

JavaScript 中，万物皆对象！但对象也是有区别的。分为普通对象和函数对象，Object ，Function 是JS自带的函数对象。下面举例说明：

    function f1(){};
    var f2 = function(){};
    var f3 = new Function('str','console.log(str)');

    var o1 = {};
    var o2 =new Object();
    var o3 = new f1();

    console.log(typeof Object); //function
    console.log(typeof Function); //function
    console.log(typeof o1); //object
    console.log(typeof o2); //object
    console.log(typeof o3); //object
    console.log(typeof f1); //function
    console.log(typeof f2); //function
    console.log(typeof f3); //function 

#### prototype原型

除了NULL之外，每个JavaScript对象都与另一个对象关联，这个对象就是“原型”，即每个对象都从原型继承属性。

通过使用 new Object() 和直接量创建的对象都继承自Object.property。同样，通过 new Array() 创建的对象的原型就是Array.prototype，
通过 new Date() 创建的对象的原型就是 Date.protorype。

但是，不是所有的对象都有原型，如：Object.prototype 就没有原型。它不继承任何属性，就相当于它是原型链上的顶级。

在JavaScript 中，每当定义一个对象（函数）时候，对象中都会包含一些预定义的属性。其中函数对象的一个属性就是原型对象 prototype。注：普通对象没有prototype,但有_ proto _属性。

原型对象其实就是普通对象（Function.prototype除外,它是函数对象，但它很特殊，他没有prototype属性（前面说道函数对象都有prototype属性））。看下面的例子：

    function f1(){};
    console.log(f1.prototype) //f1{}
    console.log(typeof f1.prototype) //Object
    console.log(typeof Function.prototype) // Function，这个特殊
    console.log(typeof Object.prototype) // Object
    console.log(typeof Function.prototype.prototype) //undefined

从这句console.log(f1.prototype) //f1 {} 的输出就结果可以看出，f1.prototype就是f1的一个实例对象（这里就是f1的原型对象）。就是在f1创建的时候，
创建了一个它的实例对象并复制给它的prototype，基本过程如下：

    var t = new f1();
    f1.prototype = t;

所以，这就是为什么 Function.prototype 是函数对象的原因。


#### 原型链

原型对象是用来做什么的呢？主要作用是用于继承。举个栗子：

    var person = function(name){
       this.name = name
    };
    person.prototype.getName = function(){
       return this.name; // 这里this指向原型对象person ==>person.name
    }
    var QinWen = new person(‘QinWen’);
    QinWen.getName(); //QinWen

栗子中，通过给person.prototype设置了一个函数对象的属性，那么person的实例对象就继承了这个属性。
具体怎么实现的，就要看下面讲的原型链了。


    function Person(name){
        this.name=name;
    }
    
    Person.prototype.share=[];
    
    Person.prototype.printName=function(){
        alert(this.name);
    }
    
    var person1=new Person('Byron');
    var person2=new Person('Frank');
    
    person1.share.push(1);
    person2.share.push(2);
    console.log(person2.share); //[1,2]

当代码读取某个对象的某个属性的时候，都会执行一遍搜索，目标是具有给定名字的属性，搜索首先从对象实例开始，如果在实例中找到该属性则返回，如果没有则查找prototype，如果还是没有找到则继续递归prototype的prototype对象，直到找到为止，如果递归到object仍然没有则返回错误。
同样道理如果在实例中定义如prototype同名的属性或函数，则会覆盖prototype的属性或函数。—-这就是Javascript的原型链。


    function Person(name){
        this.name=name;
    }
    
    Person.prototype.share=[];
    
    var person=new Person('Byron');
    person.share=0;
    
    console.log(person.share); //0；而不是prototype中的[]


##### 原型链

JS在创建对象（不论是普通对象还是函数对象）的时候，都有一个叫做_ proto _的内置属性，用于指向创建它的函数对象的原型对象prototype。以上面的例子

    console.log(QinWen._proto_ === person.prototype) //true

同样，person.prototype对象也有_proto_属性，它指向创建它的函数对象（Object）的prototype

    console.log(person.prototype._proto_=== Object.prototype) //true

继续，Object.prototype对象也有_proto_属性，但它比较特殊，为null

    console.log(Object.prototype._proto_) //null

这个由_proto_串起来的直到Object.prototype._proto_为null的链叫做原型链。即：

> [ QinWen._proto_  ==>  person.prototype  ==>  person.prototype._proto_  ==> Object.prototype  ==>  Object.prototype._proto_ ]


### 2. 为什么要有原型？

在讲之前，先说下JavaScript作用域和作用域链。在JavaScript中，变量的作用域有全局作用域和局部作用域两种。

#### 全局作用域（Global Scope）

拥有全局作用域的变量和对象可以在代码的任何地方被访问到。一般来说，拥有全局作用局的情形有：
##### 1. 最外层函数和在最外城函数外面定义的变量拥有全局作用域

        var meetingDate = "20151001";
        function doSomething() {
            var meetingName = "sharingPlan";
            function say() {
                alert(meetingName);
            }
            say();
        }
        
        alert(meetingDate);     //20151001
        alert(meetingName);     //Uncaught ReferenceError: meetingName is not defined
        doSomething();          //sharingPlan
        say():                  //Uncaught ReferenceError: innerSay is not defined

##### 2. 所有未定义直接赋值的变量自动声明为拥有全局作用域

        function doSomething() {
            var meetingName = "sharingPlan";
            meetingDate = "20151001";
            function say() {
                alert(meetingName);
            }
            say();
        }
        
        doSomething();          //sharingPlan
        alert(meetingDate);     //20151001
        alert(meetingName);     //Uncaught ReferenceError: meetingName is not defined

变量 meetingDate拥有全局作用域，而 meetingName 在函数外部无法访问到。

##### 3. 所有window对象的属性都拥有全局作用域

一般情况下，window对象的内置属性都拥有全局作用域，如 window.name, window.loaction, window.top 等等。

#### 局部作用域（Local Scope）

和全局作用域相反，局部作用域一般只在固定的代码片段内科访问到，最常见的如函数内部。

        function doSomething() {
            var meetingName = "sharingPlan";
            function say() {
                alert(meetingName);
            }
            say();
        }
        alert(meetingName);     //Uncaught ReferenceError: meetingName is not defined
        say();                  //Uncaught ReferenceError: innerSay is not defined

该栗子中， meetingName 和 say() 都是只有局部作用域。

#### 作用域链（Scope Chain）

函数对象的作用域链是指：当函数被创建时，它能访问到的函数内部和函数外部的变量和对象的集合。包含函数内部定义的对象，和window, document，this 等一些拥有全局作用域的对象。

当调用某个对象时，会从调用处，从作用域链的内部往外找，找到相同标识符的属性则返回，如果找到作用域链最外部


#### 为什么要有prototype ？

不适用原型时，我们这样定义一个对象。看下面这个栗子：

        function Obj() {
            this.a = [];    //实例变量
            this.fn = function(){}      //实例方法
        }
        
        console.log(typeof Obj.a);      //underfined
        console.log(typeof Obj.fn);     //underfined
        
        var o = new Obj();
        console.log(typeof o.a);        //object
        console.log(typeof o.fn);       //function
        
        var o1 = new Obj();
        o1.a.push(1);
        o1.fn = {};
        console.log(o1.a);              //[1]
        console.log(typeof o1.fn);      //objection
        
        var o2 = new Obj();
        console.log(o2.a);              //[]
        console.log(typeof o2.fn);      //function

>从上面的代码中可以看出，o1 修改了 a 和 fn，而o2 中没有改变。由于数组和函数都是引用类型：对象，即o1中的属性和方法与o2中的属性和方法
>虽然同名但却不是一个引用，而是对Obj对象定义的属性和方法的一个复制。

>> 这个对属性来说没什么问题，但是对于方法来说问题就大了，因为方法都是在做完全一样的功能，但是却复制了两份。
如果一个函数对象有成百上千的实例方法，那么它的每个实例都要保持一份成百上千个方法的复制，这显然不科学。

###### 于是，prototype 应运而生。


### 3. 怎么使用原型？


1. 创建一个对象SuperMan，它有力量和魔法两个属性

        var SuperMan = function(strength, magic) {
            this.strength = strength;
            this.magic = magic;
        }

2. 通过给 prototype的属性赋值对象字面量来设定 SuperMan 对象的原型。

给SuperMan添加两个技能：砍 和 喷火。

        SuperMan.prototype = {
            cut: function() {
                return this.strength;
            },
            fire: function() {
                return this.magic;
            }
        }

3. 通过 new SuperMan() 来创建实例，并可以调用原型的方法。

        var GuangDong = new SuperMan(200, 400);
        
        GuangDong.cut();        //200
        GuangDong.fire();       //400


### 拓展

#### _proto_ 属性

_proto_ 属性（IE浏览器不支持）是实例指向原型对象的一个指针，它的作用就是指向构造函数的原型属性 constructor，通过这两个属性，
就可以访问原型的属性和方法了。

JavaScript中的对象实例本质上是由一系列的属性组成的，在这些属性中，有一个内部的不可见的特殊属性： _proto_，该属性的值指向该对象实例的原型，一个对象实例只拥有一个唯一的原型。

        function SuperMan() {
            SuperMan.prototype.name = "GuangDong";
            SuperMan.prototype.strength = 200;
            SuperMan.prototype.magic = 400;
            SuperMan.prototype.fire = function(){
                return this.magic;
            }
        }
        
        var o = new SuperMan();
        console.log(o.constructor);     //构造属性，可以获取构造函数本身
                                        //作用是被原型指针定位，然后得到构造函数本身

#### _proto_ 属性和 prototype 属性的区别

> 1. prototype是原型对象中专有的属性。
> 2. _proto_ 是普通对象的隐式属性，在 new 的时候，会指向 prototype 所指的对象。
> 3. _proto_ 实际上是某个实体对象的属性，而 prototype 则是属于构造函数的属性。_proto_只能在学习或调试的环境下使用。

#### 原型模式的执行流程

> 1. 先查找构造函数实例里的属性或方法，如果有，就立即返回。
> 2. 如果构造函数的实例没有，就去它的原型对象里找，如果有，就立即返回。


#### 总结

> 构造函数 .prototype = 原型对象

> 原型对象 .constructor = 构造函数(模板)

> 原型对象 .isPrototypeof(实例对象) 判断实例对象的原型 是不是当前对象


