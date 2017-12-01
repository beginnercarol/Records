# JS 对象


## 字面量

```
function createModule(str1, str2) {
    return {
        greeting : str1,
        name : str2,
        sayIt : function(){
        	return this.greeting+', '+this.name;
    	}
    };
}
```


## 构造函数

```
function createModule(str1,str2){
    function Obj(greeting,name){
        this.name = greeting;
        this.name = name;
        this.sayIt = function(){
            return this.greeting+', '+this.name;
        }
    }
    return new Obj(str1,str2);
}
```

## 