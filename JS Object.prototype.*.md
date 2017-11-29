# JS 原型链属性 & 自身属性

## 可枚举&不可枚举

1. `Object.getPrototypeOf(obj);`

获取当前 obj 的原型 i.e. [[Prototype]]

`proto.isPrototypeOf(obj);`
proto 是否为 obj 的原型

2. `Object.getOwnPropertyNames(obj);`

获取 obj 的 **自身** 可枚举&不可枚举的属性(即**不包括原型链**上的属性)

>Object.getOwnPropertyNames() 返回一个数组，该数组对元素是 obj自身拥有的枚举或不可枚举属性名称字符串。 数组中枚举属性的顺序与通过 for...in 循环（或 Object.keys）迭代该对象属性时一致。数组中不可枚举属性的顺序未定义。

`obj.hasOwnProperty(prop);`
obj的 **自身** 是否包含`prop`属性

## 可枚举

3. `in`

无论是**原型链**属性还是**自身**属性都可以被访问到
但是必须是**可枚举**

4. `Object.keys(obj)`

返回 obj **自身** 并且 **可枚举** 属性

>Object.keys() 方法会返回一个由一个给定对象的自身可枚举属性组成的数组，数组中属性名的排列顺序和使用 for...in 循环遍历该对象时返回的顺序一致 （两者的主要区别是 一个 for-in 循环还会枚举其原型链上的属性）。



