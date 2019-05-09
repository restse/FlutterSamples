#### 变量
##### 基本类型
- ##### int double
- Dart 没有char、byte 、float 
- int double都是64位
- final 运行时常量 运行时赋值 赋值后不可改变
- const 编译期常量 编译期间赋值
```
bool done = true;
int i = 1;
double d = 3.13;
final bool done2 = false;
final int i2 = 1;
final double d2 = 3.14;
const bool done3 = true;
const int i3 = 1;
const double d3 = 3.15;
///类型推断
var done4 = true;
var i4 = 4;
var d4 = 3.14;
final done5 = false;
final i5 = 5;
final d5 = 11.11;
const done6 = true;
const i6 = 6;
const d7 = 99.99;

//var 声明变量 可赋予不同类型的值 未初始化时为null
var a; //null
//数值型 num 包含int double
num x = 10;
```
- ##### String
- Dart 里的 String 跟 Java 中的一样，是不可变对象
- == 比较内容是否一样
- 测试两个对象是否是同一个对象 使用 identical 函数
``` 
var str = " dart";
var str2 = str.toUpperCase();
var str3 = str.trim();
//assert(str == str2); 断言
var bo1 = (str == str2);
var bo2 = (!identical(str, str2));

//字符串 单引号双引号, 三个引号或双引号创建多行字符串,r创建原始raw字符串
String str = 'hello';
String str = r'hello \n Dart' //hello \n Dart 换行无效 原始字符
```
