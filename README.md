倒腾一些奇怪的玩意，以前是某种[在android hook system_server搞权限诈骗/截图隐写水印隐藏](https://github.com/AcdeAsdff/DATServiceReplacement)，

更近一点是Minecraft modding,[thaumcraft4在1.20.1的更高性能和可扩展性的重置(还没写完)](https://github.com/IgnoreLicensesCN/OpenTC4-Architectury)



这一部分和别人的不同之处可能能从

* AspectList，
* WandCastingItem的一堆interface
* AspectResourceLocation及其类似物
* CompoundTagAccessor对NBT读写的封装
* CubeChunkedWeakLookups减少查询量 [1]
* VanillaTypedRecipeResolver及其相关class进行某种Graph要素计算 [2]
* 一堆从原始逻辑抽出来的interface

看出来，也算是*比较有代表性*的两个repo？大规模重构需要一些力气就是了。

//TODO:getting nervous finding jobs

//TODO:finish this .md

[1][2]:或者（如果愿意听高大上的名词，我们有）：*基于 Java 泛型极限与面向契约设计（Interface-driven Architecture），对一款高复杂度、状态繁多的复杂仿真系统进行现代化重构。实现了零内存分配（Zero-Allocation）缓存、3D 空间弱引用分块索引、以及基于图论的解算管道，将高频 Tick 中的 GC 压力压降至极致。*
