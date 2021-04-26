**疑问**

1. P100, Claim 5.9, $\Sigma^p_i$ 中的 $u\in\{0,1\}^{q(|x|)}$，因此它中出现的 $\forall$ 可以一次遍历 $2^{q(|x|)}$，而 $\Sigma_i{\bf TIME}(n^c)$ 中 $i/2$ 次的 $\forall$ 只有两种选择，可以直接相等吗？
2. P108, 第一段中第二句，"Note also that the Boolean formulas studied in earlier chapters are circuits where the fan-out (i.e., number of outgoing ed ges) of each vertex is 1"，我理解出度为 1 的话，说明每个变量只使用一次，回顾应该是没有这个限制的？
3. P119, Definition 6.28, 为什么是对数空间规约而非多项式时间规约？我理解多项式时间即可。

# 5 - 多项式层级和交替图灵机

> Polynomial Hierarchy and Alternating TM

捕获了无法只用非确定性捕获的问题的复杂类是多项式层级，记为 $\bf PH$，是 $\bf P$，$\bf NP$ 以及 $\bf coNP$ 的一般化（generalization）。包括无限数量的子类（称为层级）。这些子类被猜想是不同的，并且这个猜想是 $\bf P\neq NP$ 的更强形式。

## 5.1 类 ${\bf\Sigma}_2^p$

存在似乎不能被 $\bf NP$-完全捕获的计算问题。

对于 $\bf NP$ 问题 INDSET，每个成员都有一个简短的证明（独立集需要枚举，但有一个存在即可，即短证明）：

<img src="note.assets/image-20210426152232421.png" alt="image-20210426152232421" style="zoom: 33%;" />

修改这个问题成确定一个图中的最大独立集：

<img src="note.assets/image-20210426152349887.png" alt="image-20210426152349887" style="zoom: 33%;" />

问题 EXACT INDSET 似乎不存在短证明，因为需要所有的独立集都求出来才可以。

问题 MIN-EQ-DNF，确定等价于给定公式的最小布尔公式：

<img src="note.assets/image-20210426152757453.png" alt="image-20210426152757453" style="zoom: 33%;" />

问题 MIN-EQ-DNF 也没有明显的短证明，因为等价性需要枚举所有的赋值，后边的 equivalent 隐含着 $\forall$。

对于 EXACT INDSET 和 MIN-EQ-DNF 这样的问题，需要存在量词（$\bf NP$）和全称量词（$\bf coNP$）的组合，定义为类 ${\bf\Sigma}_2^p$：

<img src="note.assets/image-20210426154842170.png" alt="image-20210426154842170" style="zoom: 33%;" />

> ${\bf\Sigma}_2^p$ 包含（但不限于）类 $\bf NP$ 和 $\bf coNP$；
>
> MIN-EQ-DNF 是 ${\bf\Sigma}_2^p$-完全问题。

## 5.2 多项式层级

$\bf PH$ 一般化 $\bf NP$，$\bf coNP$ 以及 ${\bf\Sigma}_2^p$。这个类包含每个可以由一个多项式时间计算的谓词和常数多个 $\forall/\exist$ 量词组合定义的语言：

<img src="note.assets/image-20210426160324184.png" alt="image-20210426160324184" style="zoom: 33%;" />

有 ${\bf\Sigma}_1^p={\bf NP}$。定义 ${\bf\Pi}_i^p={\bf co\Sigma}_i^p=\{\overline{L}:L\in{\bf\Sigma}_i^p\}$。因此 ${\bf\Pi_i^p=coNP}$。并且有 ${\bf\Sigma}_2^p\sube{\bf\Pi}_{i+1}^p\sube{\bf\Sigma}_{i+2}^p$，因此${\bf PH}=\cup_{i>0}{\bf\Pi}_i^p$。

### 5.2.1 PH 的性质

