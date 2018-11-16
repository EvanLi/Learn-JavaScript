# 第1章、值，类型和运算符

* [数字](#%E6%95%B0%E5%AD%97)
* [算术](#%E7%AE%97%E6%9C%AF)
* [特殊数字](#%E7%89%B9%E6%AE%8A%E6%95%B0%E5%AD%97)
* [字符串](#%E5%AD%97%E7%AC%A6%E4%B8%B2)
* [一元运算符](#%E4%B8%80%E5%85%83%E8%BF%90%E7%AE%97%E7%AC%A6)
* [布尔值](#%E5%B8%83%E5%B0%94%E5%80%BC)
* [比较](#%E6%AF%94%E8%BE%83)
* [逻辑运算符](#%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97%E7%AC%A6)
* [空值](#%E7%A9%BA%E5%80%BC)
* [自动类型转换](#%E8%87%AA%E5%8A%A8%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2)
* [逻辑运算符的短路特性](#%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97%E7%AC%A6%E7%9A%84%E7%9F%AD%E8%B7%AF%E7%89%B9%E6%80%A7)

---

## 数字
```
13
9.81
2.998e8
```
## 算术
```
100 + 4 * 11
(100 + 4) * 11
314 % 100 //->14
```
## 特殊数字
在 JavaScript 中有三个特殊的值，它们虽然是数字，但看起来却跟一般的数字不太一样。

前两个是Infinity和-Infinity，它们代表正无穷和负无穷。 “无穷减一”仍然是“无穷”，依此类推。 尽管如此，不要过分信任基于无穷大的计算。 它在数学上不合理，并且很快导致我们的下一个特殊数字：NaN。
NaN代表“不是数字”，即使它是数字类型的值。 例如，当你尝试计算0/0（零除零），Infinity - Infinity或任何其他数字操作，它不会产生有意义的结果时，你将得到此结果。

## 字符串
```
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
"This is the first line\nAnd this is the second" //换行符 \n
"A newline character is written like \"\\n\"."  //转义字符
"con" + "cat" + "e" + "nate"  //字符串连接
`half of 100 is ${100 / 2}`  //$ {}中写入内容时，将计算其结果，转换为字符串并包含在该位置
```
## 一元运算符
```
console.log(typeof 4.5) //typeof运算符，会产生一个字符串的值，内容是给定值的具体类型。
// → number
console.log(typeof "x")
// → string
console.log(- (10 - 2)) //减号运算符既可用作一元运算符，也可用作二元运算符
// → -8
```
## 布尔值
布尔（Boolean）类型，它有两个值：true和false，它们就写成这些单词。
## 比较
```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
console.log("Aardvark" < "Zoroaster") //比较字符串时，JavaScript 从左向右遍历字符，逐个比较 Unicode 代码。
// → true
console.log("Apple" == "Orange")
// → false
console.log(NaN == NaN) //在 JavaScript 中，只有一个值不等于其自身，那就是NaN（Not a Number，非数值）。
// → false   // NaN用于表示非法运算的结果，正因如此，不同的非法运算结果也不会相等。
```
## 逻辑运算符
```
console.log(true && false)
// → false
console.log(true && true)
// → true
console.log(false || true)
// → true
console.log(false || false);
// → false
console.log(!true)
// → false
1 + 1 == 2 && 10 * 10 > 50 // 优先级：||优先级最低，其次是&&，接着是比较运算符（>，==等），最后是其他运算符。
console.log(true ? 1 : 2); // 条件运算符（或者有时候只是三元运算符，因为它是该语言中唯一的这样的运算符）。  
// → 1                     // 问号左侧的值“挑选”另外两个值中的一个。
console.log(false ? 1 : 2); //当它为真，它选择中间的值，当它为假，则是右边的值。
// → 2
```
## 空值

有两个特殊值，写成null和undefined，用于表示不存在有意义的值。 它们本身就是值，但它们没有任何信息。
在 JavaScript 语言中，有许多操作都会产生无意义的值（我们会在后面的内容中看到实例），这些操作会得到undefined的结果仅仅只是因为每个操作都必须产生一个值。

## 自动类型转换

在绝大多数情况下，JavaScript 只是将其中一个值转换成另一个值的类型。
```
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```
但如果运算符两侧存在null或undefined，那么只有两侧均为null或undefined(均为null、均为undefined、一个null一个undefined)时结果才为true。
```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```
当你不希望发生自动类型转换时，还有两个额外的运算符：===和!==。 第一个测试是否严格等于另一个值，第二个测试它是否不严格相等。 所以"" === false如预期那样是错误的。
我建议使用三字符比较运算符来防止意外类型转换的发生，避免作茧自缚。但如果比较运算符两侧的值类型是相同的，那么使用较短的运算符也没有问题。

## 逻辑运算符的短路特性

```
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
```

这两个运算符的另一个重要特性是，只在必要时求解其右侧的部分。 在true || X的情况下，不管X是什么 - 即使它是一个执行某些恶意操作的程序片段，结果都是true，并且X永远不会求值。 false && X也是一样，它是false的，并且忽略X。 这称为短路求值。