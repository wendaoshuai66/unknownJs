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











