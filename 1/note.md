# 1 - 计算模型

> 以及为什么它不重要

**时间可构造函数（Time-constructible functions）**，对于一个函数 $T:\mathbb{N}\rightarrow\mathbb{N}$，如果 $T(n)\ge n$ 并且存在一个图灵机 $M$ 使得对于输入 $x$，能够在时间 $T(n)$ 内计算出 $T(|x|)$ 的二进制表示，则称 $T$ 为时间可构造函数。限制 $T(n)\ge n$ 是为了算法有时间读取输入。*“我认为是为了让图灵机可以在指定的时间内停止，当时间依赖于输入的长度时，若计算时间花费的时间大于指定的时间本身，就会导致无法在预期的时间自动停止”*。

**[Soundness and Completeness](https://math.stackexchange.com/questions/105575/what-is-the-difference-between-completeness-and-soundness-in-first-order-logic)**