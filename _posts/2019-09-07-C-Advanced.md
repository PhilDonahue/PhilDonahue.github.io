---
layout:     post
title:      "C Advanced"
subtitle:   "Hello World, Hello Blog"
date:       2019-09-07 00:30:00
author:     "LR"
header-img: "img/C_background.jpg"
tags:
    - C Language
---

#### ~scanf("%d%d",&a,&b)
###### 代码功能：多组输入求两个数的和
```
#include<stdio.h>
int main()
{
	int a,b;
	while(~scanf("%d%d",&a,&b))  
		printf("%d\n",a+b);
	return 0;
}
```
- scanf("%d %d",&a,&b)!=EOF  ==  ~scanf("%d%d",&a,&b)没有区别
- int scanf(char *format[,argument,...]);
- scanf("<格式化字符串>"，<地址表>);返回类型为int， scanf()函数返回成功赋值的数据项数，出错时则返回EOF。
- 例如scanf("%d %d",&a,&b),如果a、b均赋值成功返回值为2，只是a赋值成功返回1，a、b都不成功返回0，出错的时候返回EOF。(EOF不是一个字符，它被定义为是int类型的一个负数-1。)
[摘录自CSDN](https://blog.csdn.net/liluo_2951121599/article/details/78595086)<br>
[C 语言进阶之路](https://www.dotcpp.com/oj/problemset.html)
