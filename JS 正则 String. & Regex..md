# JS 正则 String. & Regex.

## String

### str.match(regexp)

如果有匹配,返回 包含 完全匹配的 string 作为 数组的**首项** 接下来是括号表达式匹配的内容;
注意:若没有使用参数,只匹配第一个!!!
否则,返回 `null`;

> 如果正则表达式没有 g 标志，则 str.match() 会返回和 RegExp.exec() 相同的结果。而且返回的 Array 拥有一个额外的 input 属性，该属性包含被解析的原始字符串。另外，还拥有一个 index 属性，该属性表示匹配结果在原字符串中的索引（以0开始）。
> 如果正则表达式包含 g 标志，则该方法返回一个 Array ，它包含所有匹配的子字符串而不是匹配对象。捕获组不会被返回(即不返回index属性和input属性)。如果没有匹配到，则返回  null 。

### str.search(regexp)

返回 第一个匹配的 index;
否则 返回 -1;


## str.split

## str.replace

如果 replace 是全局的话, function 会自动应用到每一个匹配项中


## Regexp

### reg.exec()

返回一个`array`  并更新 reg 的属性

`var myArr = myRe.exec("hello");`

正则表达式的属性:
+ myArr:
	+  [0] : 匹配到的所有字符串
	+  [1],...[n] : 括号中的分组捕获
	+  index : 匹配部分的索引
	+  inout : 原始字符串
+ myRe:
	+ lastIndex : 下一个匹配开始的索引值(只在参数为 g 时可用)
	+ source : 模式文本


当使用 g 时,可以多次匹配寻找所有的匹配

```
var myRe = /ab*/g;
var str = 'abbcdefabh';
var myArray;
while ((myArray = myRe.exec(str)) !== null) {
  var msg = 'Found ' + myArray[0] + '. ';
  msg += 'Next match starts at ' + myRe.lastIndex;
  console.log(msg);
}
```

因为 myRe 会保存每一次的 lastIndex 所以可以一直找下去

但是千万不能把正则表达式放在 while 的条件中,由于每次迭代时 lastIndex的属性都被重置，如果匹配，将会造成一个死循环。并且要确保使用了'g'标记来进行全局的匹配，否则同样会造成死循环。


### reg.test()

仅返回 `true` or `false`

***

## 实例

### 匹配3个连续数字

**零宽断言**

1. `(?=exp)` 断言 匹配的位置的后面会出现 exp
2. `(?<=exp)` 断言 匹配的位置前面会出现 exp


`/(0(?=1)|1(?=2)| ... ){2}/`


**注意:**
使用零宽断言有一个需要小心的点:即返回的匹配 str 是不包括 exp 的


### 美元书写格式

#### 题目描述
给定字符串 str，检查其是否符合美元书写格式
1. 以 $ 开始


2. 整数部分，从个位起，满 3 个数字用 , 分隔


3. 如果为小数，则小数部分长度为 2


4. 正确的格式如：$1,023,032.03 或者 $2.03，错误的格式如：$3,432,12.12 或者 $34,344.3

##### 解

`$12.02`
`$`

`/^\$(\d{1,3)(\.\d{2)?$`

`/^\$(\d{1,3})(,\d{3})+(\.\d{2})?$`

==> `/^(\d{1,3})(,\d{3})*(\.\d{2})?$`