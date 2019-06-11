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
//for in用于遍历对象的键值，不用于数组的遍历
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

1. 变量声明定义
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

2. 变量赋值，无声明定义
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

3. 定义声明的提升
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

4. 变量删除
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

5. 块作用域
```
if(true)
{
	//不支持块作用域{}
}
```

6. 作用域链
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

7. 提升作用域范围：with
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

8. 匿名函数自执行
```
(function(){
	var a = b = 3;
})();
```

---
### D6 闭包
> [扩展学习](https://www.cnblogs.com/onepixel/p/5062456.html)
---
### D7 数组对象
---
### D8 字符串与正则表达式
---
### D9 内建对象和函数对象
---
### D10 原型
---
### D11 ES6-概述
---
### D12 ES6面向对象、let和const
---
### D13 ES6-变量的解构赋值
---
### D14 ES6-Map和Set数据结构、循环