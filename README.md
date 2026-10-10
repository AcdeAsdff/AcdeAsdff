倒腾一些奇怪的玩意，以前是某种[在android hook system_server搞权限诈骗/截图隐写水印隐藏](https://github.com/AcdeAsdff/DATServiceReplacement)，

更近一点是Minecraft modding,[thaumcraft4在1.20.1的更高性能和可扩展性的重置(还没写完)](https://github.com/IgnoreLicensesCN/OpenTC4-Architectury)



这一部分和别人的不同之处可能能从

* AspectList，
* WandCastingItem的一堆interface
* AspectResourceLocation及其类似物
* CompoundTagAccessor对NBT读写的封装
* CubeChunkedWeakLookups减少查询量 [1]
* VanillaTypedRecipeResolver及其相关class进行某种Graph要素计算 [2]
* CalculationOperationAdd用于抽象特定场景下包装过的Map之间的运算，对标记好的单例有较好的性能表现 [3]
* 一堆从原始逻辑抽出来的interface

看出来，也算是*比较有代表性*的两个repo？大规模重构需要一些力气就是了。

//TODO:getting nervous finding jobs

//TODO:finish this .md

* [1] [2] :或者（如果愿意听高大上的名词，我们有）：
```
基于 Java 泛型极限与面向契约设计（Interface-driven Architecture），对一款高复杂度、状态繁多的复杂仿真系统进行现代化重构。实现了零内存分配（Zero-Allocation）缓存、3D 空间弱引用分块索引、以及基于图论的解算管道，将高频 Tick 中的 GC 压力压降至极致。
```
* [3] :类似的，我们有：
```
针对高频图论/要素代数运算的单例流式缓存加法器 (CalculationOperationAdd)

交换律拓扑等价缓存 (AllowOrderExchangeCalculationCacheKey)：
利用加法交换律构建对称哈希拓扑，消除同质计算输入的顺序依赖，显著提升高频重复算子的缓存命中率（Cache Hit Rate）。

单例结构自适应拆分与惰性合并机制 (Adaptive Singleton Decomposition)：
针对稀疏集合与单例元数据（Singleton Input），设计了低开销的路径分支策略。通过将复合集合拆解为“原子单例（Singleton Part）”与“多元残差（Not-Singleton Part）”，仅对极小化单元进行缓存寻址与 computeIfAbsent 聚合计算，大幅降低哈希碰撞与对象分配开销。

零开销状态归纳 (Zero-Allocation Identity Bypassing)：
针对空集边界进行 Identity 级别的直接短路（Short-circuit Returns），避免任何无效的线性遍历与新对象创建。 ```
