# VMAttack **IDA** PRO 插件
**IDA Pro 插件用于静态、动态分析基于虚拟化的加壳，以及反混淆**

**VMAttack 被授予第二名在每年的举办的IDA Pro Plug-in比赛 [IDA Pro Plug-in Contest in 2016](https://www.hex-rays.com/contests/2016/index.shtml)!**

## 介绍

VMAttack 是**IDA PRO** 插件能够使逆向工程师去使用额外的分析被用来对抗 _基于虚拟化的混淆_的特性. 目前聚焦于 **基于栈的虚拟机**, 但是未来将会扩展支持更多架构. 插件使用**IDA API** 特性配合插件，使插件支持静态、动态分析能力，并提供自动分析, 半自动分析、手动分析的功能. 
这个插件的主要目的是协助逆向工程师解决 _基于虚拟化的混淆_ 并且自动逆向的过程.

## 快速入门指南

Example目录 包含一个加法函数的被混淆的二进制和原二进制. 被混淆的**addvmp** 包含我们要分析的VM函数.

![alt text](screenshots/overview.png "Problem Statement")

快速查看二进制，我们能看到简单的结构：二个参数 `0AFFE1` and `0BABE5`被部署到栈上，然后一个函数(stub)被调用了。

![alt text](screenshots/stub.png "Problem Statement")

函数开始虚拟机函数引用到了push到栈上的VM字节码.

![alt text](screenshots/stub2.png "Problem Statement")

跟进地址，我们看到虚拟机函数是一个典型的接收字节码的解释器。


![alt text](screenshots/switch.png "Interpreter")

这个混淆的一个解决方案是通过逆向工程是逆向解释器并且解释字节码。考虑到这项任务时间消耗的性质，我们将会使用VMAttack plugin逆向这个二进制。
