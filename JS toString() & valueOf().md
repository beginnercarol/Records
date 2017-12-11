# JS toString() & valueOf()

## toString() & valueOf()

### toString()

`obj.toString()`

+ 每一个 object 都有`toString()`方法,继承自`Object`
+ 可以重写
+ 不重写的话返回 `[Object type]`
+ String 返回的是字符串内容
+ Number 返回 number 值

+ 返回:

> A string representing the object.
> If this method is not overridden in a custom object, toString() returns "[object type]", where type is the object type.(如果这个方法没有被重写,返回的是`[Object type]`)


> Objects in string contexts convert via the toString() method, which is different from String objects converting to string primitives using valueOf. All objects have a string conversion, if only "[object type]". But many objects do not convert to number, boolean, or function.(字符串上下文中的对象通过 toString()方法转换，这与使用valueOf转换为原始字符串的String对象不同。**所有对象都能转换成一个“[object 类型]”这种格式的字符串**。但是很多对象不能转换为数字，布尔或函数。)


### valueOf()

`obj.valueOf()`

+ 返回:

> The primitive value of the specified object.






## toPrimitive()

`toPrimitive(input[,preferredType])`

> **在没有改写或自定义@@toPrimitive方法的条件下，如果是Date求原值，则PreferredType是String，其他均为Number**


+ 作用于 object , 对于其他类型,传入是什么返回就是什么;
+ preferredType 只接受 Number or String
    + number : 先调用 valueOf() ,若不是**原始值**,再调用 toString()
    + string : 与上面顺序相反 

### 小结

toString() 和 valueOf() 都是为了获取 object 的 primitive value;

在 `toPrimitive()` 的过程中,只要不是 `Date()` 类型,都会默认 `preferredType` 为 `Number` 类型,因此先调用 `valueOf()`,如果不是原始值,再调用 `toString()` .

`[].valueOf();//[]`
`[].toString();//空字符串`
`["hello","world"];//"hello,world`



