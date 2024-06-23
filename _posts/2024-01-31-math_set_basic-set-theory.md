---
title: "기초 집합론 내용 정리"
date: 2024-01-31 12:08:29 +0900
categories: [Mathematics, Set Theory]
tags: [] # TAG names should always be lowercase

author: rouxist
math: true
---

측도론과 해석학의 내용을 공부하기 전에 기본적으로 알아야 했던 집합론에 대한 기본적인 내용들을 정리했다.  
고등학교 1학년일 때 집합에 대해 배우면서는 이런 개념을 어디에 활용하는지에 대해 전혀 이해하지 못했는데, '자연수 집합도 집합이다' 라는 사실만이라도 알았다면 훨씬 나았을 듯 하다. 고등학교에서 이런 것도 좀 가르쳐줬으면 좋겠다.

## Set Theory

---

### Set (집합)

명확하게 정의될 수 있는 대상들의 모임

### Family of set / Collection of set

집합을 원소(element)로 가지는 집합. $X$에 대해

### Power Set (멱집합)

집합 $X$의 부분집합(subset)들의 집합, 즉 Family of set의 일종.  
$$2^X, \mathcal{P}(X), \displaystyle \wp(X),  \mathscr{P}(X)$$ 등 노테이션이 너무 다양하다.

### Algebra of set

집합 $X$에 대해 collection of set $$\mathcal{F}\subseteq 2^X$$가 다음 조건들을 만족할 때 $$\mathcal{F}$$를 **algebra over X** 라 한다.

$$
\begin{gather}
1. \emptyset \in \mathcal{F} \\
2. A \in \mathcal{F} \Longrightarrow A^C \in \mathcal{F} \quad \forall A \in \mathcal{F} \\
3. A_1,...,A_n \in \mathcal{F} \Longrightarrow \bigcup_{i=1}^{n} A_i \in \mathcal{F} \quad \forall i \in \mathbb{N} \\
\end{gather}
$$

이를 **sigma of set**이라는 표현과 혼용하여 쓰기도 하는 것 같다. (다만 [위키피디아](https://en.wikipedia.org/wiki/Field_of_sets){:target=”\_blank”}에서는 구분되어있다.)

### $$\sigma$$-algebra (of set)

$$\sigma$$는 countable unions에 대해 닫혀있다는 것을 의미하며, 위 세 가지 조건 중 3번이 가산개에 대하여 성립할 경우 **sigma algebra**라 한다.

$$\bigcup_{i=1}^{\infty} A_i := A_1 \cup A_2 \cup ... \in \mathcal{F} \quad \forall i \in \mathbb{N} $$

ex) $$X=\{1,2,3,4\}, B=\{\{1\},\{2\}\}\subseteq 2^X $$일 때 $$ \mathcal{F} = \{\emptyset, X, \{1\}, \{2\}, \{2,3,4\}, \{1,3,4\}\}$$ 는 **sigma algebra generated by** $B$ 이다.

<br><br><br>

2024.01.31

## References

---

[https://blog.naver.com/mykepzzang/222197904497](https://blog.naver.com/mykepzzang/222197904497){:target=”\_blank”}