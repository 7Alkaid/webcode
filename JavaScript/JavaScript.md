# JavaScript
- [JavaScript](#javascript)
  - [基本语法](#基本语法)
    - [数据类型](#数据类型)
    - [变量、内存、数据](#变量内存数据)
  - [语句结构](#语句结构)
  - [对象、数组、函数](#对象数组函数)
    - [对象](#对象)
    - [数组](#数组)
    - [函数](#函数)
  - [Dom](#dom)
  - [Bom](#bom)
  
  


## 基本语法
### 数据类型
- 基本类型
```
number     任意数值
string     任意字符串
Boolean    true/false
undefined  undefined
 ```
- 引用类型
```
object     任意对象
function   特别对象（可执行）
array      特别对象（内部数据有序/数据下标）
```
- 判断
```
typeof（判断数据类型）
1、返回值为：number、string、boolean、undefined、function
2、不能区别：null与object 、 object与arry

instanceof（判断对象的具体类型）
- 返回值为：true/false
```
- 相关问题
```
undefined与null的区别：
undefined 表示一个变量自然的、最原始的状态值，而 null 则表示一个变量被人为的设置为空对象，而不是原始状态。所以，在实际使用过程中，为了保证变量所代表的语义，不要对一个变量显式的赋值 undefined，当需要释放一个对象时，直接赋值为 null 
```
### 变量、内存、数据
- 数据：存储在内存中代表特定信息的东西
- 变量：每个变量都对应的一块小内存，变量名用来查找对应的内存，变量值就是内存中保存的数据
- 内存：内存条通电后产生的可存储数据的空间

`三者的关系：变量是内存的标识，我们通过找到对应的内存，进而操作内存中的数据`

- 相关问题
```
- 关于引用标量赋值问题：
两个引用变量指向同一个对象，通过一个变量修改对象内部数据，另一个变量看到的是修改之后的数据
两个引用变量指向同一个对象，让其中一个引种变量指向另一个对象，另一个引用变量依然指向前一个对象

- js在调用函数时传递变量参数时，是值传递还是引用传递：
理解一：都是值（基本值和地址值）传递
理解二：可能是值传递，也可能是引用传递（地址值）

- js引擎如何管理内存
内存的生命周期：先分配内存空间得到使用权-->存储数据，进行反复操作-->释放内存空间
释放内存有两种情况：
1、局部变量：函数执行完自动释放
2、对象：成为垃圾对象-->垃圾回收器回收

```

## 语句结构
- 选择结构

```
- if 句法：
if(条件表达式)
{
  代码段
}
else if（条件表达式）
{
  代码段
}
else
{
  代码段
}

- switch 句法：
switch（条件表达式）
{
  case 标签1： 代码段1； break；
  case 标签2： 代码段2； break；
  default：代码段n；
}
```
- 循环语句

```
- while 句法：
while（条件表达式）
{
  循环代码段
}

- do-while 句法：
do{
  循环代码段
}while（条件表达式）

！！ while先检查条件再执行循环，do-while先循环再执行条件

- for 句法：
for（循环变量=初值；循环条件；递增/递减）
{
  循环代码段
}

- for in 句法：
for（声明变量 in 对象）
{
  代码段
}

```

- 跳转语句

```
- return   终止函数体运行，并返回一个值

- break    终止整个循环，不再进行判断

- continue 结束本次循环，接着去判断是否执行下次循环
```

## 对象、数组、函数
### 对象
- 对象的概念  

`对象是一组无序的相关属性和方法 的集合，所有的事务都是对象，如字符串、数值、数组、函数等`   

- 对象的组成

```
对象由属性和方法组成
属性：属性名（字符串）和属性值（任意）组成
方法：一种特别的属性（属性值是函数）
```

- 对象分类

```
- 内置对象：
由ES标准中定义的对象，在任何的ES实现中都可以使用
比如，Math、String、Number、BOOlean、Function、Object.....

- 宿主对象：
由JS运行环境提供对象，目前来讲主要指由浏览器提供的对象
比如，Bom、DOM

- 自定义对象：
由开发人员自己创建的对象
```

- 对象属性

```
- in运算符
通过该运算符可以检查一个对象中是否含有指定属性，有返回true，否则返回false      ## 包含自身以及上一级作用域
语法：
“属性名” in 对象  ； console.log（“text” in obj）；

- hasOwnProperty运算符
可以使用的hasOwnProperty（）中检查对象自身中是否含有该属性
```
### 数组
- 数组也是一个对象
- 数组创建方法

```
空数组  var obj = new Array();
指定长度数组  var obj = new Array(size);
指定元素数组  var obj = new Array(元素1，元素2，元素3.....);
单维数组      var obj = [元素1，元素2，元素3];
多维数组      var obj = new Array([数组序列1],[数组序列2],[数组序列n]);

```
- 数组方法

```
length()    获取数组长度

push()      该方法可以向数组末尾添加一个或多个元素，并返回数组的新长度

pop()       该方法可以删除数组的最后一个元素，并将被删除的元素作为返回值返回

unshift()   向数组开头添加一个或更多元素，并返回新的长度

shift()     删除并返回数组的第一个元素

```
更多的方法可参考[链接](https://www.w3school.com.cn/jsref/jsref_obj_array.asp)
### 函数
- 函数也是一个对象


- 什么是函数

`实现特定功能的n条语句的封装体 `

- 定义方法

```
- 静态方法
function 函数名（形参列表）
{
  函数体；
  return（返回值）；
}

- 动态匿名方法
var 函数名 = new function （形参列表）

- 直接量方法
函数名 = function（形参列表）{函数体}；

```

- 调用方法
```
- 直接调用
函数名（实参列表）

- 通过对象调用
obj.函数名（）

- 在连接中调用
<a href = "javascript:函数名()">文字</a>

- 在事件中调用
事件类型 = "函数名()"

- 递归调用
定义：在函数内部调用函数自身
格式：
function 函数名()
{
  代码
  函数名();
}

```

- 方法

```
- apply 将函数作为对象的方法来调用，将参数以数组形式传递给该方法

- call  将函数作为对象的方法来调用，讲指定参数传递给该方法

！！ call和apply都可以改变this的指向

- tostring 返回函数的字符串表示
```

- arguments对象

```
- 功能：
存放实参的参数列表

- 特性：
仅能在函数体内使用
带有下标属性，但并非数组
函数声明时自动初始化

-属性：
length：获取函数实参长度
callee：返回当前正在指向的函数
caler： 返回调用当前正在执行函数的函数名
```

- 指针标识

```
- this：指向当前操作对象

- callee：指向参数集合所属函数

- prototype：指向函数附带的原型对象

- constructor：指向创建该对象的构造函数
```
## Dom
- DOM全称 文档对象模型
- 常用节点node分为四类

```
文档节点： 整个html文档
元素节点： html文档中的html标签
属性节点： 元素属性
文本节点： html标签中的文本内容
```

- 获取节点

```
- document
document.getElementById(元素ID)         通过元素id获取节点
document.getElementByName(元素name属性) 通过元素name属性获取节点
document.getElementByTagName(元素标签)  通过元素标签获取节点

- 父节点
父节点.firstChild  获取元素的首个子节点
父节点.lastChild   获取元素的最后一个字节点
父节点.childNodes  获取元素子节点列表

- 兄弟节点
兄弟节点.previousSibling  获取已知节点的前一个节点
兄弟节点.nextSibling      获取已知节点的后一个节点

-子节点
子节点.parentNode  获取已知节点的父节点
```

- 节点操作

```
- 创建节点
document.createElement(元素标签)   创建元素节点
document.createAttribute(元素属性) 创建属性节点
document.createTextNode(文本内容)  创建文本节点

- 插入节点
appendChild（所添加的新节点）                向节点的子节点列表的末尾添加新的子节点
insertBefore（所要添加的新节点，已知子节点）  在已知的子节点前插入一个新的子节点

- 替换节点
replaceChild（要插入的新元素，将被替换的老元素）   将某个子节点替换为另一个

- 复制节点
需要被复制的节点.cloneNode(true/false)  创建指定节点副本
参数：
true  复制当前节点及所有子节点
false 仅复制当前节点

-删除节点
removeChild（要删除的节点）  删除指定节点
```
## Bom
- Bom全称 浏览器对象模型

- window对象

`window对象是BOM的核心，window对象代表的是整个浏览器窗口，同时也是网页中的全局对象 `

- History对象

```
定义：history对象记录了用户曾经浏览过的页面（URL），并可以实现浏览器前进与后退相似导航的功能

语法：window.history.[属性/方法]，window可以省略

返回上一个页面：
window.history.back();
window.history.go(-1);
返回下一个页面：
window.history.forward();
window.history.go(1);

返回浏览历史中的其他页面：
window.history.go(number);
```

- location对象

```
定义：location用于获取或设置窗体的URL，并且用于解析URL
语法：location[属性/方法]

var url = location.href  获取当前url
```

- navigator对象

```
定义：navigator对象包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本

var browser = navigator.appName       返回浏览器名称  

var platform = navigator.platform     返回操作系统平台

var platform = navigator.appVersion   返回浏览器的平台和版本信息
```

- userAgent对象

```
定义：返回用户代理的字符串表示
语法：navigator.userAgent
```

- screen对象

```
定义：screen对象用于获取用户的屏幕信息
语法：window.screen.属性

screen.height   返回屏幕分辨率的高
screen.width    返回屏幕分辨率的宽

```