---
title: "Conditional Entropy 유도"
date: 2023-09-25 17:58:06 +0900
categories: [Mathematics, etc]
tags: [] # TAG names should always be lowercase

author: rouxist
math: true
---

## 2023.09.24

---

&nbsp;&nbsp;정보이론 기초부분의 Conditional Entropy 부분에 대한 증명을 보던 중 1학기 확통 시간에 배웠던 **Law of total expectation**이 떠올라서 유도를 했다.

$$
\begin{aligned}
H(Y|X) & = E_{X}[H(Y|x)] =E_{X}[E_{Y}(I(y|x))] \\
 & = \sum_{x\in X}^{}[p(x)(E_{Y}[I(y|x)])] \\
 & = \sum_{x\in X}^{}[p(x)\sum_{y\in Y}^{}-p(y|x)log(p(y|x))] \\
 & = \sum_{x\in X}^{}[p(x)\sum_{y\in Y}^{}-p(y|x)(log(p(x,y))-log(p(x)))] \\
 & = \sum_{x\in X}^{}[p(x)\left\{ \sum_{y\in Y}^{}-p(y|x)log(p(x,y))+\sum_{y\in Y}^{}p(y|x)log(p(x)) \right\}] \\
 & =\sum_{x\in X}^{}[p(x)\left\{ \sum_{y\in Y}^{}-\frac{p(x,y)}{p(x)}log(p(x,y))+log(p(x))\sum_{y\in Y}^{}p(y|x) \right\} ] \\
 & = \sum_{x\in X}^{}[-\sum_{y\in Y}^{}p(x,y)log(p(x,y)) ] - \sum_{x\in X}^{}[-p(x)log(p(x)) ] \\
 & = H(X,Y) - H(Y)
\end{aligned}
$$

<br/><br/>
