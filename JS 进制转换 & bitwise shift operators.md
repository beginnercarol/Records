# JS 进制转换 & operators


## & | ^ ~

+ 按比特位进行运算
+ 


## Shift operators

### left shift `<<`

+ 左移,右位补零
>Excess bits shifted off to the left are discarded. (?)

### sign-propagating right shift `>>`

+ 带符号
+ 右移


### zero-fill right shift `>>>`

+ 不带符号

## Logical operators

### &&  ||  !

+ 布尔值


## parseInt & parseFloat

**radix 表示的是第一个参数的进制,不是要转换的进制**

>如果 parseInt 遇到了不属于radix参数所指定的基数中的字符那么该字符和其后的字符都将被忽略。接着返回已经解析的整数部分。parseInt 将截取整数部分。开头和结尾的空白符允许存在，会被忽略。
>如果第一个字符不能被转换成数字，parseInt返回NaN。

>parseFloat将它的字符串参数解析成为浮点数并返回.如果在解析过程中遇到了正负号(+或-),数字(0-9),小数点,或者科学记数法中的指数(e或E)以外的字符,则它会忽略该字符以及之后的所有字符,返回当前已经解析到的浮点数.同时参数字符串首位的空白符会被忽略.
`parseFloat(314e-2);//3.14`


## toString()

十进制转其他

`value.toString(radix);`
radix是value希望转换为的进制