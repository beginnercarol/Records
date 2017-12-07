# JS Symbol

参考资料:

[ECMAScript 6 入门](http://es6.ruanyifeng.com/#docs/symbol)

***


+ Symbol 是一个新的数据类型,属于 primitive data type
+ 每一个 `Symbol()` 返回的 symbol 值都是 unique 的.
	+ 所谓的 unique 见下面的代码

	```
	var sym1 = Symbol();
	var sym2 = Symbol('foo');
	var sym3 = Symbol('foo');
	``` 
	
	虽然看起来 sym2 和 sym3 是一样的,但是实际上二者用 `===` 进行比较会得到 `false`
	添加参数是为了进行区分,接上面的代码:
	
	```
	 console.log(sym2.toString());//Symbol('foo')
	```
	
	+ 为什么要这么做呢?
		+ 因为当你引用一个现有的对象,又想为其添加新的属性时,可能会与现有的属性重名,使用 symbol 就不会有这个问题了 
	
+ symbol 类型的唯一用途就是作为 object 属性的 identifier
+ 以及 **不可以使用 `new` 创建一个 symbol**  因为symbol 并不是对象


## Symbol 作为属性名

symbol 的 unique 特性 非常适合 作为标识符

```
let mySymbol = Symbol();

// 第一种写法
let a = {};
a[mySymbol] = 'Hello!';

// 第二种写法
let a = {
  [mySymbol]: 'Hello!'
};

// 第三种写法
let a = {};
Object.defineProperty(a, mySymbol, { value: 'Hello!' });

// 以上写法都得到同样结果
a[mySymbol] // "Hello!"
```

+ **不能使用`.`运算符**

```
const mySymbol = Symbol();
const a = {};

a.mySymbol = 'Hello!';
a[mySymbol] // undefined
a['mySymbol'] // "Hello!"
```

使用`.`运算符的时候,实际上使用的不是 symbol , 而是 字符串属性 `"mySymbol"`


+ **在对象内部使用 symbol 定义属性时,也必须加方括号**

## 作为常量

`const COLOR_RED = Symbol();`


## 魔术字符串

> 代码之中多次出现、与代码形成强耦合的某一个具体的字符串或者数值。

消除魔术字符串, 通常是将这个魔术字符串改写成一个变量:

```
const magicType = {
	triangle : 'Triangle',//'Triangle'就是一个魔术字符串
	...
}	
```

使用 symbol 的话只需要:

```
const magicType = {
	triangle : Symbol();
		...
}	
```

这个用法和上面的不一样;
上面都是 Symbol 作为属性名,
此处重要的其实只是这个属性名(魔术字符串).

## 作为属性名时的遍历

+ Symbol 作为属性名时 **不是私有变量**; 但是不会被 `for...in` 或者 `Object.keys(obj)` 或者 `Object.getOwnPropertyNames()` ... 获取到;
+ 有一个专门的函数 `Object.getOwnPropertySymbols()` 可以获取;


