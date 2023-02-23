### 关键字

#### private关键字





#### this关键字





#### static关键字





### 类方法

#### Scanner获取输入

import java.util.Scanner

```java
Scanner sc = new Scanner(System.in);

int num = sc.nextInt();  //键盘输入用int接收

String str = sc.next();  //键盘输入用string接收
```

#### Random随机数

import java.util.Random

```java
Random r = new Random();

int num = r.nextInt();  //无范围整型，有正负

int num = r.nextInt(10);  //有范围整型，[0，10)
```

### 工具方法

#### 字符串方法

创建方法：

```java
String str = new String();  //空字符串

String str = new String(char[] array);

String str = new String(byte[] array);

//直接创建，存放在常量池中，相同的内容为同一个字符串，不管名字是否相同。
String str = "Hello";
```

比较方法：

```java
String str1 = "Hello";
String str2 = "Hello";

str1.equals(str2);  //true
//常量池中为同一字符串，相等，如果是用别的创建方法，判断为false

str1.equalsIgnoreCase(str2);  //忽略大小写的比较
```

获取方法：

```java
int length = str.length();

//拼接字符串,原字符串不变，产生新的字符串(直接+也可以拼接字符串)
String str3 = str1.concat(str2);

//获取索引位置字符
char ch = str1.charAt(1);

//查找字符串第一次出现的索引，如果没有则返回-1
int index = str.indexOf("llo")；
```

截取方法：

```java
String str1 = "HelloWorld";

//从索引位置到末尾
String str2 = str1.substring(5);

//按索引位置返回,[4,7)
String str2 = str1.substring(4, 7);

```

转换方法：

```java
//将字符串转化为字符数组
char[] chars = "Hello".toCharArray();

//将字符串转化为字节数组
byte[] bytes = "Hello".getBytes();

//替换字符串
String str1 = "How do you do?";
String str2 = str1.replace("o", "*");
```

分割方法:

```java
String str1 = "aaa bbb ccc";
String[] array1 = str1.spilt(",");

String str1 = "XXX.YYY.ZZZ";
String[] array1 = str1.spilt("\\.");  //如果用.来分割，必须加\\
```

#### Arrays方法

import  java.util.Arrays

```java
Arrays.toString(数组);
        
Arrays.sort(数组);	//直接对原数组原地修改（1.数值默认从小到大，2.字符串默认字母升序）
```

#### Math方法

import  java.util.Math

```java
Math.abs();
    
Math.ceil();  //向上取整
    
Math.floor();  //向下取整
    //都不是四舍五入
    
Math.round();  //四舍五入
    
Math.PI;  //圆周率
```



### Collection接口

定义单列集合共性的方法，无索引

```java
Collection<String> coll = new ArrayList<>();

coll.add("hello");

System.out.println(coll);  //按 [   ,   ,   ] 格式打印

coll.remove("hello");  //返回bool值，表示是否删除成功

coll.clear();  //无返回值

boolean result = coll.contains( ); //判断集合中是否有某元素

coll.isEmpty();  //判断集合是否为空

coll.size();  //获取集合长度

Object[] arr = coll.toArray();  // 将集合转成数组，转成数组后可以遍历输出
```

 

#### Collections集合工具类方法

```java
ArrayList<String> list = new ArrayList<>();

Collections.addAll(list, "a","b","c");  //添加所有元素

Collections.shuffle(list);  //打乱顺序

Collections.sort(list);  //默认是升序，排序自定义类的话，需要重写compareTo方法
/*
comparable接口排序规则：
this（自己）- 参数  ：升序
*/

Collections.sort(list, new Comparator<Tnteger>(){
    public int compare(Integer o1,Integer o2){
        return o1-o2;  //升序
    }
});
 
```



#### List接口

特点：

+ 有序（存储和取出元素顺序相同）
+ 允许存储重复的元素
+ 有索引，可以for循环遍历

##### ArrayList集合

import java.util.ArrayList

数组长度不可变，ArrayList长度可变

| 基本类型 |      包装类       |
| :------: | :---------------: |
|   byte   |       byte        |
|  short   |       short       |
|   int    |  ==**Integer**==  |
|   long   |       long        |
|  float   |       float       |
|  double  |      double       |
|   char   | **==character==** |
| boolean  |      boolean      |

```java
//<>内为泛型（引用类型），即上表包装类
ArrayList<String> list = new ArrayList<>();

System.out.println(list);  //打印成[...,...,...]格式

list.add("aaa");  //添加元素，其会返回一个bool值代表是否添加成功

String name = list.get(0);  //根据索引值获取元素

String removed = list.remove(0);  //根据索引删除元素

int size = list.size();  //获取集合的长度
```

##### LinkedList集合

```java

```





##### Vector集合





#### Set接口

特点：

+ 不允许存储重复元素
+ 没有索引（不能使用for循环遍历）

##### HashSet集合





##### LinkedHashSet集合





##### TreeSet集合





### Iterator迭代器

```java
Collection<String> coll = new ArrayList<>();

coll.add("hello");
coll.add("world");
coll.add("java");

Iterator<String> it = coll.iterator();  //实例迭代器后，指针指向-1位置

boolean b = it.hasNext();  //判断下一位有无元素

String s = it.next();  //取出第一个内容，同时指针+1

//遍历输出集合
while(it.hasNext()){
    String s = it.next();
    System.out.println(s);
}

for( Iterator<String> it2 = coll.iterator() ; it2.hasNext() ; ){
    String s = it2.next();
    System.out.println(s);
}
```

#### 增强for循环

单列集合/数组均可使用

```java
int[] arr = {1,2,3,4,5};
 
for(int i :arr){
    System.out.println(i);
}

ArrayList<String> list = new ArrayList<>();

list.add("aaa");
list.add("bbb");
list.add("ccc");

for(String s : list){
    System.out.println(s);
}
```









































