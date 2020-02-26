---
layout: post
title: java-gui-first-step
postTitle: Java开发桌面GUI应用初探
categories: [Java, Swing, GUI, Software Construction]
description: 软件构造第2周博客
keywords: Java, GUI, Software Construction, Desktop Applications, Swing
mathjax: false
typora-root-url: ..
---

## 用Swing开发桌面应用

在软件构造Lab1 Problem3（朋友关系图）中，我尝试用Java实现一个有简单GUI（图形界面）的桌面应用程序。与Java Web应用不同，Java为我们提供了桌面GUI应用的开发工具包swing。它是Java基础类的一部分，使用纯Java实现，且无需依赖外部框架，可以说相当地「原生」了。

国内有高人写了一份详细的[Java Swing开发教程](https://blog.csdn.net/xietansheng/article/details/72814492)，供参考。

swing包含了构建GUI的各种组件`Components`，如窗口（`JFrame`和`JDialog`）、标签
`JLabel`、按钮`JButton`、文本框`JText`等。本文中，我们还将用到表格`JTable`这一较为复杂的组件。

此外，swing还支持各种布局`Layout`以及各种其他特性，如与绘图工具包Graphics的互动。Lab1的小乌龟画图任务中，MIT的绘图动画就是用Graphics实现的。

## 构思功能和GUI布局

写前端代码之前，必须先要熟悉应用的功能和对应的API，并对GUI布局有初步的构思。

本应用要做的是，实现一个简单的图模型（朋友关系网络），要求支持三个主要功能：

- 新建结点
- 新建有向边
- 求解任意两节点间最短距离

这里，我们的后端API已经写好，即`Person`和`FriendshipGraph`两个类。

接下来，对GUI整体布局做个构思，如下图所示：

![image-20200226155421564](/images/asserts/image-20200226155421564.png)

界面左侧为功能区，从上至下分别放置三个主要功能；界面右侧为信息区，包含两个表，用于展示目前图中的节点信息和边信息。

## GUI初步建立

