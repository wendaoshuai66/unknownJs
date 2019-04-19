# 类型

## 定义

对语言引擎会让开发人员来说，类型是值的内部特征，它定义了了值的行为，以使其区别于其他值。例如：42 (数字)与'42'(字符串)采取 不同的处理方式--------》说明是不同的类型

## 详情

Javascript有七种内置类型：

1、空值（null）2、未定义（undefined）3、布尔值（boolean）4、数字（number）5、字符串（string）6、对象（object）7、符号（symbol，ES6中新增），除对象外，其他统称为‘基本类型’

```
typeof null = 'object'//true
正确返回null,这个bug由来已久
var a =null
(!a && typeof a === 'object')//true
```

function（函数）也是JavaScript的一个内置类型，然而查阅规范就会知道，它其实是object的一个‘子类型’。具体来说，函数是‘可调用对象’，它有一个内部属性[call]，改属性使其可以被调用，函数对象的length属性是其声名参数个数。例如：

```
function a(a,b){} a.length = 2
```

## undefined和undeclared

列子

```
var a 
typeof a //undefined
typeof b //undefined  没有报错，这是因为typeof 有一个特殊的安全防范机制
```

