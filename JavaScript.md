## JavaScript 教程
> ##### JavaScript 是世界上最流行的编程语言。他有很多特点，最著名的即是其简单性与跨平台性。JS也是前端开发必不可少的一部分。
> ###### 课程源：[创客学院](http://www.makeru.com.cn/course/550.html)
> ###### .MD(markdown)：[教程链接](https://www.cnblogs.com/liugang-vip/p/6337580.html)
> ###### ~~不忘初心，继续前行~~

---
### 目录
* D1 初识JS
* D2 变量与数据类型
* D3 流程控制和普通对象
* D4 函数
* D5 作用域
* D6 闭包
* D7 数组对象
* D8 字符串与正则表达式
* D9 内建对象和函数对象
* D10 原型
* D11 ES6-概述
* D12 ES6面向对象、let和const
* D13 ES6-变量的解构赋值
* D14 ES6-Map和Set数据结构、循环

---
### D1 初识JS
#### 序
* HTML和CSS是静态语言，JS是动态语言，真正的编程语言
* 训练软件编程抽象思维逻辑能力
* 课程重点偏向编程思维，弱化动画交互效果
* JS是对现实世界的抽象，用炒菜来比喻变量，流程控制，函数等
* ES6（ECMAScript6，ECMA-262第六版）是新版本JS的标准，JS遵守ECMA262的标准
> ES7,ES8,ES9 [扩展学习](https://tuobaye.com/demo/es7_es8_es9/)

#### 初识JS
* JS是一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言。浏览器内置了解释器
* HTML（内容）+CSS（显示效果）+JS（互动效果）
* JS = ECMAScript + DOM + BOM
> ECMAScript（JS核心语法标准）
>
> DOM（Document Object Model）封装好的JS访问HTML文档的API，以树状结构组织HTML标签
>
> BOM（Browser Object Model）封装好的JS访问浏览器的API，如打开浏览器窗口，获取历史记录等

* 开发环境：编辑器，支持ES6的浏览器
* HelloWorld
```
<html>
	<head>
		<title>Hello World</title>
		<script>
			var name = '史亚楠'; //语句以;分隔
			var nickname = "思维乱跑"; //字符串可以单引号或双引号
			var age = 32; //数值类型
			alert(name); //弹出提示框，显示变量name的内容
			alert(typeof(name)); //弹出提示框，显示变量name的类型
			console.log(nickname); //浏览器调试打印输出
			console.log(age);
		</script>
	</head>
	<body>
		此处也可以写JS代码...
	</body>
</html>
```

#### 描述世界
* 空间描述：变量
```
var bag; //定义变量
bag = 'apple'; //变量赋值
```

* 有什么东西：数据类型
```
var bag; //定义变量
bag = 'apple'; //字符串
```
```
var price;
price = 3.5; //数值
```
```
var count;
count = 3;
```
```
//数组，是多个变量的集合
var arr = ['sugar','盐','花椒','味精']; //调味盒
console.log(arr);
console.log(arr[0]);
```
```
//Json对象，是对信息的描述，将零散的变量组合起来
var json_obj = {product:'矿泉水', price:2, valid_date:'2020.05.16'};
```
```
//Json对象
var person;
person = {
	name:'史亚楠', //key:value键值对
	age:32,
	nickname:'思维乱跑'
};
```
```
//布尔Boolean
var pay_already = true;
pay_already = false;
var age = 32;
if(age>=18)
{
	console.log('已成年');
}
else
{
	console.log('未成年');
}
```
```
//未定义undefined
var goods;
console.log(goods);
```

#### 描述做什么事
```
//函数的定义：做事的计划
function shopping(money)
{
	var apple = {
		name:'红富士',
		price:3.5,
		count:8
	};
	var total_price = apple.price * apple.count;
	var payOK = money > total_price; //布尔类型
	if(payOK)
	{
		console.log('支付成功');
	}
	else
	{
		console.log('支付失败')
	}
}
//函数的调用：做这件事
shopping(50);
//反复多次做一件事
shopping(20);
```

---
### D2 变量与数据类型
#### 语法识别
1. 关键字（保留字）：取名为关键字会报错
> var, function, [], {}, if, else, null, typeof, instanceof, this

2. 语句
```
var bag; //声明语句
var price = 4+5; //表达式语句
var Price = 5+6; //区分大小写
```

3. 注释
`// /* */`

4. 字面量（直接量）：直接用的数据值
> 'name', 32, {name:'syn'}, 正则表达式, 函数

#### 变量类型（弱）
##### 1 本身不可变类型，基础类型，存值
* 字符串 string

* 数字 number
> 整数，浮点数
> 
> `var count = price = 3;`

* 未定义 undefined

* 布尔型 boolean
> `alert(3>5); var judge=5<3; alert(judge);`
> 
> 空字符串，undefined，0，空对象null，它们都是为假

##### 2 本身可变类型，复合类型，引用类型，存址
* 普通对象（json名值对/键值对）Object
```
 var girl = {
	 age: 32,
	 name: 'shiyanan',
	 country: 'China',
	 height: 1.5
 };
 alert(girl.country);
 //空对象，后赋值（动态语言特性）
 var lili = {}; //var lili = new Object();
 lili.name = 'Lili';
 lili.age = 30;
```

* 函数 function
```
 var travel = function()
 {
	 alert('fly to Beijin');
	 alert('go to hotel');
	 alert('swimming in pool');
	 alert('go back home');
 }
 travel();
 travel();
```

* 数组 array（编号索引）
```
 var box = ['辣椒','盐','味精'];
 alert(box[0]);
```

#### 命名规范
1. 匈牙利命名法：变量名=类型+对象描述
>* s 字符串 String sMyData
>* fn 函数 Function fnHandle
>* b 布尔值 Boolean bIsComplete
>* i 整数 Integer iCount
>* f 浮点数 Float fPrice
>* a 数组 Array aItems
>* o 对象 Object oPerson
>* re 正则表达式 RegExp reEmailCheck
>* v 任意变量 Variant vAnything
2. 驼峰命名法：首字母小写 myData
3. 帕斯卡命名法：首字母大写 MyData
4. 下划线命名法：my_data

#### 类型转换
##### 1 显式转换
* parseInt //转换成整型
* toString //转换成字符串
* Number //转换成数字，转换失败NaN

##### 2 隐式转换
```
alert('7' * '2');
alert(7 + 'people');
var n = 1 - 'x';
alert(n);
```

#### 运算
* 算术 + - * / %
* 赋值 = += ++ -= -- *= /= %=
* 比较 < > <= >= == != === !==
* 逻辑 && || !
* 三元/三目 ? :
* 优先 ()

#### 变量声明定义、赋值
```
var name; //变量声明定义，不占用内存
var house,bag,car; //定义多个变量，逗号分隔
var 1name; //报错，不能以数字开头
name = 'shiyanan'; //变量赋值，占用内存
var name = 'shiyanan'; //声明和赋值合在一起
name = 32; //弱类型，可变
count = 8; //漏掉声明，自动补上
var a=b=c=3; //连续赋值
```

#### 引用类型实例
```
function a(b){
	b.siteUrl = 'www.baidu.com';
	b = new Object();
	b.siteUrl = 'www.google.com';
}
var c = new Object();
a(c);
console.log(c.siteUrl);
```

#### 空值的区别
* undefined //未定义，不知道是什么类型
* null //知道是object类型，但它的地址为空，不指向任何对象实体
* var obj = {}; //空的对象，指向的对象存在，但里面什么都没有
* var name = ''; //空的字符串

#### 作业
```
1题：运行的结果？
var a;
alert(a);
-
2题. 下面typeof 的返回类型有哪些
alert(typeof [1, 2]); 
alert(typeof 'leipeng'); 
var i = true; 
alert(typeof i); 
alert(typeof 1); 
var a; 
alert(typeof a); 
function a(){;};
alert(typeof a)
-
3题. 输出是？
var bool = !!2; alert(bool);
-
4.题. 下面程序输出结果，及转换后的数据类型 
alert('5'+3);
alert('5'+'3'); 
alert('5'-3); 
alert('5'-'3'); 
alert('ab'-2); 
-
5题. 实现检测数据类型是否为字符串
function isString(str)
{
	if(typeof(str) == 'String')
	{
		return true;
	}
	else
	{
		return false;
	}
}
-
6题. 输出是
var a=10; b=20; c=4; 
alert(++b+c+a++);
-
7题. 下面程序的输出是，并说明原因
var n = 0.3,m = 0.2, i = 0.2, j = 0.1;
console.log((n - m) == (i - j)); 
console.log((n-m) == 0.1);
console.log((i-j)==0.1); 
-
8题：输出结果是？
for(i=0, j=0; i<10, j<6; i++, j++){
k = i + j;
} 
alert(k);	
```

---
### D3 流程控制和普通对象
> 流程控制能够让我们在不同的状态下，执行不同的操作。万物皆对象。
#### 流程控制
* 条件语句
```
//if条件语句
if(){
	...
}else if(){
	...
}else if(){
	...
}
else(){
	...
};
//switch条件语句
switch(){
	case 1:
		do something...
		break;
	default:
		do something...
}
```

* 循环语句
```
//while循环
var count = 1;
while(count<5)
{
	count++;
	do something...
}
//do循环
do{
	do something...
}
while()
{
	console.log();
}
//for循环
for(var i=0;i<5;i++)
{
	do something...
}
//循环中止
break;
//跳过这步
continue;
//switch判断是全等判断
//switch(true){}支持范围判断
```

* 条件+循环
```
//男女性判断是否报年龄 name,sex,age
var aPerson = [{},{},{},{}];
```

#### 浏览器调试
* 断点
* 跟踪变量

#### 普通对象（Json对象）
##### 创建单个对象
```
var oActor = {
	name:'蔡徐坤',
	sex:'male',
	sing:function(){
		console.log('我会唱');
	},
	dance:function(){
		console.log('我会跳');
	}
};
alert(oActor.name);
oActor.sing();
```
```
var oActor2 = new Object();
oActor2.name = '蔡依林';
...
oActor2.sing = function(){
	...
}
```

##### 创建多个对象（工厂方式）
```
var createComputer = function(name)
{
	var oPhone = new Object();
	oPhone.name = name;
	oPhone.playMovie = function()
	{
		console.log(this.name + '我能播放电影');
	}
	oPhone.getName = function()
	{
		return obj.name;
	}
	console.log('reate');
	return oPhone;
}
var phone1 = createComputer('华为');
var phone2 = createComputer('中兴');
```

##### 遍历对象&遍历数组
```
//for in用于遍历对象的键，不用于数组的遍历
for(var key in obj)
{
	console.log(key + obj[key]);
}
//for of用于遍历数组的值
for(var value of obj)
{
	console.log(value);
}
```

---
### D4 函数
> 函数是由事件驱动的或者当它被调用时执行的可重复使用的代码块。
> 
> what 描述如何做一件事
> 
> why 学好js关键，半壁江山
>
> how 不同用法，不同侧面的细节，结合面试题学习

#### 初识函数
##### 函数声明（定义）和调用
* 关键字 function //让浏览器识别这是函数的定义声明
* 函数名 start //事情的名称，定义多个函数，名字不能重复
* 函数体 {} //规划做事的内容
* 调用函数 start(); //可调用多次
* 传参 (v) //做事需要什么东西
* 返回值 return //做完事能得到什么
* 函数作用域 //外面不能访问函数里面的东西

```
//e.g.定义和调用
function driveCar(name)
{
	...
}
function driveBus(name)
{
	...
}
driveCar('n');
driveBus('m');
//e.g.返回值
function sum(x,y)
{
	return x + y;
}
//e.g.作用域
function fn()
{
	var age = 30;
	console.log(age);
}
fn();
console.log(age);
//e.g.函数内调用另一个函数，Marathon
function things()
{
	do1(1,2);
	do2(3,4);
	do3(5,6);
}
things();
```

#### 函数定义方法
1. 具名函数
> 常规函数
```
function dinner(name)
{
	console.log(name);
}
dinner(1);
dinner(2);
var fn = dinner;
fn(3);
```

2. 匿名函数
```
var start = function()
{
	console.log('start');
}
start();
var fn = start;
fn();
```

3. 具名函数表达式（变量里放一有名称的函数）
```
var count = 0;
var fn = function fnn(x)
{
	...
	if(count++ > 2)
	{
		return;
	}
	fnn(); //调用函数本身 —— 递归调用
}
fn(1);
fnn(2); //没有访问权限，表达式变量名fnn，外部不能访问，fnn is not defined
```

4. 对象里的方法
```
var person = {
	name: 'shiyanan',
	run: function(c)
	{
		...
		walk();
		this.run();
		person.run();
	}
}
person.run('high speed');
function walk()
{
	...
}
```

#### 函数传参
> 做一件事产生不同变化
##### 传参基础类型
> 传的是值的拷贝
```
var name = "shiyanan";
function setName(n) //n形参
{
	console.log(n);
	n = "lzb";
	console.log(n);
}
setName(name); //name实参
console.log(name);
```

##### 传参引用类型
> 传的是地址的拷贝，引用类型只有一个实体，底层讲究效率
```
var person = {
	name: 'shiyanan',
	age: 18
}
function changeName(p)
{
	p.name = 'lzb';
	console.log(p.name);
}
console.log(person);
changeName(person);
console.log(person);
```

##### 传参
1. 字符串，数值，数组做参数
```
function fn(v)
{
	console.log(v + ', type:' + typeof v + ', v[2]:' + v[2]);
}
fn('shiyanan');
fn(18);
fn([12,34,67]);
```

2. 函数做参数，常用于回调函数
```
ajax('www.youku.com',function(data){console.log(data)});
function ajax(url,callback)
{
	function getData(url)
	{
		console.log('等待连接...');
		//connection(url)
		var data = 'picture OK';
		return data;
	}
	callback(getData(url));
}
```
```
//定义主函数
function A(callback)
{
	callback();  
	console.log('我是主函数');
}
//定义回调函数
function B(){
	setTimeout("console.log('我是回调函数')", 3000);//模仿耗时操作  
}
//调用主函数，将函数B传进去
A(B);
```

3. 对象做参数
```
var person = {
	name: 'shiyanan',
	run: function()
	{
		console.log('I can run');
	}
}
console.log(person.name);
person.run();
function changeP(obj)
{
	obj.name = 'lzb';
	obj.run = function()
	{
		console.log('I can fly');
	}
}
changeP(person);
console.log(person.name);
person.run();
```

##### 实参和形参
1. 实参比形参少
> 从第一个开始匹配，其他为undefined
```
function sum(x,y)
{
	console.log(x);
	console.log(y);
	return x+y;
}
sum(3,4);
alert(sum(6));
```

2. 实参比形参多
> 参数被储存起来不会丢弃，通过系统提供的数组arguments进行访问
```
function sum(x,y)
{
	console.log(arguments);
}
sum(3,4,'aaa',5);
```

#### 函数返回值
> * 无return时，返回undefined
> * return表示返回函数的运行结果
> * return后面的语句不执行

1. 返回number，string
```
alert(sum(3+5));
```

2. 返回函数
```
function fn(a)
{
	console.log('fn go '+a);
	return function(b)
	{
		console.log('fback go '+b);
		return a+b;
	}
}
//var fback = fn(a);
//fback(b);
console.log(fn(5)(10));
```

3. 返回对象
```
function fn(num)
{
	return {
		name: "shiyanan",
		run: function(b)
		{
			console.log('i can run');
			return num+b;
		}
	}
}
console.log(fn(5).run(3));
```

4. 注意
```
//return独立一行，自动加分号，return undefined
function foo()
{
	return
	{
		bar: 'hello'
	};
}
```

#### 作业
```
1. 下面输出结果是 //考察全局变量 局部变量
var f = true;
if (f === true) {
var a = 10;
}
function fn() {
var b = 20;
c = 30; //没有声明的变量，直接赋值的话，会自动创建变量，但作用域是全局的
}
fn();
console.log(a);
console.log(b);
console.log(c);
-
2. 分析下面的JavaScript，的输出是多少。 //考察 数组 for循环
a=new Array(2,3,4,5,6); 
sum=0; 
for(i=1;i < a.length;i++ ) 
sum +=a[i]; 
console.log(sum); 
-
3.输出是多少 
var x = 1; 
function ScopeTest(){
alert( x ); 
var x = 'hello world';
alert( x ); 
}
ScopeTest();
-
4.输出是多少
var name = 'laruence'; 
function echo()
{ 
alert(name); 
} 
function env()
{
var name = 'eve'; 
echo(); 
} 
env();
-
5.输出是多少 //类型转换
var a = '' + 3; 
var b = 4;
console.log(typeof a);
console.log(a+b);
console.log(a-b); 
var foo = "11"+2+"1"; 
console.log(foo);
console.log(typeof foo);
-
6. 输出是？
var obj1 = new Object()
obj1.name = 'zjzhome'
var obj2 = obj1
console.log(obj2.name); 
obj1.name = 'zjz'
console.log(obj2.name) 
-
7.输出是多少
var x=8;
var objA = {
x:'good',
y:32
}
function add(x,y){
console.log(x.y+y);
}
function fn(x,y){
x.y=5;
y(x,3);
}
fn(objA,add);
console.log(objA);
-
8: 下面程序输出为多少？
function changeObjectProperty (o) {
o.siteUrl = "http://www.csser.com/";
o = new Object(); 
o.siteUrl = "http://www.popcg.com/"; 
}
var CSSer = new Object(); 
changeObjectProperty(CSSer);
console.log(CSSer.siteUrl); 
-
9. 下面程序运行后，返回值是什么？
function foo(){
return 
{
bar: "hello"
};
}	
-
10. 写一个按照下面方式调用都能正常工作的 sum 函数
console.log(sum(2,3)); // Outputs 5
console.log(sum(2)(3)); // Outputs 5
11.下题的结果是？
function t(flag){ 
if(flag){ 
var s="ifscope"; 
for(var i=0;i<2;i++) 
; 
} 
console.log(i); 
console.log(s); 
} 
t(true); 
-
12.输出是多少
var num=5;
function func1(){
var num=3;
var age =4;
function func2(){
console.log(num);
var num ='ivan';
function func3(){
age =6;	
}
func3();
console.log(num);
console.log(age);
}
func2();
}
func1();
-
13.输出是多少 
var count =[32,4,8];
function out(){
console.log('i='+i);
}
function getCount(callback){
num =2;
console.log(num);
for(i=1;i < count.length;i++){
if(num==i){
count[i] =num;
continue;
}
count[i] = callback;
}
var num = 'hello';
console.log(num);
}
getCount(out);
count[1]();
count[2]();
count[0]();	 
-
14.输出是多少
var fn1 = 'ivan';
var name ='good';
var fn1 = function(y){
y();
} 
function fn1(x){ 
x(name);	
}
function fn2(x){
console.log(x);
console.log(name);
var name = 'hello';
console.log(name);
}
fn1(fn2);
-
15.下面的输出内容是
(function(){
var a = b = 3; 
})();
console.log("a defined? " + (typeof a !== 'undefined')); 
console.log("b defined? " + (typeof b !== 'undefined')); 
console.log(b); 
console.log(typeof a); 
```

---
### D5 作用域
> 能读写变量的范围，函数外不能访问函数内变量
> 封装

#### 变量声明定义
```
blanket = 'banana'; //当变量赋值，找不到声明时，默认会把它当成全局变量
var country = "China"; //全局变量
function fn()
{
	country = "India";
	var age = 35; //局部变量
	console.log('fn:'+country);
	console.log('fn:'+age);
}
console.log(country);
fn();
console.log(age); //不能访问函数内部资源，报错：age is not defined
```

#### 变量赋值，无声明定义
```
function fun()
{
	count = 3; //无声明则是全局变量（隐式全局变量）
	var lCount = 5;
	console.log(lCount);
}
fun();
console.log(count);
console.log(lCount);
```

#### 定义声明的提升
```
//变量声明和赋值
var getName = function()
{
	alert(5);
}
//定义函数
function getName()
{
	alert(4);
}
getName();
```
```
var myname = 'syn';
function changeName()
{
	alert(myname);
	var myname = 'lzb';
	alert(myname);
}
test();
```
```
"use strict";
function sum()
{
	b = 3; //严格模式下报错，ReferenceError: assignment to undeclared variable b
	console.log(b);
}
sum();
```

#### 变量删除
```
var a = 1;
b = 2;
var c = {
	name: 'syn',
	age: 18
}
delete a; //false
delete b; //true，无声明的隐式全局变量可删除，此时它是window.b，是window对象的属性
delete c.name; //true，删除对象的属性
console.log(a);
console.log(b);
console.log(c);
```

#### 块作用域
```
if(true)
{
	//不支持块作用域{}
}
```

#### 作用域链
> 函数嵌套→形成链条→变量回溯（当前没有，沿着链条追查上级）
```
var country = 'China',age = 80; //全局变量（任意地方用）
function fn()
{
	console.log(country);
	var country = 'India';
	var name1 = 'syn'; //局部变量，只在函数内部用
	var age = 30; //同名时，在局部作用域内（函数内），局部变量有效
	function fn() //嵌套子函数
	{
		console.log(name1); //子函数可用父函数作用域内的变量
		age = 18;
	}
	fn();
	console.log(age);
}
fn();
console.log(name1);
console.log(age);
```
```
function fn1()
{
	console.log(i);
}
var a = [];
function fn(callback)
{
	for(i=0;i<3;i++)
	{
		a[i] = callback;
	}
	callback();
}
fn(fn1);
a[0]();
a[1]();
```

#### 提升作用域范围：with
```
var person = {
	name: 'syn',
	age: 30,
	beautify: {
		age: 18
	}
}
with(person.beautify) //临时提升作用域为最近
{
	console.log(age);
}
console.log(age); //临时改变后就恢复
```

#### 匿名函数自执行
```
(function(){
	var a = b = 3;
})();
```

#### 作业
```
1 下面输出的结果是
function doSomething(){
var authorName="创客学院";
blogName="Web全栈";
alert(authorName);
}
doSomething(); //
alert(blogName); //
alert(authorName); //
-
2 下面输出的结果是
var authorName="小美老师";
function doSomething(){
	var blogName="ivan";
	function innerSay(){
		alert(blogName);
	}
	innerSay();
}
alert(authorName); //
alert(blogName); //
doSomething(); //
innerSay() //
```

---
### D6 闭包
> [闭包扩展学习](https://www.cnblogs.com/onepixel/p/5062456.html)
> 
> [JQuery源码解析](https://github.com/chokcoco/jQuery-)
> 
> 通过引用访问函数内的函数，实现信息的驻留。
> 
> 驻留：信息保持（引用在，空间则不销毁）

#### 引用在空间不灭
```
var aa;
//规划fn，并没有分配空间
function fn()
{
	var count = 0;
	function fn1()
	{
		console.log(count++);
	}
	aa = fn1;
	return fn1;
}
var p = fn(); //分配了空间，引用传值
p(); //0
p(); //1
p(); //2 通过引用访问函数内的函数，实现信息的驻留
aa();
fn()();
var p1 = fn();
p1();
p1();
p1();
aa();
aa();
```
```
var fn;
var person = function() //函数作用域：有封装隐藏作用
{
	var _name = 'yzg'; //私有private，外部不能访问
	var _count = 0;
	function getName()
	{
		_count ++;
		return _name;
	}
	fn = getName; //局部函数赋给全局变量，实现外部访问（该方式污染了全局空间，慎用）
	function getCount()
	{
		return _count; //获取访问次数
	}
	return getCount; //访回函数名（public，暴露内部信息）
}
var p = person(); //去掉试试
console.log(fn());
console.log(p()); //通过子函数访问，能访问局部变量
console.log(fn());
console.log(fn());
console.log(p()); //驻留：子函数的引用，多次调用，其内部的变量将一直保持，直至引用不存在。空间浪费
```

#### 共享封闭空间
```
function fn()
{
	var num = 0;
	return {
		add1:function()
		{
			num ++;
			console.log(num);
		}
		add2:function()
		{
			num += 2;
			console.log(num);
		}
	}
}
var c = fn();
c.add1();
c.add2();
c.add1();
```

#### 快照——新的备份
> 存档此时函数作用域内的现场信息（包括局部变量，参数，函数等）——>创建新实例
```
function fun(a)
{
	return function(b)
	{
		return function(c)
		{
			console.log(a+b+c);
		}
	}
}
var x = fun(3); //快照：驻留了参数a的信息
y = fun(7);
x(4)(5);
x(2)(1);
y(2)(1);
z = fun(5)(6);
z(2);
```

#### 链式调用
> JQuery库
```
var name = 'syn';
//匿名函数自执行（函数内是独立的名字空间，避免和外面的名字冲突）
(function(){
	var name = 'abc';
	alert(name); //local
	var jQuery = function()
	{
		return {
			getName: function()
			{
				return name;
			},
			setName: function(v)
			{
				name = v;
				return this; //返回对象本身，链式调用
			}
		}
	}
	window.$ = jQuery; //暴露对外的接口
})();
alert(name); //global
alert($().getName());
alert($().setName('lzb').getName()); //链式调用，信息的驻留
```

#### bind例
```
//只保留一份快照，结果为3
var buttons = [{name:'b1'},{name:'b2'},{name:'b3'}];
function bind()
{
	for(var i=0;i<buttons.length;i++)
	{
		buttons[i].onclick = function()
		{
			alert(i);
		}
	}
}
bind();
buttons[0].onclick();
buttons[1].onclick();
buttons[2].onclick();
//以下是修改，使结果得到0，1，2
function bind()
{
	for(var i=0;i<buttons.length;i++)
	{
		(function(m){
			buttons[i].onclick = function()
			{
				alert(m);
			}
		})(i)
	}
}
//修改2
function bind()
{
	for(let i=0;i<buttons.length;i++)
	{
		buttons[i].onclick = function()
		{
			alert(i);
		}
	}
}
```

#### 综合例，难点
```
function fun(n,o)
{
	console.log(o);
	return {
		fun:function(m)
		{
			return fun(m,n);
		}
	}
}
var a = fun(0);
a.fun(1);
a.fun(2);
a.fun(3);
var b = fun(0).fun(1).fun(2).fun(3);
var c = fun(0).fun(1);
c.fun(2);
c.fun(3);
```

---
### D7 数组对象
> [数组对象操作手册](http://www.w3school.com.cn/jsref/jsref_obj_array.asp)
#### 数组的创建和读写
```
//数组的创建
var num = [2,3,4,5];
var num1 = new Array('lili','lucy');
console.log(num);
console.log(num[2]);
num[1] = 55;
console.log(num);
//数组的遍历
for(var i = 0;i<num.length;i++)
{
	console.log(num[i]);
}
//数组的嵌套
var worker = [
	'lili',
	[2,3], //存址
	[5,6,function(){console.log('fn');}], //存址
	{name:'syn',age:30} //存址
];
//访问
var a = worker[2];
var fn = a[2];
fn();
//或者
worker[2][2]();
//多维数组
var count = [[[1,2,3],[4,5,6],[7,8,9]],[1,2,3],[4,5,6],[7,8,9]],[1,2,3],[4,5,6],[7,8,9]]];
```

#### 数组的操作方法
```
Array 对象方法
方法	        描述
push()	    向数组的末尾添加一个或更多元素，并返回新的长度。
pop()	    删除并返回数组的最后一个元素
shift()	    删除并返回数组的第一个元素
unshift()	向数组的开头添加一个或更多元素，并返回新的长度。
slice()	    从某个已有的数组返回选定的元素
splice()	删除元素，并向数组添加新元素。
concat()	连接两个或更多的数组，并返回结果。
sort()	    对数组的元素进行排序
reverse()	颠倒数组中元素的顺序。
join()	    把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。
toString()	把数组转换为字符串，并返回结果。
indexOf()   返回元素在数组中的位置
---
toSource()	返回该对象的源代码。
toLocaleString()	把数组转换为本地数组，并返回结果。
valueOf()	返回数组对象的原始值
```

##### 改变原数组的操作方法
```
var a = [7,2,5,9,8,1,2,3,4,5,6];
a.push(7);
a.pop();
a.unshift(2);
a.shift();
a.splice(2,2,5);
a.sort(); //字符串排序
a.reverse();
console.log(a);
```

##### 不改变原数组的操作方法
* 添加分隔符
```
var a = [7,2,5,9,8,1,2,3,4,5,6];
console.log(a.indexOf(2));
console.log(a.slice(1,3));
console.log(a.slice(2));
console.log(a.join(':')); //数组转字符串
function join(){} //实现join函数
```
* 拼接数组
```
var age1 = [1,2,3];
var age2 = [4,5,6];
console.log(age1.concat(age2));
var age3 = age1.concat(age1,age2);
console.log(age3);
function concat(){}
```
* 遍历数组
```
var w = [11,22,33];
//for循环
for(var i=0; i<w.length; i++)
{
	console.log(w[i]);
}
//for of遍历
for(var j of w)
{
	console.log(j);
}
//forEach遍历：参数为回调函数，好处是灵活将算法和循环分开
var a = [];
function callback(v)
{
	a.push(v**2);
	console.log(v);
}
w.forEach(callback);
console.log(a);
//map遍历：会得到新的数组，转换数组中的元素
var new_w = w.map(function(v){return v**2});
console.log(new_w);
function map(a,callback)
{
	var b = [];
	for(var i = 0; i<a.length; i++)
	{
		b[i] = callback(a[i]);
	}
	return b;
}
console.log(map(w,function(v){return v**2;}))
```
* 转字符串
```
var a = [1,2,3];
console.log(a.toString()); //与join不传参的结果一致
```

#### 各函数实现
```
var a = [44,55,66,11,22,33];
//删除并返回数组的最后一个元素
function pop1(arr)
{
	var ret = arr[arr.length - 1];
	--arr.length;
	return ret;
}
console.log(pop1(a));
console.log(a);
//删除并返回数组的第一个元素
function shift1(arr)
{
	arr.reverse();
	var ret = pop1(arr);
	arr.reverse();
	return ret;
}
console.log(shift1(a));
console.log(a);
//向数组的末尾添加一个元素，并返回新的长度。
function push1(arr, str)
{
	arr[arr.length] = str;
	return arr.length;
}
console.log(push1(a, '我爱你'));
console.log(a);
//向数组的开头添加一个元素，并返回新的长度。
function unshift1(arr, str)
{
	for(var i=arr.length;i>=0;i--)
	{
		if(i>0)
		{
			arr[i] = arr[i-1];
		}
		else
		{
			arr[i] = str;
		}
	}
	return arr.length;
}
console.log(unshift1(a, '我也爱你'));
console.log(a);
//从某个已有的数组返回选定的元素
function slice1(arr, start, end)
{
	var b = [];
	for(var i=start;i<end;i++)
	{
		push1(b, arr[i]);
	}
	return b;
}
console.log(slice1(a, 2, 4));
console.log(a);
//把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。
function join1(arr, separator)
{
	var b = '';
	for(var i=0;i<arr.length;i++)
	{
		if(i<arr.length-1)
		{
			b += arr[i] + separator;
		}
		else
		{
			b += arr[i];
		}
	}
	return b;
}
function join2(arr, separator)
{
	var b = '';
	for(var i=0;i<arr.length;i++)
	{
		b += arr[i];
		if(i<arr.length-1)
		{
			b += separator;
		}
	}
	return b;
}
function join3(arr, separator)
{
	var b = '';
	for(var i=0;i<arr.length-1;i++)
	{
		b += arr[i] + separator;
	}
	return b += arr[i];
}
function join4(arr, separator)
{
	var b = '';
	for(var i=0;i<arr.length;i++)
	{
		i<arr.length-1 ? b += arr[i] + separator : b += arr[i];
	}
	return b;
}
function join5(arr, separator)
{
	var b = arr[0];
	for(var i=1;i<arr.length;i++)
	{
		b += separator + arr[i];
	}
	return b;
}
console.log(reverse1(a));
console.log(a);
```

#### 数组去重
1. 不利用系统函数
```
var a = [44,11,66,121,22,11,0,5];
function checkR(arr, n)
{
	for(var i=0;i<arr.length;i++)
	{
		if(n === arr[i])
		{
			return true;
		}
	}
	return false;
}
function handle_arr(arr)
{
	var b = [];
	for(var i=0; i<a.length; i++)
	{
		if(checkR(b, a[i]) == false)
		{
			b[b.length] = a[i];
		}
	}
	return b;
}
console.log(handle_arr(a));
```
2. 利用系统函数：indexOf，push

#### 数组复制
1. 浅度复制
> push
2. 深度复制（如多维数组）
> 判断类型再递归，typeof，instanceof，constructor，Object.prototype.toString.call()四者区别

#### 数组排序
> [十种排序方式详解](https://blog.csdn.net/hellozhxy/article/details/79911867)
> 
> 冒泡排序，选择排序，插入排序，快速排序
> 
> [二叉树专题](https://www.jianshu.com/p/bf73c8d50dc2)

---
### D8 字符串与正则表达式
#### 字符串
```
//创建字符串
var str = "abc"; //普通字符串
var str1 = new String('abc'); //字符串对象，类似数组
str[0] = str1[1] = "w"; //不能通过此方法改变
//字符串对象方法
var name1 = 'shiyanan';
console.log(name1.charAt(1)); //查某个位置的字符
console.log(name1.indexOf('ya')); //查某个字符串的位置
//提取子字符串：string[x]，substring，slice，substr
var date = "xiamen 2019.06.18";
console.log(date[2]);
console.log(date.substring(4,9));
console.log(date.substring(4));
console.log(date.substring());
console.log(date.slice(4,9));
console.log(date.slice(4));
console.log(date.slice());
console.log(date.slice(-4)); //支持倒数
console.log(date.substr(4,3)); //第二个参数是长度
console.log(date.substr(-4)); //支持倒数
//大小写转化
console.log(date.toLowerCase());
console.log(date.toUpperCase());
console.log(date);
//拼接字符串
console.log('myname'+' '+'is shiyanan');
var a = 'myname';
var b = ' ';
var c = 'is shiyanan';
var d = a.concat(b,c);
console.log(d);
//分隔字符串
str.split(':').toString();
str.split('-').join('-');
//查找字符串，替换
str.search('shi');
str.search(/\d/); //支持正则表达式
str.indexOf('shi');
str.match(/\d/); //正则表达式
str.replace(/\d/),''); //替换，删除
```

#### 正则表达式
> 字符串规则过滤

```
var reg = /age/;
var reg = /d/;
var reg = /\d/; //数字 reg.test("i am age of 18"); 检测参数内是否含有数字 true
var reg = /\D/; //非数字 reg.test("i am age of 18"); 检测参数内是否含有非数字 true
var reg = /^\d/; //行首是否存在数字
var reg = /^Abc/;
var reg = /com$/; //行尾是否存在com
var reg = /^\d{4,6}$/; //re.test("12345") 4~6次数字
var reg = /^\d{6}$/; //刚好6次数字
var reg = /^\d{6,}$/; //连续出现6次以上数字，至少6次
var reg = /^\d+$/; //只能输入数字，1个以上，相当于{1,}
var reg = /^\d*$/; //只能输入数字，0个以上，相当于{0,}
var reg = /^\d?$/; //只能输入数字，0个或1个，相当于{0,1}
var reg = /^[123]$/; //1或2或3
var reg = /^[1-9]$/; //1到9的一个数
var reg = /[ab]/ = /a|b/; //a或者b
var reg = /[a-zA-Z]/ = /[a-z]|[A-Z]/; //大小写英文字母
var reg = /^[a-zA-Z]+$/; //只能输入英文
var reg = /[^a-z]/; //非a-z
var reg = /[\u4e00-\u9fa5]/; //检测中文 console.log(reg.test('a我爱你b'));
var reg = /./; //任意字符
var reg = /\.com/; //转义后表示.本身
var reg = /\w/; //字母、数字、下划线
```
```
//验证一年的12个月（正确格式为01-09和1-12）
var reg1 = /^[1-9]$/; //1 2 3 4 5 6 7 8 9
var reg2 = /^0[1-9]$/; //01 02 03 04 05 06 07 08 09
var reg3 = /^1[012]$/; //10 11 12
var reg = /^[1-9]|0[1-9]|1[012]$/;
var reg = /^0?[1-9]|1[012]$/;
```
```
var str = 'my age 是 18';
var reg = /\d/ig; //i(ignore)忽略大小写 g(global)全局检测
console.log(str.match(reg));
```
```
//去除首尾空格 \s
var str = ' i am age of 18 ';
var reg = /(^\s+)|(\s+$)/g;
console.log(str.replace(reg,''));
```
```
//邮箱过滤 window.onload后执行
var reg = /^\w+@[a-z0-9]+\.[a-z]{2,4}$/;
/^\w+ 行首是大小写字母、数字、下划线的多个字符
@[a-z0-9] 表示@后是英文或数字
\. 转义字符.（因.是关键字）
[a-z]{2,4}$/ 行尾是2到4个英文字母
```

* 验证用户密码
* 验证身份证号
* 验证Internet地址

#### 作业
1. 实现字符串indexOf函数
2. 实现一函数，判断一个字符串是不是回文字符串（从左右读右左读是一样的。比如"Level"）

---
### D9 内建对象和函数对象
> [JavaScript对象](http://www.w3school.com.cn/jsref/index.asp)

#### 内建对象
1. String 字符串对象

2. Number 数值对象
```
var n = new Number(55);
```

3. Array 数组对象

4. Math 对象：数学函数
```
var d = Math.random();
```

5. Date 对象：日期时间
```
var d = new Data();
console.log(Date());
d.getYear();
d.getDate();
d.getDay();
d.getHours();
d.getMonth();
```

6. DOM 对象
> 定义了访问和操作HTML文档的属性和方法
```
document.getElementById('a');
```

7. BOM 对象
> 定义了访问和操作浏览器的属性和方法
```
//window对象可以省略
console.log(window.location);
console.log(location);
window.alert('a');
alert('a');
var callback = function(){console.log(Date())};
window.setTimeout(callback, 3000); //3000毫秒后回调函数
```

#### 函数对象
##### 面向对象
> [Javascript的继承与多态](https://www.jianshu.com/p/5cb692658704)

* 封装（快速打包）：隐藏，分而治之，复用，
* 继承（父子）
* 多态（不同类型）

##### 定义函数对象（非普通函数）
```
//1. 定义属性
function Person(name, age, face) //Person此处是构造函数，习惯性大写首字母，PHP的类
{
	this.name = name;
	this.age = age;
	this.face = face;
}
//2. 定义方法
Person.prototype.sing = function()
{
	console.log('sing');
}
Person.prototype.run = function()
{
	console.log('run');
}
//3. 创建一个新对象（实现）
var syn = new Person("shiyanan",18,'ugly'); //运行构造函数Person，拷贝方式分配新空间，所以可单独更改
var lzb = new Person("lzb",32,'handsome'); //再创建一个，分配了一个新的实例空间
console.log(syn.name);
console.log(lzb);
syn.name = 'abc';
lzb.name = 'fff';
console.log(syn, lzb);
lzb.run();
syn.run();
syn.length = 160; //动态增加属性，JS动态语言可以，但只在syn实例内增加
syn.look = function() //动态增加方法，但只在syn实例内增加
{
	console.log('syn look');
}
Person.prototype.walk = function() //动态更改对象的方法，更改后所有实例都会有
{
	console.log(this.name + ' walking');
}
syn.walk(); //实例继承了对象的属性和方法
lzb.walk();
delete syn.name; //动态删除对象属性，不能删除方法
```

##### this用法
```
var age = 30; //全局对象都相当于window的属性
var man = {
	name: 'syn',
	age: 18,
	getName: function()
	{
		console.log(this.name);
	},
	getAge: function()
	{
		function aaa() //局部函数
		{
			console.log(this + ' ' + this.age); //局部普通函数里的this指的是window对象
		}
		aaa(); //相当于window.aaa()
		this.aaa();
		console.log(this + ' ' + this.age); //作为对象的方法时，this指向的是这个对象
		return this; //用于链式调用
	},
	aaa:function()
	{
		console.log(this.age);
	}
}
man.getName(); //man对象调用方法，this指向man对象
man.getAge().getName();
//函数对象中的this
function Person()
{
	this.name = 'syn';
}
Person.prototype.getName = function()
{
	console.log(this.name); //this指向实例
	return this; //用于链式调用
}
var p1 = new Person();
p1.getName();
```

##### call/apply让函数服务不同的对象
```
var obj1 = {
	name:'syn',
	age:18
}
var obj2 = {
	name:'lzb',
	age:30
}
age = 40;
getAge();
var age = 40;
getAge();
function getAge()
{
	console.log(this.age);
}
getAge.call(obj1); //callback
getAge.apply(obj2); //让函数服务不同的对象，和call的区别是传参不一样
//call和apply的区别
var stu1 = {
	name:'name1',
	age:20,
	say:function(a,b)
	{
		console.log(this.name+' '+this.age+' '+a+' '+b);
	}
};
var stu2 = {
	name:'syn',
	age:18
};
var stu3 = {
	name:'lzb',
	age:32
};
stu1.say.call(stu2,'清华','北大');
stu1.say.apply(stu3,['交大','南大']);
```
```
//继承函数对象
function Person()
{
	this.class = "脊椎动物";
	this.legs = 4;
}
Person.prototype.eat = function()
{
	console.log('use mouth');
}
function AsianPeople()
{
	Person.call(this);
	this.skin = "yellow";
}
function Syn()
{
	AsianPeople.call(this);
	this.gender = 'female';
}
var syn = new Syn();
console.log(syn.legs, syn.skin, syn.gender);
```

##### bind防止this丢失
```
var name = 'syn';
var obj = {
	name : 'lzb',
	getName: function()
	{
		console.log(this.name); //this动态绑定，谁用就指向谁
	}
}
obj.getName();
var fn = obj.getName;
fn(); //相当于window.fn()
var fn1 = obj.getName.bind(obj);
fn1(); //类似于obj.getName.call(obj);
//实现bind函数
Function.prototype.bind2 = function(obj)
{
	var self = this;
	return function(){
		self.apply(obj,arguments);
	};
}
var fn2 = obj.getName.bind2(obj);
fn2();
```

#### 作业
```
题1. 下面程序输出信息是 
function Foo() {
getName = function () { alert (1); }; //为定义的变量，会默认加全局声明
return this;
}
var getName = function () { alert (4);};
Foo().getName(); 
---
题2. 下面程序输出信息是 
var getName = function () { alert (4);};
function getName() { alert (5);}	 
getName(); 
---
题3. 下面程序结果是什么？
function foo(){
foo.a = function(){alert(1)}; 
this.a = function(){alert(2)};
a = function(){alert(3)};
var a = function(){alert(4)};
}; 
foo.prototype.a = function(){alert(5)};
foo.a = function(){alert(6)};
foo.a(); 
var obj = new foo();
obj.a(); 
foo.a(); 
---
题4. 下面的代码会输出什么结果？给出你的答案 
var name = 'lili';
var obj = {
name: 'liming',
prop: {
name: 'ivan',
getname: function() {
return this.name;
}
}
};
console.log(obj.prop.getname()); 
var test = obj.prop.getname; 
console.log(test()); 
题5. 解决前一个问题，使输出一致
```

---
### D10 原型
> 原型可称为一种创建模式，它提供了一种创建对象的最佳方式。

#### 原型属性方法
```
new Person(a,b); //创建原型实例
var a = new Person(1,2); //a存放指向原型实例的引用地址
var b = new Person(2,2); //写时复制，只有在新增或更改键值对时才复制
//本身找不到，才去原型里找，节省空间
```

#### 原型继承
```
function Person(name,sex)
{
	this.name = name;
	this.sex = sex;
}
Person.prototype.getName = function()
{
	console.log(this.name);
}
function Teacher(name,sex,lang)
{
	Person.call(this,name,sex); //属性继承
	this.lang = lang;
}
Teacher.prototype = new Person(); //方法继承
//prototype.constructor仅仅可以用于识别对象是由哪个构造函数初始化的，仅此而已。
Teacher.prototype.constructor = Teacher;
Teacher.prototype.getLang = function()
{
	console.log(this.lang);
}
var me = new Teacher('lzb','male','English');
me.getLang();
me.getName();
me.getName = function() //只影响实例本身
{
	console.log('new name');
}
me.getName();
Person.prototype.getName = function()
{
	console.log('proto name');
}
delete me.getName; //删除实例的方法
me.getName(); //一级级回溯原型的方法
```
> 原型回溯机制：当前没有，则回溯上级
> 
> [为什么要设置prototype.constructor](https://blog.csdn.net/yiifaa/article/details/72809704)

#### 继承动态更改
* 动态语言可更改 Class.prototype.function

#### 控制台查看继承
1. firebug插件，查看DOM
2. chrome Sources，查看Scope->global，加入断点或debugger;代码

#### 作业
```
1. 下面输出结果是：
　　　　function fun1(a){
　　　　　　this.a = a;
　　　　}
　　　　function fun2(a){
　　　　　　if(a){
　　　　　　　　this.a = a;
　　　　　　}
　　　　}
　　　　fun1.prototype.a = 1;
　　　　fun2.prototype.a = 1;
　　　　console.log(new fun1().a);
　　　　console.log(new fun2(2).a);
---
2. 已知如下类father，要求设计一个son类继承自father，并实现如下功能： 
function father(){ 
this.name = "father"; 
this.showName = function(){ 
console.log(this.name); 
} 
} 
function son(){ 
this.name = "son"; 
this.showName1 = function(){ 
console.log(this.name); 
} 
this.showName2 = function(){ 
console.log(this.name); 
} 
this.showName3 = function(){ 
console.log(this.__super.name + "= >" + this.name); 
} 
} 
请完善son部分相关代码，得到如下结果 
var son = new son(); 
console.log(son instanceof father ); // 得到：true 
son.showName1(); // 得到："son" (需要读到son中的name属性) 
son.showName2(); // 得到：”father" (需要读到father中的name属性) 
son.showName3(); //得到：”father" => "son" (需要同时读到son中的name和father中的name) 
```

---
### D11 ES6-概述
* 全称ECMAScript6.0，2015年发布的JS标准
* 使JS更安全易用
* 能编写复杂的大型应用程序
* 浏览器支持越来越完善，许多应用都用它
* 如node.js react等，是未来的方向
* 学习：掌握核心语法

#### 环境安装
* [安装nodejs](https://nodejs.org)
* ES6转ES5 babel 或 [在线转译](https://babeljs.io/repl/)
* [HBuilderX的nodejs插件配置](http://ask.dcloud.net.cn/article/19599)
* [HBuilderX scss/sass 使用教程](http://ask.dcloud.net.cn/article/35683)
* [手把手教你如何在Node中使用ES6](https://www.jianshu.com/p/c1865ee36edb)

#### 模块化
* [JS模块化](https://www.imooc.com/article/43781?block_id=tuijian_wz)
* html,js,css分开放置，多文件整合
* ES5无模块化功能，多文件可能冲突 → 通过CommonJS和AMD模块规范来实现
* ES6通过模块化实现

##### CommonJS同步，后端JS模块化
* CommonJS规范：一文件一模块，单独的作用域，同步加载（后端采用nodejs，react等）
* require 引用模块
* module.exports 导出模块
* 安装nodejs后即支持CommonJS
```
//m.js
var count = 1;
function msg()
{
	console.log('ttt');
}
module.exports.count = count;
module.exports.msg = msg;
//m2.js
var count = 2;
function msg()
{
	console.log('ttt2');
}
module.exports.count = count;
module.exports.msg = msg;
//user.js
var obj = require('./m.js');
var obj2 = require('./m2.js');
console.log(obj.count);
obj2.msg();
//node
>node user.js
```

##### AMD异步，前端js模块化
* AMD规范：异步加载模块，允许指定回调函数，前端采用如浏览器
* require(["js/a"]); //使用模块   define //定义模块
* 支持AMD //需下载RequireJS库

##### ES6模块化功能import
```
//m.js
var count = 1;
function msg()
{
	console.log('msg');
}
export {count,msg};
//export var count = 1;
//export var msg = 2;
//js.js
import {count,msg} from "./m";
console.log(count);
```
* ES6模块是静态的，不能通过if语句等动态加载

##### ES6引用传递 vs CommonJS值拷贝（缺陷）
```
//CommonJS
count++; //值没变
getCount(); //闭包，值改变
//ES6
//解决了上述问题，以及安全性问题
```

#### 作业
```
1.es5有模块化功能吗， 它通过什么来实现的模块化的。
2.es6有模块化功能吗， 它通过什么来实现的模块化的。
3. nodejs 虽支持大部分es6语法，但import export不支持，通过安装什么来实现：
4. 下面使用AMD语法的是
A. require //引用模块
module.exports //导出模块 
B.	require(["js/a"]); //使用模块
define //定义模块 
5. es6模块相比 CommonJS 是 值拷贝还是引用传递
```

---
### D12 ES6面向对象、let和const
#### 创建类的属性和方法，继承，防止this丢失，静态方法
```
//创建类的属性和方法
class Person{
	//构造函数
	constructor(name,gender){
		this.name = name;
		this.gender = gender;
		this.getName = this.getName.bind(this); //防止this丢失，参考下节
	}
	getName(){
		console.log(this.name);
	}
	setName(name){
		this.name = name;
	}
	static getName()
	{
		console.log('static ' + this.name);
	}
}
var obj = new Person('shiyanan','f');
console.log(obj.name);
obj.getName();
obj.setName('lzb');
obj.getName();
//继承
class Teacher extends Person{
	constructor(name,gender,age){
		super(name,gender); //继承父类属性和方法
		this.age = age; //新增属性
	}
	speak(lang)
	{
		console.log("I can speak " + lang);
	}
}
var obj2 = new Teacher('liming','m',33);
obj2.speak('English');
//父变子也变，动态更改，C和java等不支持
Person.prototype.getGender = function(){
	console.log(this.gender);
}
obj.getGender();
obj2.getGender();
//防止this丢失
var method = obj.getGender();
method(); //报错，因为this指向window对象
//静态方法
Person.getName();
Teacher.getName();
//静态属性
Person.grade = 2;
Teacher.school = "qinghua";
console.log(obj.grade); //undefined
console.log(Teacher.grade); //OK
```

#### 提升安全性
* 先声明后使用（避免变量提升），避免运行时出错
```
console.log(foo); //输出undefined
console.log(bar); //报错
var foo = 2;
let bar = 1;
```
* 避免重复声明，覆盖不确定性情况
```
var a = 0;
function aa()
{
	var a = 1;
	var a = 3;
	console.log(a);
	let a = 4; //不能通过
	{
		let a = 5; //可以通过
	}
}
aa();
function bb(arg)
{
	var arg = 5; //潜在隐患
	let arg = 5; //不能通过
	console.log(arg);
}
bb(4); //输出5
```
* 暂时性死区
```
var tmp = 2;
if(true)
{
	console.log(tmp);
	let tmp = 1; //不能通过，let将变量所在块作用域锁死，不允许重名情况出现
}
```
* 避免同名，内层覆盖外层
```
var tmp = 2;
function aa()
{
	console.log(tmp);
	if(false)
	{
		console.log(tmp); //undefined
		var tmp = 9; //let tmp = 9
	}
}
aa();
```
* 变量泄露
```
for(let i=0; i<3; i++)
{
	console.log(i);
}
console.log(i); //undefined
```
* 闭包（let可实现块作用域现场保护）
```
var a = [];
for(var i=0; i<10; i++) //let i
{
	a[i] = function()
	{
		console.log(i);
	}
}
console.log(i);
a[6]();
a[7]();
```

#### 块作用域，避免空间污染
```
if(true)
{
	var a = 1;
	let b = 2;
}
console.log(a,b); //b无法访问
function aa()
{
	{
		var a = 1;
		let b = 2;
	}
	console.log(a);
	console.log(b); //b无法访问
}
aa();
```
```
//匿名函数自执行
(function(){
	var tmp = 1;
})();
console.log(tmp);
//块作用域
{
	let tmp2 = 2;
}
console.log(tmp2);
//强制严格模式，强制ES6执行，才能使块作用域生效
"use strict"
{
	function aa(){}
}
aa();
```

#### const只读变量，支持块作用域
```
const size = 100;
console.log(size);
size = 88; //更改则报错，只读提升安全性
function fn(size)
{
	size = 5;
	console.log(size);
}
fn();
//对象指向地址，可更改
const obj = {name:"lzb"};
obj.name = "syn";
console.log(obj);
//支持块作用域
if(true)
{
	const name = 'lzb';
}
console.log(name);
```

#### 作业
```
1.用ES6来改写下面的ES5的原型。
function Point(x, y) {
this.x = x;
this.y = y;
}
Point.prototype.toString = function () {
return '(' + this.x + ', ' + this.y + ')';
};
var p = new Point(1, 2);
---
2. 下面输出结果是，即原因是什么？	及解决方法
class Student { 
constructor(age) {
this.age = age; 
}	
getAge(){console.log(this.age)} 
}	
var obj = new Student('ivan','female');
var funTemp = obj.getAge; 
funTemp(); 
---
3.说明下题的结果，及原因
{
let a =10 ;
var b = 1;
}
console.log(b);
console.log(a);
---
4.说明下题的结果，及原因
var a=[];
for(var i=0;i<10;i++){
a[i]=function(){
console.log(i)
}
}
a[6]();
var b=[];
for(let j=0;j<10;j++){
b[j]=function(){
console.log(j)
}
}
b[6]();
```

---
### D13 ES6-变量的解构赋值
#### 箭头函数
* 左边是参数=>右边是返回值
```
var num;
var fn = num => num + 1;
var fn1 = () => num + 1;
var fn2 = (x,y) => x + y;
var fn3 = (x,y) => {
	var sum = x + y;
	sum *= 2;
	return sum;
};
fn();
fn1();
```

* 解决了this丢失问题
```
//foo箭头函数安全
function foo(){
	setTimeout(()=>{
		console.log('id:',this.id);
	},100);
}
foo.call({id:42});
//fo的this丢失
function fo()
{
	setTimeout(function(){
		console.log('id2:',this.id);
	},1000)
}
fo.call({id:32});
```

#### 数组解构（智能匹配）
```
//多个变量赋值
var [a,b,c] = [1,'2','syn'];
var [,y,] = [1,2,3,4];
var [a,[b,c],d] = [1,[2,3],4];
//默认值
let [x,y=0] = [3];
var [x=1,y=x] = [2];
let [x=1,y=x] = [2,3];
let [x=y,y=1] = []; //undefined,1
//交互x,y的值
var [x,y] = [y,x];
//赋值
var [x=true] = [];
var [x,y='b'] = ['a']; //x='a',y='b'
var add = function(x){return x+1}
var [x=add,y] = [function(y){return y-1},2];
x(2);
```

#### 对象解构
```
var React = {
	name:'aaa',
	size:23,
}
var {
	name,size:len
} = React;
console.log(name,len);
```

#### 嵌套解构
```
var obj = {
	p:[
		'hello',
		{y:'world',z:34}
	]
}
var {
	p:[x,{y,z:n},m]
} = obj;
console.log(x,y,n,m);
```

#### 字符串解构
```
var [a,b,c,d,e] = 'hello';
console.log(a,b,c,d,e);
var {length:len} = 'hello';
console.log(len);
```

#### 函数解构
```
function add([x,y])
{
	console.log(x+y);
}
add([3,5]);
//ES6参数默认值设置
function setPrice(id=80,price=200)
{
	console.log(price)
}
setPrice(30,50)
setPrice();
//对象参数
function move({x=0,y=1})
{
	console.log(x,y);
}
move({x:30,y:60});
//不定参，扩展运算符
function sum(...a)
{
	for(var i=0;i<a.length;i++)
	{
		console.log(a[i]);
	}
}
sum(1,2,3,4)
function sum1(x,y,z)
{
	return x+y+z;
}
sum1(...[1,2,3]);
var a1 = [2,4], a2 = ['a','b'], a3 = [5,6];
var a4 = [...a1,...a2,...a3];
console.log(a4);
//返回多个值
function getPerson()
{
	return {
		name:"shiyanan",
		age:18,
		gender:"female"
	};
}
var obj = getPerson();
console.log(obj);
var {name,gender,age} = obj;
console.log(name,age,gender);
```

#### 作业
```
1. 下题输出结果是，并解释原因
(function(x, f = () => x) {
var x;
var y = x;
x = 2;
return [x, y, f()];
})(1)
---
2. 下题输出结果是，并解释原因
(function() {
return [
(() => this.x).bind({ x: 'inner' })(),
(() => this.x)()
]
}).call({ x: 'outer' });
---
3. 下题输出是多少
let [y = x,x = 2] = [6,];
console.log(x);
console.log(y);
---
4. 下题输出是多少，要输出5，怎么改。
function sum(x,y){
console.log(x+y);
}
sum([2,3]);
---
5. 下题输出是多少，并说出原因
var student = { 
name: "ivan",
age : 35,
city : 'chengdu',
}
var {
age, 
city, 
len, 
} = student;	
console.log(age);
console.log(len); 
---
6. 下题输出是多少，并说出原因
function getPerson() {
return {
name: 'ivan',
age: 30
};
}
var { age,name2 } = getPerson();
console.log(name2);
console.log(age);	
```

---
### D14 ES6-Map和Set数据结构、循环
#### 集合
1. Array
2. Object
3. Map 是键值对key-value的集合：Object的改进版（key可以是数值，查找快）
4. Set 是key的集合（无value）：Array的改进版（不重复）

#### Object遍历：key是字符串，查找慢
```
var obj = {name:'shiyanan',age:18}
for(var key in obj)
{
	console.log(typeof key);
}
```

#### Map遍历
```
var p = new Map([['name','shiyanan'],['age',30],[1,'lzb']]);
console.log(p);
console.log(p.get('name'));
console.log(p.get(1));
p.set('name',38);
p.set('school','qinghua');
p.delete('name');
console.log(p.get('school'));
console.log(p.has('age'));
console.log(p.has('name'));
p.set(8,333);
console.log(p.get(8));
for(let key of p.keys())
{
	console.log(key);
}
for(let value of p.values())
{
	console.log(value);
}
for(let item of p.entries())
{
	console.log(item);
}
```

#### Set遍历
```
var stu = ['lili','lucy','lzb','shiyanan',9527,9527];
var stu1 = new Set(['lili','lucy','lzb','shiyanan',9527,9527]); //不能重复
console.log(stu1);
for(var i of stu1.keys()) //只有key
{
	console.log(i);
}
```

#### for of遍历
1. for 缺陷（过于原始，编写麻烦）
2. forEach 回调 缺陷（只用于数组，不能break return）
3. for in 缺陷（用于数组不安全会将属性也遍历，且效率低）
4. for of 统一了遍历方法
```
//替代forEach
var age = [10,20,30,40];
age.forEach(
	function(v)
	{
		console.log(v*1.2);
	}
);
for(let v of age)
{
	function a(v)
	{
		console.log(v*1.2);
	}
	if(v>30)
	{
		break;
	}
	a(v);
}
//替代for in
var person = {
	name:'shiyanan',
	age:18,
	1:'lzb'
}
for(var k in person)
{
	console.log(k+' '+ person[k]);
}
for(let key of Object.keys(person)) //Object.keys迭代器iterator，字符串效率低
{
	console.log(key + ' type:' + typeof key + ' ' + person[key]);
}
```

#### 总结
1. ES6易用，安全，支持大型应用
2. import export 模块化
3. 类继承 class extends
4. let const 块作用域
5. 箭头函数，绑定了this
6. 解构赋值
7. 遍历，易用安全效率
