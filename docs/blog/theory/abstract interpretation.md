# Abstract Interpretation @ NYU CSCI-GA.3140-001 Spring 2023

- 教授：Patrick Cousot
- 教材：Cousot, Patrick. _Principles of Abstract Interpretation_, MIT Press, 2021. _ProQuest Ebook Central_, http://ebookcentral.proquest.com/lib/nyulibrary-ebooks/detail.action?docID=6715808.  
- 网页：https://cs.nyu.edu/~pcousot/courses/spring23/CSCI-GA.3140-001/slides/index.shtml
- https://github.com/PrAbsInt


# 读教材笔记
For those interested only in the use of such static analyzers, Introduction to Static Analysis by Xavier Rival and Kwangkeun Yi [837] is a good reference.  

Over time, the fundamental ideas of abstract interpretation have found a wide range of applications, often unexpected, such as, the formalization of Boolean satisfiability (SAT) and satisfiability modulo theories (SMT) solvers [274, 284]; fuzz testing [851]; robustness and fairness of neural networks [893, 941]; biological networks [140]; and so on. This book provides all the foundations to understand these applications in depth.  

duality of logic : Exercise 2.5

Remark 2.7

A set S equipped with a partial order <= is called a poset \<S, <=\>

It may be that the returned value of a function always belong to a set that depends upon one of its parameters (this is called a dependent type in computer science [166]).

before 2.2.5: A pointwise definition of a function?

# 大纲
首先我们定义一个简单的 PL（编程语言）
```
while ()
```



# Notion

| Symbol               | Type                  | Description                                                                             | Example | tex        |     |
| -------------------- | --------------------- |:--------------------------------------------------------------------------------------- | ------- | ---------- | --- |
| $\mathbb{N}$         |                       |                                                                                         |         | \mathbb{N} |     |
| $\mathbb{N}^+$       |                       |                                                                                         |         |            |     |
| $\mathbb{Z}$         |                       |                                                                                         |         |            |     |
| $\mathbb{R}$         |                       |                                                                                         |         |            |     |
| <br>                 |                       |                                                                                         |         |            |     |
| tt                   | Bool                  | True                                                                                    |         |            |     |
| ff                   | Bool                  | False                                                                                   |         |            |     |
| $\mathbb{B}$         |                       | Bool                                                                                    | tt, ff  |            |     |
| $\varnothing$        |                       |                                                                                         |         |            |     |
| ℘, $\wp(S)$          | Set->Set(Set)         | [Weierstrass] powerset, $\wp(S)=\{S'\mid S'\subseteq S\}$                               |         | \wp        |     |
| $\wp_f(S)$           |                       | finite powerset (all finite subsets)                                                    |         |            |     |
| $\neg$               |                       |                                                                                         |         | \neg       |     |
| <br>                 |                       |                                                                                         |         |            |     |
| $\alpha$             | Any->Any              | 抽象化，abstraction                                                                     |         |            |     |
| $\gamma$             | Any->Any              | 具象化，concretization                                                                  |         |            |     |
| $\mathcal{S}$        | Any->Label->Any       | 语义，semantic                                                                          |         |            |     |
| $\triangleq$         | \<meta\>              | 定义为                                                                                  |         | \triangleq |     |
| $\mathbb{R}$         |                       |                                                                                         |         |            |     |
| poset                | \<Set, PartialOrder\> | A set $S$ equipped with a partial order $\leq$ is called a poset $\left<S, \leq\right>$ |         |            |     |
| $\nrightarrow$       | partial function      |                                                                                         |         |            |     |
| $\twoheadrightarrow$ | 满射，surjective      |                                                                                         |         |            |     |
| $\rightarrowtail$    | 单射，injective       |                                                                                         |         |            |     |
| ⤖                    | 双射，bijective       |                                                                                         |         |            |     |
| $\mathbb{R}$         |                       |                                                                                         |         |            |     |

