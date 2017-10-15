# VMAttack **IDA** PRO 插件
**IDA Pro 插件用于静态、动态分析基于虚拟化的加壳，以及反混淆**

**VMAttack 被授予第二名在每年的举办的IDA Pro Plug-in比赛 [IDA Pro Plug-in Contest in 2016](https://www.hex-rays.com/contests/2016/index.shtml)!**

## 介绍

VMAttack 是**IDA PRO** 插件能够使逆向工程师去使用额外的分析被用来对抗 _基于虚拟化的混淆_的特性. 目前聚焦于 **基于栈的虚拟机**, 但是未来将会扩展支持更多架构. 插件使用**IDA API** 特性配合插件，使插件支持静态、动态分析能力，并提供自动分析, 半自动分析、手动分析的功能. 
这个插件的主要目的是协助逆向工程师解决 _基于虚拟化的混淆_ 并且自动逆向的过程.

## 快速入门指南

Example目录 包含一个加法函数的被混淆的二进制和原二进制. 被混淆的**addvmp** 包含我们要分析的VM函数.
