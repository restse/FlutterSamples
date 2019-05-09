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
#### List、Map 和 Set
```
void fun() {
  ///---------------List---------------
  // 使用构造函数创建对象
  // 跟 var list = new List<int>(); var list = new List();一样
  // 在 Dart 2 里，创建对象时可以省略 new 关键字，也推荐省略 new
  var list = List<int>();
  list.add(1);
  list.add(2);

  var list1  = [1,2,3,"Dart",true];//创建List
  var list2 = [1, 2];
  print(list1);//[1,2,3,Dart,true]
  print(list1[2]);//3
  list1[1] = "hello";//[1,hello,3,Dart,true]
  list1.indexOf(2);//1


  //没有元素，显式指定泛型参数为 int
  var list3 = <int>[];
  list3.add(1);
  list3.add(2);
  // ignore: unnecessary_statements
  list3.clear;//[]

  var list4 = const[1,2,4];//创建不可变list
 //list4指向的是一个常量，我们不能给它添加元素（不能修改它）
  list4.add(3); //error
 //list4 本身不是一个常量，所以它可以指向另一个对象
  list4 = [4,5,6]; //it's fine

  const list5 = [1, 2];
 //相当于 const list5 = const[1, 2];
  list5.add(3); // error

  //Dart 同样提供了 for-in 循环。
  //in 在 Dart 里是一个关键字
  var list6 = [1, 3, 5, 7];
  for (var e in list6) {
    print(e);
  }
  
  
  ///---------------Set---------------
  //只能通过 Set 的构造函数创建实例
  var set = Set<String>();
  set.add('foo');
  set.add('bar');
  assert(set.contains('foo'));
  
   ///---------------Map---------------
  var map = {"first": "Dart", 1: true, true: "2"}; //创建Map
  var language = const {"first": "Dart", "second": "Java"}; //创建不可变Map
  var language2 = new Map(); //构造创建
  print(map); //{first: Dart,1: true,true: 2}
  print(map["first"]); //Dart
  print(map[true]); //2
  map[1] = false; //重新赋值
  print(map); //{first: Dart,1: false,true: 2}
  list1.asMap(); //key 0 1 2 3 ...

  var map2 = Map<String, int>();
  //添加
  map2['foo'] = 1;
  map2['bar'] = 3;
  // 修改
  map2['foo'] = 4;
  //对应的 key 不存在时，返回 null
  if (map2['foobar'] == null) {
    print('map does not contain foobar');
  }
  var map3 = const {
    'foo': 2,
    'bar': 4,
  };
  var map4 = <String, String>{};
  ```
