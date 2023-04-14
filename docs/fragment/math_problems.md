
假设 $a_1,a_2,\dots,a_n \in (-1,1)$，证明
$$\prod_{1\leq i, j \leq n}\frac{1+a_ia_j}{1-a_ia_j}\geq1$$
并求取等条件。

答：取 $\log$ 然后泰勒展开，交换求和符号（什么时候能？）

----

是否存在完全平方数 $a^2, b^2$ ，使得 $a^2-b^2$ 和 $a^2+b^2$ 都是完全平方数？

答：似乎无解，待证明 TODO

分析：去掉任何一个`是完全平方数`的条件都有解：

- 去掉 $a^2-b^2$ 或 $a^2+b^2$：勾股数
- 去掉 $a^2$：$5-4=1, 5+4=9$
- 去掉 $b^2$：$25-24=1, 25+24=49$



----

是否存在一个形如 $144\dots 444$ 的完全平方数？

答：除 $1$ 和 $144$ 外不存在，因为不存在完全平方数 $a^2 \equiv 4444 \pmod{10000}$

分析：逐位考虑，$a^2 \equiv 4 \pmod{10}$ 的解有 $2$ 和 $8$

$a^2 \equiv 44 \pmod{100}$ 的解有 $12,62,88,38$

显然 $x$ 是解则 $-x$ 也是解。如果 $x$ 是 $\bmod 10^k$ 的解，那么对应 $\bmod 10^{k+1}$ 的解为 $c\cdot 10^k+x$，有

$$(c\cdot 10^k+x)^2 \bmod 10^{k+1} = 2\cdot c\cdot10^k(x\bmod 10) + x^2$$

----

图灵机停机问题？（相关：哥德尔不完备性定理，Rice定理，）

答： TODO

----

推广结合律到 n元运算？

分析：在一个数组上的 n 叉树