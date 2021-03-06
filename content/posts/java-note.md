+++
title = "Java Note"
date = "2021-02-18T23:50:52+08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["java", "oop"]
keywords = ["", ""]
description = ""
showFullContent = false
+++

目的：虽然自己做的是前端，平时用不上 Java，但 Java 的面向对象编程却是经典，即使自己用不上，但学习了解下纯正的面向对象思想也是不错的。

既然学习一门后端语言只是为了学习下面向对象编程的思想，那么选择 Java 就行，因为这门语言够久，有足够的资料可以学，出了问题也能很方便地找到答案，相比 rust 之类的新语言学习起来会轻松许多。

面向对象三大特性：封装、继承、多态

设计方法的原则：保持方法的原子性，一个方法只完成一个功能，这样有利于后期扩展

修饰符

值传递和引用传递

重载就是在一个类中有相同的函数名称，但形参不同的函数

递归的边界、前阶段、返回阶段

Java 内存：堆、栈、方法区

+ 堆：专门存放 new 的对象和数组，可以被所有的线程共享，不会存放别的对象引用
+ 栈：存放基本变量类型（会包含这个基本类型的具体数值），引用对象的变量（会存放这个引用在堆里面的具体地址）
+ 方法区：可以被所有线程共享，包含了所有的 class 和 static 变量

数组的三种初始化：
+ 静态初始化：创建+赋值
```
   int[] a = {1,2,3};
```
+ 动态初始化：先分配空间，再赋值
```
    int[] a = new int[2];
    a[0] = 1;
    a[1] = 2;
```
+ 默认初始化：数组是引用类型，它的元素相当于类的实例变量，因此数组一经分配空间，其中的每个元素也被按照实例变量同样的方式被隐式初始化

稀疏数组：当一个数组中大部分元素为0，或者为同一值时，可以使用稀疏数组来保存

稀疏数组的处理方式：
+ 记录数组共有几行几列，有多少个不同值
+ 把具有不同值的元素和行列及值记录在一个小规模的数组中，从而缩小程序的规模

面向过程与面向对象

面向过程：步骤清晰简单，一步两步线性操作，适合一些简单的问题

面向对象：通过封装继承多态来将一个大型问题分解为一个个小问题，然后再逐个解决这些问题，适合处理大型项目

对于复杂的项目，我们需要使用面向对象去进行拆分把握，但在拆分后的具体问题中，我们仍然使用面向过程的思想去处理，两者相辅相成

面向对象本质上是以类的方式组织代码，以对象的组织封装数据

类与对象的关系：

类是一种抽象的数据类型，它是对某一类事物的整体描述和定义，但是并不能代表某一个具体的事物

对象是抽象概念的具体实例

构造器的作用：使用 new 关键字构建对象必须有构造器，包括无参构造和有参构造，一旦定义了有参构造，无参就必须显示定义，new 的本质是在调用构造方法，初始化对象的值

构造器和类名相同，没有返回值

引用类型：除了八大基本类型都是引用类型，引用类型意味着对象是通过引用来操作的，即在栈中指向堆

封装，通常指禁止直接访问一个对象中的数据，对数据的操作应该通过接口来访问，常规操作就是将属性设为私有，想要操作属性时使用 get/set 来操作

高内聚就是类的内部数据操作细节自己完成，不允许外部干涉

低耦合就是仅仅暴露必要的方法给外部使用

继承的本质是对某一批类的抽象，从而实现对现实世界的建模

Java 只有单继承，没有多继承

super()：调用父类的构造方法，必须在构造方法的第一个，super 只能在子类的方法或者构造方法中，super 和 this 不能同时调用

重写：需要有继承关系，子类重写父类的方法

+ 方法名必须相同
+ 参数列表必须相同
+ 修饰符的范围可以扩大但不能缩小
+ 抛出的异常的范围可以缩小但不能扩大

为什么需要重写？

+ 子类的需要父类不一定满足

静态方法和非静态方法：静态方法的调用只和左边的类型有关，非静态的方法就会调用子类重写的方法

注解：有功能的注释

多态

+ 可以实现动态编译
+ 增强可扩展性

