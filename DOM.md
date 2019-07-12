## DOM 教程
> ##### 文档对象模型（Document Object Model）是W3C的标准。
> ##### 它定义了访问HTML和XML文档的标准方法。
> ##### DOM将HTML和XML文档表达为树结构，而树叶被定义为节点。
> #### HTML DOM 树
> ![HTML DOM 树](http://www.w3school.com.cn/i/ct_htmltree.gif)
> #### XML DOM 树
> ##### XML指可扩展标记语言，被设计用来传输和存储数据。
> ![XML DOM 树](http://www.w3school.com.cn/i/ct_nodetree1.gif)

---
### 1 DOM简介
#### 什么是 XML DOM？
* XML DOM 定义了所有 XML 元素的对象和属性，以及访问它们的方法。
> [XML DOM 教程](http://www.w3school.com.cn/xmldom/index.asp)

#### 什么是 HTML DOM？
##### HTML DOM 是：
* HTML 的标准对象模型
* HTML 的标准编程接口
* W3C 标准
###### HTML DOM 定义了所有 HTML 元素的对象和属性，以及访问它们的方法。
> 换言之，HTML DOM 是关于如何获取、修改、添加或删除 HTML 元素的标准。

---
### 2 DOM节点
#### 在 HTML DOM 中，所有事物都是节点。DOM 是被视为节点树的 HTML。
> HTML 文档中的所有内容都是节点：
* 整个文档是一个文档节点
* 每个 HTML 元素是元素节点
* HTML 元素内的文本是文本节点
* 每个 HTML 属性是属性节点
* 注释是注释节点
* 通过 HTML DOM，树中的所有节点均可通过 JavaScript 进行访问。
* 所有 HTML 元素（节点）均可被修改，也可以创建或删除节点。

#### 节点父、子和同胞
> 节点树中的节点彼此拥有层级关系。
>
> 父（parent）、子（child）和同胞（sibling）等术语用于描述这些关系。父节点拥有子节点。同级的子节点被称为同胞（兄弟或姐妹）。
* 在节点树中，顶端节点被称为根（root）
* 每个节点都有父节点、除了根（它没有父节点）
* 一个节点可拥有任意数量的子节点
* 同胞是拥有相同父节点的节点

```
<html>
  <head>
    <title>DOM 教程</title>
  </head>
  <body>
    <h1>DOM 第一课</h1>
    <p>Hello world!</p>
  </body>
</html>
```

---
### 3 HTML DOM方法
##### 一些常用的 HTML DOM 方法：
* getElementById(id) - 获取带有指定 id 的节点（元素）
* appendChild(node) - 插入新的子节点（元素）
* removeChild(node) - 删除子节点（元素）

|方法						|描述														|
|--							|--															|
|getElementById()			|返回带有指定 ID 的元素。										|
|getElementsByTagName()		|返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）。	|
|getElementsByClassName()	|返回包含带有指定类名的所有元素的节点列表。						|
|appendChild()				|把新的子节点添加到指定节点。									|
|removeChild()				|删除子节点。													|
|replaceChild()				|替换子节点。													|
|insertBefore()				|在指定的子节点前面插入新的子节点。								|
|createAttribute()			|创建属性节点。												|
|createElement()			|创建元素节点。												|
|createTextNode()			|创建文本节点。												|
|getAttribute()				|返回指定的属性值。											|
|setAttribute()				|把指定属性设置或修改为指定的值。								|

---
### 4 HTML DOM属性
#### 一些常用的 HTML DOM 属性：
* innerHTML - 节点（元素）的文本值
* parentNode - 节点（元素）的父节点
* childNodes - 节点（元素）的子节点
* attributes - 节点（元素）的属性节点

#### nodeName 属性
> nodeName 属性规定节点的名称。

* nodeName 是只读的
* 元素节点的 nodeName 与标签名相同
* 属性节点的 nodeName 与属性名相同
* 文本节点的 nodeName 始终是 #text
* 文档节点的 nodeName 始终是 #document
* 注释：nodeName 始终包含 HTML 元素的大写字母标签名。

#### nodeValue 属性
> nodeValue 属性规定节点的值。

* 元素节点的 nodeValue 是 undefined 或 null
* 文本节点的 nodeValue 是文本本身
* 属性节点的 nodeValue 是属性值

#### nodeType 属性
> nodeType 属性返回节点的类型。nodeType 是只读的。

|元素类型|nodeType|
|--|--|
|元素|1|
|属性|2|
|文本|3|
|注释|8|
|文档|9|

---
### 5 HTML DOM访问
> 访问 HTML 元素等同于访问节点

##### 您能够以不同的方式来访问 HTML 元素：
* 通过使用 getElementById() 方法
* 通过使用 getElementsByTagName() 方法
* 通过使用 getElementsByClassName() 方法
> 注释：getElementsByClassName() 在 Internet Explorer 5,6,7,8 中无效。

---
### 6 HTML DOM修改
##### 修改 HTML DOM 意味着许多不同的方面：
* 改变 HTML 内容
* 改变 CSS 样式
* 改变 HTML 属性
* 创建新的 HTML 元素
* 删除已有的 HTML 元素
* 改变事件（处理程序）

```
<div id="d1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>

<script>
var para=document.createElement("p");
var node=document.createTextNode("This is new.");
para.appendChild(node);

var element=document.getElementById("d1");
element.appendChild(para);
</script>
```

---
### 7 HTML DOM内容
#### 改变 HTML 内容
```
<html>
<body>
<script type="text/javascript">
document.write("Hello World!");
document.writeln("Hello World! ","Hello You! ","<p style='color:blue;'>Hello World!</p>")
</script>
</body>
</html>
```

```
<html>
<body>
<p id="p1">Hello World!</p>
<script>
document.getElementById("p1").innerHTML="New text!";
</script>
</body>
</html>
```

#### 改变 HTML 样式
```
<html>
<body>
<p id="p2">Hello world!</p>
<script>
document.getElementById("p2").style.color="blue";
</script>
</body>
</html>
```

#### 使用事件
```
<html>
<body>
<input type="button" onclick="document.body.style.backgroundColor='lavender';" value="Change background color" />
</body>
</html>
```

```
<html>
<body>
<script>
function ChangeBackground()
{
document.body.style.backgroundColor="lavender";
}
</script>
<input type="button" onclick="ChangeBackground()" value="Change background color" />
</body>
</html>
```

```
<html>
<body>
<p id="p1">Hello world!</p>
<script>
function ChangeText()
{
document.getElementById("p1").innerHTML="New text!";
}
</script>
<input type="button" onclick="ChangeText()" value="Change text">
</body>
</html>
```

---
### 8 HTML DOM元素
#### 创建新的 HTML 元素 - appendChild()
```
<div id="div1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>
<script>
var para=document.createElement("p"); //这段代码创建了一个新的 <p> 元素：
var node=document.createTextNode("This is new."); //如需向 <p> 元素添加文本，您首先必须创建文本节点。这段代码创建文本节点：
para.appendChild(node); //然后您必须向 <p> 元素追加文本节点：
var element=document.getElementById("div1"); //这段代码查找到一个已有的元素：
element.appendChild(para); //这段代码向这个已存在的元素追加新元素：
</script>
```

#### 创建新的 HTML 元素 - insertBefore()
```
<div id="div1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>
<script>
var para=document.createElement("p");
var node=document.createTextNode("This is new.");
para.appendChild(node);
var element=document.getElementById("div1");
var child=document.getElementById("p1");
element.insertBefore(para,child); //在指定子节点前添加新节点。
</script>
```

#### 删除已有的 HTML 元素 - removeChild()
```
//这个 HTML 文档包含一个带有两个子节点（两个 <p> 元素）的 <div> 元素：
<div id="div1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>
<script>
var parent=document.getElementById("div1"); //查找 id="div1" 的元素：
var child=document.getElementById("p1"); //查找 id="p1" 的 <p> 元素：
parent.removeChild(child); //删除已有的 HTML 元素
</script>
```

#### 替换 HTML 元素 - replaceChild()
```
<div id="div1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>

<script>
var para=document.createElement("p");
var node=document.createTextNode("This is new.");
para.appendChild(node);

var parent=document.getElementById("div1");
var child=document.getElementById("p1");
parent.replaceChild(para,child); //替换 HTML 元素
</script>
```

---
### 9 HTML DOM事件
> 对事件作出反应
> 当事件发生时，可以执行 JavaScript，比如当用户点击一个 HTML 元素时。

#### HTML 事件的例子：
* 当用户点击鼠标时 onmousedown onmouseup onclick
* 当用户触摸屏幕时 ontouchstart ontouchend
* 当网页已加载时 onload onunload
* 当图片已加载时 onload
* 当鼠标移动到元素上时 onmouseover onmouseout
* 当输入字段被改变时 onchange
* 当 HTML 表单被提交时 onsubmit
* 当用户触发按键时 onkeyup onkeydown onkeypress
* 元素获得和失去焦点 onfocus onblur

#### JQuery中阻止冒泡常用到的有以下3个方法：
1. event.stopPropagation(); 只阻止了冒泡事件， 默认行为没有阻止
2. event.preventDefault(); 只阻止了默认事件，冒泡事件没有阻止
3. return false; 冒泡事件和默认事件都阻止

```
//HTML 事件属性 onclick=JavaScript
<!DOCTYPE html>
<html>
<body>
<h1 onclick="this.innerHTML='hello!'">请点击这段文本!</h1>
</body>
</html>
//从事件处理程序中调用函数
<!DOCTYPE html>
<html>
<head>
<script>
function changetext(id)
{
id.innerHTML="hello!";
}
</script>
</head>
<body>
<h1 onclick="changetext(this)">请点击这段文本!</h1>
</body>
</html>
//使用 HTML DOM 来分配事件
//为 button 元素分配 onclick 事件：
<script>
document.getElementById("myBtn").onclick=function(){displayDate()};
</script>
```

```
<html>
<head>
<script type="text/javascript">
function getEventTrigger(event)
{ 
  x=event.target; 
  alert("The id of the triggered element: " + x.id);
}
</script>
</head>
<body>
<p id="p1" onmousedown="getEventTrigger(event)">
Click on this paragraph. An alert box will
show which element triggered the event.</p>
</body>
</html>
```

---
### 10 HTML DOM导航
#### HTML DOM 节点列表
* getElementsByTagName() 方法返回节点列表。节点列表是一个节点数组。

```
var x=document.getElementsByTagName("p"); //获取所有 <p> 元素节点
y=x[1];
for (i=0;i<x.length;i++)
{
document.write(x[i].innerHTML); //输出每个 <p> 元素的文本节点的值
document.write("<br />");
}
```

#### 导航节点关系
> 您能够使用三个节点属性：parentNode、firstChild 以及 lastChild ，在文档结构中进行导航。

```
<html>
<body>
<p>Hello World!</p>
<div>
  <p>DOM 很有用!</p>
  <p>本例演示节点关系。</p>
</div>
</body>
</html>
<!--
首个 <p> 元素是 <body> 元素的首个子元素（firstChild）
<div> 元素是 <body> 元素的最后一个子元素（lastChild）
<body> 元素是首个 <p> 元素和 <div> 元素的父节点（parentNode）
-->
```

```
<html>
<body>
<p id="intro">Hello World!</p>
<script>
x=document.getElementById("intro");
document.write(x.firstChild.nodeValue);
</script>
</body>
</html>
```

#### DOM 根节点
> 有两个特殊的属性，可以访问全部文档：
> 
> document.documentElement - 全部文档
> 
> document.body - 文档的主体

```
<html>
<body>
<p>Hello World!</p>
<div>
<p>DOM 很有用!</p>
<p>本例演示 <b>document.body</b> 属性。</p>
</div>
<script>
alert(document.body.innerHTML);
</script>
</body>
</html>
```

#### childNodes 和 nodeValue
> 除了 innerHTML 属性，您也可以使用 childNodes 和 nodeValue 属性来获取元素的内容。

```
<html>
<body>
<p id="intro">Hello World!</p>
<script>
//getElementById 是一个方法，而 childNodes 和 nodeValue 是属性。
var txt=document.getElementById("intro").childNodes[0].nodeValue;
document.write(txt);
</script>
</body>
</html>
```

---
### 11 实例
