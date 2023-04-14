# Abstract Interpretation @ NYU CSCI-GA.3140-001 Spring 2023

- 教授：Patrick Cousot
- 教材：Cousot, Patrick. _Principles of Abstract Interpretation_, MIT Press, 2021. _ProQuest Ebook Central_, http://ebookcentral.proquest.com/lib/nyulibrary-ebooks/detail.action?docID=6715808.  
- 网页：https://cs.nyu.edu/~pcousot/courses/spring23/CSCI-GA.3140-001/slides/index.shtml
- https://github.com/PrAbsInt


# 读教材笔记

## Chap2
For those interested only in the use of such static analyzers, Introduction to Static Analysis by Xavier Rival and Kwangkeun Yi [837] is a good reference.  

Over time, the fundamental ideas of abstract interpretation have found a wide range of applications, often unexpected, such as, the formalization of Boolean satisfiability (SAT) and satisfiability modulo theories (SMT) solvers [274, 284]; fuzz testing [851]; robustness and fairness of neural networks [893, 941]; biological networks [140]; and so on. This book provides all the foundations to understand these applications in depth.  

duality of logic : Exercise 2.5

Remark 2.7

A set S equipped with a partial order <= is called a poset \<S, <=\>

It may be that the returned value of a function always belong to a set that depends upon one of its parameters (this is called a dependent type in computer science [166]).

before 2.2.5: A pointwise definition of a function?

Readers may enjoy studying more advanced introduction to abstract set theory, such as [706]

## Chap3
Structural definitions are the basis of denotational semantics, introduced by Dana Scott and Christopher Strachey [872] (and called compositional in this context).  

The idea of collecting semantics was introduced in [235] (under the *qualifier static semantics* ) as a basis for proving the soundness of static analyses. The concept of collecting semantics is further developed in chapter 8.  


## Chap15
Slides-10--15--fixpoints-AI.pdf p17 property

Slide 11 p27
Slide 12 10-19
Slide 16 An overview of set-theoretic formal definitions is given in [Aczel, 1977].

Theorem (18.10,

Slide 18 p28-32

Slide 19 p28
Slide 19 p29 Not mechanizable, even if the loop invariant is given (Rice theorem)
Slide 20 Proof
Slide 21 P24

# 勘误
?book pointwise function
slide04-p11 exists -> exit

# 大纲
首先我们定义一个极简的指令式语言（imperative programming language）
```
A ::= 1 | x | y | ... | z | A1 - A2
B ::= A1 < A2 | B1 nand B2
E ::= A | B

S ::= x = E
	| ;
	| if (B) S
	| if (B) S else S
	| while (B) S
	| break ;
	| { Sl }
Sl ::= Sl S | ɛ
```
非严格地，这是 C 语言的一个子集，即语句可以按照 C 来理解。

省略了括号？todo
代码运行的局部性


The description of syntax by grammar dates back to Noam Chomsky [180]. P28

一个性质（Property）用一个集合 $P$ 表示，在集合里的满足性质，蕴含（imply）关系即集合的包含关系 $P \subseteq Q$

# 符号 Notion

## 基础 Basic

$\mathbb{N, N^+, Z, R}$

$\mathbb{B}$ = Bool : tt, ff

“定义为” = "$\triangleq$"

## 集合 Set

| Symbol                | Type                   | Description                                                                             | Example | tex        |     |
| --------------------- | ---------------------- |:--------------------------------------------------------------------------------------- | ------- | ---------- | --- |
| $\varnothing$         |                        |                                                                                         |         |            |     |
| ℘, $\wp(S)$           | Set->Set(Set)          | [Weierstrass] powerset, $\wp(S)=\{S'\mid S'\subseteq S\}$                               |         | \wp        |     |
| $\wp_f(S)$            |                        | finite powerset (all finite subsets)                                                    |         |            |     |
| $\neg$                |                        |                                                                                         |         | \neg       |     |

## 结构与映射 Structures and maps
| Symbol                | Type                   | Description                                                                             | Example | tex        |     |
| --------------------- | ---------------------- |:--------------------------------------------------------------------------------------- | ------- | ---------- | --- |
| $\alpha$              | Any->Any               | 抽象化，abstraction                                                                     |         |            |     |
| $\gamma$              | Any->Any               | 具象化，concretization                                                                  |         |            |     |
| $\mathcal{S}$         | Any->Label->Any        | 语义，semantic                                                                          |         |            |     |
| $\mathbb{R}$          |                        |                                                                                         |         |            |     |
| poset                 | =\<Set, PartialOrder\> | A set $S$ equipped with a partial order $\leq$ is called a poset $\left<S, \leq\right>$ |         |            |     |
| $\nrightarrow$        |                        | partial function                                                                        |         |            |     |
| $\twoheadrightarrow$  |                        | 满射，surjective                                                                        |         |            |     |
| $\rightarrowtail$     |                        | 单射，injective                                                                         |         |            |     |
| ⤖                     |                        | 双射，bijective                                                                         |         |            |     |

## 程序 Program
| Symbol                | Type                   | Description                                                                             | Example | tex        |     |
| --------------------- | ---------------------- |:--------------------------------------------------------------------------------------- | ------- | ---------- | --- |
| italic $\mathbb{V}$   |                        | 变量，variable                                                                          |         |            |     |
| italic $\mathbb{A}$   |                        | 算术表达式，arithmetic exp                                                              |         |            |     |
| italic $\mathbb{B}$   |                        | 布尔表达式，boolean exp                                                                 |         |            |     |
| italic $\mathbb{E}$   |                        | 表达式，expression                                                                      |         |            |     |

| Symbol                | Type                   | Description                                                                             | Example | tex        |     |
| --------------------- | ---------------------- |:--------------------------------------------------------------------------------------- | ------- | ---------- | --- |
| $\rho$                | Var->Int               | 一个环境                                                                                |         |            |     |
| $\mathbb{Ev}$         | Type1                  | =Var->Int                                                                               |         |            |     |
|                       |                        |                                                                                         |         |            |     |
| $\mathscr{A}$         | ArithExp->Ev->Int      |                                                                                         |         |            |     |
| $\mathscr{B}$         | BoolExp->Ev->Bool      |                                                                                         |         |            |     |
| $\mathcal{S}$         | Exp->Ev->(Int\|Bool)   |                                                                                         |         |            |     |
|                       |                        |                                                                                         |         |            |     |
| semantic property $P$ | Set(Ev->(Int\|Bool))   |                                                                                         |         |            |     |
| $\mathcal{S}$         | Exp->Ev->(Int\|Bool)   |                                                                                         |         |            |     |

## Abstraction

| Symbol                   | Type | Description | Example    | tex |     |
| ------------------------ | ---- |:----------- | ---------- | --- | --- |
| the hat of $\widehat{S}$ |      |             | Structural |     |     |