# 7 采样和重建

&#160;&#160;&#160;&#160;
虽然渲染器(如PBRT)的最终输出是一张二位的像素图，但在投影平面(Film plane)上定义的入射辐射率却是一个连续函数。通过连续函数来计算离散像素值的方法对最终渲染的图像质量有非常大的影响。如果不处理好，渲染将会出现瑕疵。相反，如果处理的好，可以在增加少量计算的情况下显著的提高渲染质量。

&#160;&#160;&#160;&#160;
本章首先介绍采样原理-既从连续域定义的函数提取离散样本，然后重建与原始函数相似的新函数的原理。基于采样原理和低差分点集（低差分点集是一种特殊的分布良好的采样点类型），本章会一各种方法定义采样器来生成 $n$ 维采样数据。本章描述了五个采样器的实现，包含采样的各种方法。

&#160;&#160;&#160;&#160;
本章包含过滤(Filter)类和胶片(Film)类，Filter 用于确定如何混合每个像素附近的多个样本计算出像素值，Film类将图像样本累积到图像的像素中。
