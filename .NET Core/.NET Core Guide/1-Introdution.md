# .NET Core

@(.NET Core Guide)[.NET Core]

[TOC]

## 概述

.NET Core是由微软和活跃于Github的.NET开源社区的开发者共同维护的一个通用开发平台。具有跨平台的特性, 支持的平台包括Windows, macOS, Linux, 以及移动设备, 云端, 以及一些嵌入式和物联网有关的应用场景.

以下的一些特性是对于.NET Core最好的定义：
* 灵活的部署方式
* 跨平台 --- 可以运行在Windows, macOs, Linux以及移植到其它的操作系统. 支持的操作系统, CPUs, 和构建的应用程序的类型会随着时间不断的完善. [.NET Core Road Map](https://github.com/dotnet/core/blob/master/roadmap.md)
* 命令行工具 --- 所有的应用场景都可以通过命令行来执行.
* 良好的兼容性 --- 通过[.NET标准类库](https://docs.microsoft.com/zh-cn/dotnet/articles/standard/library), .NET Core可以很好的与.NET Framework, Xamarin和Mono兼容.
* 遵守开源项目标准
* 由微软支持维护 --- [.NET Core Support](https://www.microsoft.com/net/core/support/)

## .NET Core SDK的组成部分
.NET Core由以下部分组成：
* **.NET运行时** --- 提供的功能包括通用的类型系统, 加载程序集, 垃圾回收机制, 语言的互操作性和一些基本的服务.
* **基础类库** --- 提供基本的数据类型, 组合类型和基础的工具.
* **SDK Tools** --- [.NET Core command-line (CLI) tools](https://github.com/dotnet/cli)
* **Language Complier** ---[The .NET Compiler Platform ("Roslyn") ](https://github.com/dotnet/roslyn)

### 语言

基于.NET Core之上, 你可以使用C#以及将要更新的F#, VB构建应用程序或者类库. 因为编译器包含在.NET Core中, 通常情况下应优先使用SDK Tools编译应用程序.

Roslyn编译器和.NET Core SDK Tools可以被继承到不同的集成开发环境中(IDEs), 包括Visual Studio, Visual Studio Code, Sublime Text, Vim, Atom, Emacs等. 配置最合适你的代码编写环境

### .NET APIs 和兼容性

.NET Core可以被看成是.NET Framework的跨平台版本. 它重新实现了.NET Framework中的基础类库, 以便支持跨平台的特性. .NET Core目前提供了.NET Framework中的部分API. 一些类型和方法还没有被实现或已经移除. [.NET Core Road Map](https://github.com/dotnet/core/blob/master/roadmap.md)

### 与.NET标准库的关系

.NET标准库是一系列描述一致的API集合, 为了兼容不同的平台, 不同的.NET runtime版本都必须实现特定版本的标准库, 以便于支持开发者使用.NET平台的APIs.

![net_standard](http://v-zhidu.com/wp-content/uploads/2016/07/net_standard.png)

### 相关的框架技术

.NET Core只包含一个应用程序模型---控制台应用程序, 用于开发工具，本地服务等。额外的应用程序模型都基于.NET Core之上搭建以扩展其功能, 比如：
* [ASP.NET Core](http://asp.net/)
* [Windows 10 Universal Windows Platform (UWP)](https://developer.microsoft.com/windows)
* [Xamarin.Forms](https://developer.microsoft.com/windows)

### 开源

.NET Core是一个开源项目(MIT许可证), 从2014由.NET基金会主持开发, 目前为止成为了.NET基金会主持的开源项目中最活跃的一个。它可以被任何个人, 公司自由采纳, 用于个人, 教育以及商业目的. 许多公司用.NET Core创建他们的应用程序, 工具, 新的开发平台以及各种形式的服务. 其中的一些公司在Github上对.NET Core做出了显著的贡献. 并作为.NET基金会技术小组成员对产品开发方向提供指导.

## 产品发布

.NET Core产品有两种发布方式, 作为一系列package发布到NuGet.org以及独立的安装应用程序.

### 发行版

你可以从.NET Core的[官方网站](https://www.microsoft.com/net/core#windows)下载.NET Core

* *Microsoft.NET Core* 发行版包含CoreCLR runtime, 相关的类库, 一个控制台寄宿应用程序和一个*dotnet*启动程序. 关于详细信息描述在[`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) 包中
* *Microsoft.NET Core SDK* 发行版包含.NET Core和一些加载nuget package, 编译, 运行应用程序的工具

一般来说, 你应该先安装.NET Core SDK开始开发基于.NET Core的应用程序. 你也可以选择安装其它预发布的.NET Core生成版本

### 包管理

* **.NET Core Packages** --- .NET Core被拆分为一揽子package, 包含.NET Core运行时和类库(引用的程序集和实现), 提供基础的功能. 例如, [`System.Net.Http`](https://www.nuget.org/packages/System.Net.Http/)

* *.NET Metapackages* --- metaPackages是一些具有特定功能包的集合

> 关于这部分内容会在以后翻译学习 --- [英文源地址]((https://docs.microsoft.com/zh-cn/dotnet/articles/core/packages)
