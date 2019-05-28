# 一些JS的问题
## main函数的参数   
main函数中可以直接调用`arguments[]`这个数组中将存储输入main函数的所有参数  
## JS中的bool值  
JS中不区分数据类型，所以在进行if判断时，以下的变量将可用于bool值  
`undifined`    
判断对象时`null`  
判断数字时`0`或`NaN`  
判断字符串时`''`或`""`  注意字符串的'false'和'0'全部按true对待  
另外{}、[],以及无穷也全部按true对待。