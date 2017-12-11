# JS 特殊值

## null undefined

`null == null; //true`
`null === null; //true`

`undefined` 同 `null`

`null==undefined;//true`
`null===undefined;//false`


## NaN

**NaN 是个傲娇,无论什么都不会等于 NaN 甚至自己也不等于自己**


***

## JS 中的相等性判断

参考资料:
[JavaScript 中的相等性判断](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Equality_comparisons_and_sameness)

+ `==`将执行类型转换

	+ `null==0;//false` 
	+ `null` 和 `undefined` 是可以互相`==`的
+ `===`不进行类型转换,即当类型不一致时,总是返回 false
+ `Object.is` 与 `===` 类似

	+ 但是会对 `NaN` ,`+0`,`-0` 进行特殊处理
	+ `Object.is(NaN,NaN);//true`
	+ 以及 +0 不等于 -0

	> Determines whether two values are the same value.

***

下面是几个概念的补充:

参考资料:

[JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

[IEEE 754](https://zh.wikipedia.org/wiki/IEEE_754)

[浮点数的二进制表示](http://www.ruanyifeng.com/blog/2010/06/ieee_floating-point_representation.html)

***

## Primitive Data Type

> A primitive (primitive value, primitive data type) is data that is not an object and has no methods. In JavaScript, there are 6 primitive data types: string, number, boolean, null, undefined, symbol (new in ECMAScript 2015).

Primitive data type 是 immutable 的

### 7大类型

+ 6个 primitive data type : 

	+ string
	+ number
	+ boolean
	+ null
	+ undefined
		+ 声明但未被赋值
	+ symbol

+ Object

+ 除 `null` 和 `undefined` 以外,每一个 primitive data 都有 wrapper objects(i.e.对应的构造函数)

### Number

Js 中只有双精度64-bit 符合 IEEE 754 标准的的浮点数
所有的浮点数都可以被表示为:
`(-1)^S * M * 2^E`
+ 其中 S 代表符号 
	+ 1bit 
	
+ M 是小数部分(因为整数部分都是1,省略) 
	+ 52bit
	+ 偏移
	
+ E 是指数部分 
	+ 11bit

> There is no specific type for integers.(没有整型)
> Three symbolic values: +Infinity, -Infinity, and NaN (not-a-number).

#### 检查数据范围

在安全范围之**外**的整数会被表示为 双精度浮点数

+ `Number.MAX_VALUE` & `Number.MIN_VALUE`
+ `Number.isSafeInteger()` 和 `Number.MAX_SAFE_INTEGER` & `Number.MIN_SAFE_INTEGER`

***

`+0 === -0;//true`

```
> 42 / +0
Infinity
> 42 / -0
-Infinity
```


### Symbol

> The data type "symbol" is a primitive data type having the quality that, values of this type can be used to make object properties that are anonymous.

+ 


## 小结

> None of them compares whether the parameters are conceptually similar in structure

他们**都不会**对结构进行比较




















