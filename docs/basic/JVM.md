### JVM内存模型

![](/images/JVM内存区域.png)

### JVM垃圾回收

堆是垃圾收集器管理的主要区域，因此也被称作GC 堆（Garbage Collected Heap）.从垃圾回收的角度，由于现在收集器基本都采用分代垃圾收集算法，所以 Java 堆还可以细分为：新生代和老年代：再细致一点有：Eden 空间、From Survivor、To Survivor 空间等。进一步划分的目的是更好地回收内存，或者更快地分配内存。

#### 堆内存空间结构

#### 堆内存分配策略

目前主流的垃圾收集器都会采用**分代回收算法**，因此需要将堆内存分为新生代和老年代，这样我们就可以根据各个年代的特点选择合适的垃圾收集算法。

分代收集算法

#### 垃圾回收器有哪些算法？

- 标记-清除算法
- 标记-整理算法
- 分代收集算法

#### 垃圾收集器

如果说收集算法是内存回收的方法论，那么垃圾收集器就是内存回收的具体实现。

- CMS收集器
- G1收集器

### GC参数调优

为什么要参数调优？
并发量增多，虚拟机层面用较小内存获得高吞吐量和低延迟。
Java对象的GC过程会中断Java程序运行，可通过设置JVM参数、GC参数提高系统性能。

### 内存溢出的原因？

1.JVM堆内存不够导致。
2.代码创建大量对象，存在相互引用，对象长时间不能被回收。
3.无限递归调用导致。
JDK1.7中堆内存的永久区在1.8中替换为元空间。
