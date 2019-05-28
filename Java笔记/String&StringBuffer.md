# Java中的String和StringBuffer

首先第一点，无论如何String不能被修改，而StringBuffer可以修改。由字面值创建的String对象会被存储在常量区和堆中，这是因为，Java 为了节省资源，对于通过字面值创建的String都会保存在常量区中，当发现新的  
String的字面值与原有的字面值相同时，则不在创建，而是返回原来已经创建好的地址，这个地址将被作为对象存放在堆内存中。

## equals方法
判断两个String的内容是否相同时，尽量使用equals方法。 但注意String类实现了equals方法，但StringBuffer并没有，所以在比较两个SB是否equals时，需要将SB转换为String。

## 构造器
除了String的字面值构造器以外，将int类转换为String可使用，`String.Valueof(int)`或`Integer.toString`.  
字符数组转字符串可以直接调用以字符数组为参数的String构造器，字符串转字符数组时应调用`.toCharArray`.  
针对于上一段提出的String和SB互转的问题，将String转为SB时，直接调用以String为参数的SB构造器，将SB转为String时，调用`.toString()`  
SB还拥有指定字符缓冲区大小作为参数的构造器。

## 一些函数
`subString()`拥有两种参数列表，当只给定一个参数时，将返回从该参数（包括）至结尾的子串，当给定2个参数时，将返回从第一个参数处（包括）到第二个参数处（不包括）的子串。