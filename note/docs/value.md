# 值

## 数组

数组可以容纳任何类型的值，可以是字符串、数字、对象、甚至是其他数组，对数组声名后即可加入值，不需要预定设定大小，使用delete运算符可以将单元从数组中删除，但是注意，单元删除后，数组的length属性不会发生变化

例子

```
var a = [1,2,3]//
delete a[1]
console.log(a)//[1, empty, 3]
console.log(a.length)//3
```

在‘‘稀疏“创建数组（sparse array，即含有空白或空缺的单元的数组）时特别注意：

```
var a = []
a[0] = 1
a[2]= [3]
console.log(a[1])//undefined
console.log(a.length)//3
console.log(a)//[1, empty, Array(1)]
```

在数组中加入字符串键值/属性并不是一个好主意。建议使用对象来存放键值/属性值，用数组来存放数组索引值：

```
var a = []
a[0] = 1
a['foo'] =2
console.log(a[0])//1
console.log(a['foo'])//2
console.log(a.foo)//2
console.log(a.length)//1



var b = []
b['12'] = 42
b.length //12   字符串u键值能够被强制类型转换为十进制数字的话，它就会被当做数字索引来处理
```

## 类数组

类数组有：一些DOM查询操作 会返回DOM元素列表，通过arguments对象

转换数组方法：

```
function foo(){
//方法一
var arr = Array.prototype.slice.call(arguments)
//方法二
var arr = Array.from(arguments)
arr.push('bar')
console.log(arr)
}

foo('a','b')// ["a", "b", "bar"]
```

## 字符串

字符串不可变是指字符串的成员函数不会改变其原始值，而是创建并返回一个新的字符串。而数组的成员函数都是在其原始值进行操作

## 数字

JavaScript中的“整数”就是没有小数的十进制，所以42.0即等同于“整数”42。与大部分现代编程语言（包括几乎所有的脚本语言）一样，JavaScript中的数字类型是基于IEEE 75标准来实现的，该标准也被称为“浮点数”，JavaScript使用的是“双精度”格式（即64位二进制）。

1、数字的语法

特别大和特别小的数字默认用指数格式显示，与toExponential（）函数的输出结果相同。例如：

```
var a = 5E10
console.log(a)// 50000000000
console.log(a.toExponential())//5e+10
console.log(5e+10)//50000000000
```

tofixed(..)方法可指定小数部分的显示位数

```
var a = 42.59
a.tofixed(0)//43
a.tofixed(1)//42.6
a.tofixed(2)//42.59
a.tofixed(3)//42.590
```

toPrecision(..)方法用来指定有效数位的显示位数

