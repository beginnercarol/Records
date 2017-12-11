# JS ...rest 和 ...spread 和 解构赋值(destructing)

## ...rest 剩余参数

剩余参数语法将 一个不定数量的 参数 表示为一个数组
**剩余参数必须是最后一个**
> 如果函数的最后一个命名参数以...为前缀，则它将成为一个数组

+ 剩余参数和 arguments对象之间的区别主要有三个：
	+ 剩余参数只包含那些没有对应形参的实参，而 arguments 对象包含了传给函数的所有实参。
	+ arguments对象不是一个真正的数组，而剩余参数是真正的 Array实例，也就是说你能够在它上面直接使用所有的数组方法，比如 sort，map，forEach或pop。
	+ arguments对象对象还有一些附加的属性 （如callee属性）。

	
## 扩展语句

> 扩展语法允许一个表达式在期望多个参数（用于函数调用）或多个元素（用于数组字面量）或多个变量（用于解构赋值）的位置扩展。

+ 即原本是数组使用`...arr`之后就变成了单个的参数
+ 可以像 `arr.slice()` 一样复制整个数组


> 扩展运算符可以将一个类数组对象中索引范围在[0,length)之间的所有属性的值添加到一个数组中,这样就可以得到一个真正的数组.

## 结构赋值

> 解构赋值语法是一个 Javascript 表达式，这使得可以将值从数组或属性从对象提取到不同的变量中。

+ 对象字面量和数组字面量:
`let x = [1,2,3];`
+ 解构赋值的语法是相同的,只是**在表达式左边定义了要从原变量中取出什么变量.

```
var x = [1,2,3,4];
var [y,z] = x;
//y=1,z=2
```

+ 可以使用这样的语法来对变量进行赋值
+ 可以交换变量:`[a,b]=[b,a];`
+ 忽略不感兴趣的值:`[a, ,b]=[1,2,3];`
+ 与正则提取结合食用效果最佳:

```
var url = "https://developer.mozilla.org/en-US/Web/JavaScript";

var parsedURL = /^(\w+)\:\/\/([^\/]+)\/(.*)$/.exec(url);
console.log(parsedURL); // ["https://developer.mozilla.org/en-US/Web/JavaScript", "https", "developer.mozilla.org", "en-US/Web/JavaScript"]

var [, protocol, fullhost, fullpath] = parsedURL;

console.log(protocol); // "https"
```


+ Object destructuring
	+ 通常要给一个对象赋值可以用下面的方式:

	```
	var o = {p:42,q:32};
	var {p,q} = o;
	```

	+ 使用解构赋值可以在不声明对象变量的情况下赋值:

	```
	var a,b;
	({a,b} = {a:12,b:32});
	```
	

		+ 必须有`()`
		+ 右边的a 和 b 才是上面用 var 声明的












