# 第2章、程序结构

* [表达式和语句](#%E8%A1%A8%E8%BE%BE%E5%BC%8F%E5%92%8C%E8%AF%AD%E5%8F%A5)
* [绑定](#%E7%BB%91%E5%AE%9A)
* [绑定名称](#%E7%BB%91%E5%AE%9A%E5%90%8D%E7%A7%B0)
* [环境](#%E7%8E%AF%E5%A2%83)
* [函数](#%E5%87%BD%E6%95%B0)
* [console\.log函数](#consolelog%E5%87%BD%E6%95%B0)
* [返回值](#%E8%BF%94%E5%9B%9E%E5%80%BC)
* [控制流](#%E6%8E%A7%E5%88%B6%E6%B5%81)
* [条件执行](#%E6%9D%A1%E4%BB%B6%E6%89%A7%E8%A1%8C)
* [for循环](#for%E5%BE%AA%E7%8E%AF)
* [while和do循环](#while%E5%92%8Cdo%E5%BE%AA%E7%8E%AF)
* [跳出循环](#%E8%B7%B3%E5%87%BA%E5%BE%AA%E7%8E%AF)
* [代码缩进](#%E4%BB%A3%E7%A0%81%E7%BC%A9%E8%BF%9B)
* [更新绑定的简便方法](#%E6%9B%B4%E6%96%B0%E7%BB%91%E5%AE%9A%E7%9A%84%E7%AE%80%E4%BE%BF%E6%96%B9%E6%B3%95)
* [switch条件分支](#switch%E6%9D%A1%E4%BB%B6%E5%88%86%E6%94%AF)
* [大写](#%E5%A4%A7%E5%86%99)
* [注释](#%E6%B3%A8%E9%87%8A)
* [习题](#%E4%B9%A0%E9%A2%98)
    * [LoopingaTriangle](#loopingatriangle)
    * [FizzBuzz](#fizzbuzz)
    * [棋盘](#%E6%A3%8B%E7%9B%98)

---

## 表达式和语句
我们把产生值的操作的代码片段称为表达式。按照字面含义编写的值（比如22或"psychoanalysis"）都是一个表达式。而括号当中的表达式、使用二元运算符连接的表达式或使用一元运算符的表达式，仍然都是表达式。
如果一个表达式对应一个句子片段，则 JavaScript 语句对应于一个完整的句子。 一个程序是一列语句。
最简单的一条语句由一个表达式和其后的分号组成。比如这就是一个程序：
```
1;
!false;
```
## 绑定
为了捕获和保存值，JavaScript 提供了一种称为绑定或变量的东西：
```
let ten = 10;
console.log(ten * ten);
// → 100
```

```
let mood = "light";
console.log(mood);
// → light
mood = "dark";
console.log(mood);
// → dark
```
```
let luigisDebt = 140;
luigisDebt = luigisDebt - 35;
console.log(luigisDebt);
// → 105
```
```
let one = 1, two = 2;  //一个let语句可以同时定义多个绑定，定义必需用逗号分隔。
console.log(one + two);
// → 3
```
var和const这两个词也可以用来创建绑定，类似于let。var（“variable”的简写）是 JavaScript 2015 之前声明绑定的方式。 我们在下一章中，会讲到它与let的确切的不同之处。 现在，请记住它大部分都做同样的事情，但我们很少在本书中使用它，因为它有一些令人困惑的特性。
```
var name = "Ayda";
const greeting = "Hello ";  // const这个词代表常量
console.log(greeting + name);
// → Hello Ayda
```
## 绑定名称
绑定名称可能包含美元符号（$）或下划线（_），但不包含其他标点符号或特殊字符。
具有特殊含义的词，如let，是关键字，它们不能用作绑定名称。 在未来的 JavaScript 版本中还有一些“保留供使用”的单词，它们也不能用作绑定名称。 关键字和保留字的完整列表相当长：
```
break case catch class const continue debugger default
delete do else enum export extends false finally for
function if implements import interface in instanceof let
new package private protected public return static super
switch this throw true try typeof var void while with yield
```
## 环境
给定时间中存在的绑定及其值的集合称为环境。 当一个程序启动时，这个环境不是空的。 它总是包含作为语言标准一部分的绑定，并且在大多数情况下，它还具有一些绑定，提供与周围系统交互的方式。 例如，在浏览器中，有一些功函数能可以与当前加载的网站交互并读取鼠标和键盘输入。
## 函数
```
prompt("Enter passcode");  //绑定prompt包含一函数，个显示一个小对话框，请求用户输入
```
## console.log函数
```
let x = 30;
console.log("the value of x is", x);
// → the value of x is 30
```
console.log不是一个简单的绑定。 它实际上是一个表达式，它从console绑定所持有的值中检索log属性。 我们将在第 4 章中弄清楚这意味着什么。
## 返回值
```
console.log(Math.max(2, 4));
// → 4
console.log(Math.min(2, 4) + 100); //Math.min的调用用作加法表达式的一部分
// → 102
```
## 控制流
```
// 直线控制流程
let theNumber = Number(prompt("Pick a number")); //Number函数将一个值转换为一个数字,类似的函数还有String和Boolean
console.log("Your number is the square root of " +
    theNumber * theNumber);
```
## 条件执行
```
let theNumber = Number(prompt("Pick a number"));
if (!isNaN(theNumber)) //Number.isNaN是一个标准的JavaScript 函数，仅当它给出的参数是NaN时才返回true
    alert("Your number is the square root of " +
        theNumber * theNumber);
```
```
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
    console.log("Your number is the square root of " +
        theNumber * theNumber);
} else {
    console.log("Hey. Why didn't you give me a number?");
}
```
```
let num = Number(prompt("Pick a number", "0"));

if (num < 10) {
    console.log("Small");
} else if (num < 100) {
    console.log("Medium");
} else {
    console.log("Large");
}
```
## for循环
```
for (let number = 0; number <= 12; number = number + 2) // 输出0,2,4,...,12
    console.log(number);
// → 0
// → 2
//   … etcetera
```
```
var result = 1; // 计算2的10次方
for (var counter = 0; counter < 10; counter = counter + 1)
    result = result * 2;
console.log(result);
// → 1024
```
## while和do循环
while循环语句
以关键字while开头，在关键字while后紧跟一个用括号括起来的表达式，括号后紧跟一条语句，这种形式与if语句类似。
```
let number = 0;
while (number <= 12) {
    console.log(number);
    number = number + 2;
}
// → 0
// → 2
//   … etcetera
```

```
let result = 1;
let counter = 0;
while (counter < 10) {
    result = result * 2;
    counter = counter + 1;
}
console.log(result);
// → 1024
```
do循环语句
至少执行一遍循环体，只有第一次执行完循环体之后才会开始检测循环条件
```
let yourName; //这个程序会强制你输入一个名字。 它会一再询问，直到它得到的东西不是空字符串。
do {
    yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

## 跳出循环
除了循环条件为false时循环会结束以外，我们还可以使用一个特殊的break语句来立即跳出循环。
下面的程序展示了break语句的用法。
```
for (let current = 20; ; current++) {  //找出第一个大于等于 20 且能被 7 整除的数字
    if (current % 7 == 0) {
        console.log(current);
        break;
    }
}
// → 21
```
continue关键字与break类似，也会对循环执行过程产生影响。循环体中的continue语句可以跳出循环体，并进入下一轮循环迭代。

## 代码缩进

块内缩进的作用是使代码结构显而易见。 在其他块内开启新的代码块中，可能很难看到块的结束位置，和另一个块开始位置。 通过适当的缩进，程序的视觉形状对应其内部块的形状。 但每个人的风格不同 - 有些人使用两个空格，有些人使用四个空格，而有些人使用制表符。 重要的是，每个新块添加相同的空格量。

```
if (false != true) {
    console.log("That makes sense.");
    if (1 < 2) {
        console.log("No surprise there.");
    }
}
```
## 更新绑定的简便方法
```
counter = counter + 1;
counter += 1;
counter++;
counter -= 1;
counter--;
result = result * 2;
result *= 2;
```
## switch条件分支
```
switch (prompt("What is the weather like?")) {
    case "rainy":
        console.log("Remember to bring an umbrella."); break;
    case "sunny":
        console.log("Dress lightly.");
    case "cloudy":
        console.log("Go outside."); break;
    default:
        console.log("Unknown weather type!"); break;
}
```
你可以在switch打开的块内放置任意数量的case标签。 程序会在向switch提供的值的对应标签处开始执行，或者如果没有找到匹配值，则在default处开始。 甚至跨越了其他标签，它也会继续执行，直到达到了break声明。 在某些情况下，例如在示例中的"sunny"的情况下，这可以用来在不同情况下共享一些代码（它建议在晴天和多云天气外出）。 但要小心 - 很容易忘记这样的break，这会导致程序执行你不想执行的代码。
## 大写
```
fuzzyLittleTurtle
```
要习惯这样的小事并不困难，而且混合命名风格的代码可能会让人反感，所以我们遵循这个约定。
标准的 JavaScript 函数和大多数 JavaScript 程序员都遵循最底下的风格 - 除了第一个词以外，它们都会将每个词的首字母大写（驼峰命名法）。 
在极少数情况下，绑定名首字母也会大写，比如Number函数。这种方式用来表示该函数是构造函数。我们会在第6章详细讲解构造函数的概念。现在，我们没有必要纠结于表面上的风格不一致性。
## 注释
```
let accountBalance = calculateBalance(account); //单行注释时，使用两个斜杠字符开头
// It's a green hollow where a river sings
accountBalance.adjust();
// Madly catching white tatters in the grass.
let report = new Report();
// Where the sun on the proud mountain rings:
addToReport(accountBalance, report);
// It's a little valley, foaming like light in a glass.
```
```
/*
 I first found this number scrawled on the back of one of
 an old notebook. Since then, it has often dropped by,
 showing up in phone numbers and the serial numbers of
 products that I've bought. It obviously likes me, so I've
 decided to keep it.
*/
const myNumber = 11213; // 多行注释，/*和*/之间的一段文本将被忽略
```
## 习题
### LoopingaTriangle
编写一个循环，调用 7 次console.log函数，打印出如下的三角形：
```
#
##
###
####
#####
######
#######
```
这里给出一个小技巧，在字符串后加上.length可以获取字符串的长度。
```
let abc = "abc";
console.log(abc.length);
// → 3
```

**解答1：**
```
for (let line = "#"; line.length < 8; line += "#")
  console.log(line);
```
### FizzBuzz
编写一个程序，使用console.log打印出从 1 到 100 的所有数字。不过有两种例外情况：当数字能被 3 整除时，不打印数字，而打印"Fizz"。当数字能被 5 整除时（但不能被 3 整除），不打印数字，而打印"Buzz"。
当以上程序可以正确运行后，请修改你的程序，让程序在遇到能同时被 3 与 5 整除的数字时，打印出"FizzBuzz"。

（这实际上是一个面试问题，据说剔除了很大一部分程序员候选人，所以如果你解决了这个问题，你的劳动力市场价值就会上升。）

**解答2：**
```
for (let n = 1; n <= 100; n++) {
    let output = "";
    if (n % 3 == 0) output += "Fizz";
    if (n % 5 == 0) output += "Buzz";
    console.log(output || n);
}
```

```
for (let n = 1; n <= 100; n++) {
    let output = "";
    if (n % 3 == 0) output = "Fizz";
    if (n % 5 == 0) output = "Buzz";
    if (n % 3 == 0 && n % 5 == 0) output = "FizzBuzz";
    console.log(output || n);
}
```
### 棋盘
编写一个程序，创建一个字符串，用于表示8×8的网格，并使用换行符分隔行。网格中的每个位置可以是空格或字符"#"。这些字符组成了一张棋盘。
将字符串传递给console.log将会输出以下结果：
```
 # # # #
# # # #
 # # # #
# # # #
 # # # #
# # # #
 # # # #
# # # #
```
当程序可以产生这样的输出后，请定义绑定size=8，并修改程序，使程序可以处理任意尺寸（长宽由size确定）的棋盘，并输出给定宽度和高度的网格。

**解答3：**
```
let size = 8;

let board = "";

for (let y = 0; y < size; y++) {
    for (let x = 0; x < size; x++) {
        if ((x + y) % 2 == 0) {
            board += " ";
        } else {
            board += "#";
        }
    }
    board += "\n";
}

console.log(board);
```