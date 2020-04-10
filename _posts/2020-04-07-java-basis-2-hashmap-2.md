---
layout: post
title: java-basis-2-hashmap-2
postTitle: Java基础（二）——HashMap剖析（下）
categories: [Java, Software Construction]
description: 软件构造第7周博客
keywords: Java, Software Construction, HashMap, Data Structure
published: true
mathjax: true
typora-root-url: ..
---



## 两个因子一棵树

有两个因子直接影响`HashMap`的效率，

- 初始容量（initial capacity）。容量是指哈希表中桶的数量，而初始容量顾名思义就是`HashMap`实例创建时的最初容量。
- 载入因子（Load factor）。含义在前面已经阐述。

此外，同一桶内挤进去很多元素的时候，如果仍用链表存储，效率就会非常低下。因此，在桶内元素过多时，`HashMap`会用红黑树替换链表。

这些内容，且听下回细细分解。

## 参考资料

- [JavaDocs - HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)

- [掘金 - HashMap](https://juejin.im/post/5dee6f54f265da33ba5a79c8)

- [WikiPedia - Hash table](https://en.wikipedia.org/wiki/Hash_table)

- [YiKun - HashMap工作原理及实现](https://yikun.github.io/2015/04/01/Java-HashMap%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%8F%8A%E5%AE%9E%E7%8E%B0/)

- [CSDN - HashMap线程不安全的体现](https://www.cnblogs.com/developer_chan/p/10450908.html)

- [CNblogs - HashMap多线程并发问题](https://www.cnblogs.com/wyq178/p/8676655.html)

- [ConcurrentHashMap & Hashtable](https://mp.weixin.qq.com/s/AixdbEiXf3KfE724kg2YIw)