# JS &&  &  比较

资料:

[What's the difference between & and && in JavaScript?](https://stackoverflow.com/questions/7310109/whats-the-difference-between-and-in-javascript)

***

**在 js 中只有 `0`,`null`,`undefined`,`NaN`,`false`,`''`为`false`**
i.e 在作为 `if` 判断条件时 为 `false`.

+ `if(-1){};//true;`

## && 与 & 区别

+ & 按位与 (bitwise AND)
	+ 先将要比较的变量转为Number,再进行 bitwise AND
	+ 不推荐使用

+ && 逻辑与 (logical AND)
	+ 如果首项为 `false` 则返回首项 (不是返回 `false`,而是返回等同于 `false` 的首项)
	+ 如果首项为 `ture` 则返回第二项




