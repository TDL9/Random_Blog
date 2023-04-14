# 基础数学概念

## 前言

同样的概念在不同的语境下（例如不同的教材，视频）表达方式不同。

统一的表达有利于思考和阅读。这里定义一些基本的数学概念。

注：本人受到构造主义影响，且讨厌实无穷，使用类型论

## Meta

类型全大写，常量首字母大写

对象：

等于：

自然数被认为是基本的

## 集合论

def ∅ = empty type

def /A -> B/ = function type of A to B

def (range i j) = type of {i, i+1, ... ,j}

def \[i\] = (range 0 /i-1/)


对：A->

列表


## 张量 Tensor

see:[Ricci calculus] [Einstein notation]

def (tensor n1 ...) = 一个多维数组，其每个维度的大小为 n1 ...

def (X (i ...) (j ...) (k ...) f g) = 爱因斯坦求和符号，默认 f 为乘法，g为加法

def 矩阵乘法 = (X (i j) (j k) (i k))

def 矩阵乘向量 = (X (i j) (j) (i)) 

(X ... L ...) ... (f . (pp pi)) ...=(X ... ((pp pi) L) ...) ... f ...

