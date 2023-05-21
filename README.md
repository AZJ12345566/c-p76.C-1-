# c-p76.C-1-
C语言学习笔记 p76.C语言预处理（1）
重点：
      程序的翻译环境
      程序的执行环境
      详解：C语言程序的编译+链接
      预定义符号介绍
      预处理指令#define
      宏和函数的对比
      预处理操作符#和##的介绍
      命令定义
      预处理指令#include
      预处理指令#undef
      条件编译
      test.c到test.exe中间有编译和链接两个阶段（今天重点掌握）
      
      
      
      
      test.c到test.exe所依赖的环境为翻译环境，test.exe执行依赖运行环境
#include<stdio.h>
int main()
{
      int arr[10]={0};
      int i=0;
      for(i=0;i<10,i++)
      {
            arr[i]=0;
      }
      for(i=0;i<10;i++)
      {
            printf("%d\n",arr[i]);
      
      return 0;
}

翻译环境中的源代码被转换为可执行的机器指令，执行环境用于执行代码
test.exe放的是二进制信息（二进制文件），机器只能读懂二进制信息
每一个原文件都会经过编译器生成一个目标文件（test.obj），所有目标文件合在一起能和链接库经过连接器产生可执行程序
编译文件依赖编译器，链接依赖链接器（这两个都属于翻译阶段）
编译又分为3个阶段：预编译；编译；汇编->目标文件->链接


include<stdio.h>
int g_val=1000;
int main()
{
      int i=0;
      int arr[10]={0};
      for(i=0;i<10;i++)
      {
            arr[1]=i;
      }
      for(i=0;i<10;i++)
      {
            printf("%d",arr[i]);
      }
      return 0;
}

gcc-E test.c  预编译/预处理
1.头文件的包含在预处理阶段就已经完成了
2.注释删除
使用空格来替换注释
3.#define
直接代值进去
以上三点总的来说就是文本操作



gcc-S test.i ->test.s    编译
把c语言代码翻译成汇编代码
汇编过程所做的事情：
1.语法分析； 2.词法分析； 3.语义分析； 4.符号汇总（在汇编阶段和链接阶段应用）
词法分析较为复杂，包括编译原理，像一棵语法树
符号汇总包括函数名，全局变量等符号
