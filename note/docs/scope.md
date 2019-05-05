# 作用域是什么

## 编译流程

![https://wendaoshuai66.github.io/unknownJs/note/images/compile.png](https://wendaoshuai66.github.io/unknownJs/note/images/compile.png)

## 引擎 、编译器、作用域

![引擎 、编译器、作用域](https://wendaoshuai66.github.io/unknownJs/note/images/three.png)

```
var a= 2;
```

以上代码，引擎认为这里经历了两个不同的声明：

- 编译器在编译时的处理
- 引擎在运行时的处理

 以 var a = 2; 为例，演示引擎、编译器、作用域三者是如何工作的

![https://wendaoshuai66.github.io/unknownJs/note/images/engine.png](https://wendaoshuai66.github.io/unknownJs/note/images/engine.png)

总结：

变量的赋值操作会执行两个动作：1. 编译器在当前作用域中声明一个变量； 2. 运行时引擎在作用域中查找该变量，找到便赋值，找不到抛出异常。

## LHS RHS

```
var a = 2;
引擎会为变量 a 进行 LHS 查询。另外一个查找的类型叫作 RHS。
```

![https://wendaoshuai66.github.io/unknownJs/note/images/lhs.png](https://wendaoshuai66.github.io/unknownJs/note/images/lhs.png)

看下面代码，加深理解

```
console.log(a); // 对 a 的引用是 RHS 引用。因为没有对 a 赋值，而是查找并取得 a 的值。
a = 2; // 对 a 的引用是 LHS 引用。不用关心 a 的值是什么，只需要为 = 2 这个赋值操作找到一个目标。
```

##异常

    function foo(a) {
     console.log( a + b );
     b = a;
    }
    foo( 2 );

第一次对 b 进行 RHS 查询时是无法找到该变量的。也就是说，这是一个“未声明”的变

量，因为在任何相关的作用域中都无法找到它。

如果 RHS 查询在所有嵌套的作用域中遍寻不到所需的变量，引擎就会抛出 ReferenceError

异常。值得注意的是，ReferenceError 是非常重要的异常类型

##提升
![https://wendaoshuai66.github.io/unknownJs/note/images/tisheng.png](https://wendaoshuai66.github.io/unknownJs/note/images/tisheng.png)












