---
title: "Finite Set, Infinite Set, Countable Set, Uncountable Set"
date: 2024-05-07 17:28:29 +0900
categories: [Mathematics, Set Theory]
tags: [] # TAG names should always be lowercase

author: rouxist
math: true
---

### Finite Set

A finite set is a set that has a finite number of elements. Informally, a finite set is a set which one **could in principle count and finish counting**. [^fn1]

- 원소의 개수를 _세는 것을 멈출 수 있으면_ finite set이다. 아래의 정의를 통해 더 명료히 할 수 있다.

#### Definition

Formally, a set $S$ is called finite if there exists a bijection
$$f:S \rightarrow n$$
for some natural number $n$.

- 의미하는 바는, 원소의 개수를 자연수 $n$으로 나타낼 수 있어야 한다.
  - 이 때 $n$은 cardinality $$\lvert S \rvert$$ 와 같다.
- bijection이란 one-to-one correspondence를 말한다. [^fn2]
- **Finite set은 countable set이다**.

보통 위와 같이 $$\rightarrow$$를 사용한 함수 표현은 화살표 앞뒤로 집합이 오고 [stackexchange에서도 그런 얘기](https://math.stackexchange.com/q/1751187){:target=”\_blank”}가 있는데, 위 정의에서는 갑자기 (집합이 아닌?) 수 $n$이 나와서 혼란이 있었는데... $n$을 1부터 $n$까지의 자연수들이 포함된 ($n$개의 원소가 들어있는) 집합으로 보면 의미상 맞아보인다.

#### Examples

$$\{1,2,3\}$$ 과 같은 집합

### Infinite Set

An infinite set is **a set that is not a finite set**. [^fn3]

- Finite set이 아닌 set은 infinite set이다.
- Infinte set은 countable일 수도 있고, uncountable일 수도 있다.

#### Examples

Countable:

- 자연수 집합 $$\mathbb{N}$$

Incountable:

- 실수 집합 $$\mathbb{R}$$

둘 다 원소의 개수를 셀 수는(=원소의 개수를 자연수로 나타낼 수는) 없다. 하지만 아래의 차이에 의해 가산(countable) 여부는 갈린다.

### Countable Set

A set is countable if either it is finite or it can be made in one to one correspondence with the set of natural numbers. [^fn4]

- 집합의 원소를 자연수 집합에 일대일로 대응시킬 수 있거나, 자연수 집합의 부분집합에 일대일로 대응시킬 수 있으면 countable set이다.
- **<span style="color:#6667ab">원소의 개수를 자연수로 나타낼 수 있다는 것(=finite)</span>** 과 **<span style="color:#6667ab">원소들을 자연수들에 일대일 대응시킬 수 있다는 것(=countable)</span>** 이 다르다. 이게 정말 tricky하다.
- 자연수 집합의 크기를 $$\aleph_0$$ (aleph-zero, aleph-nought, aleph-null) 라고 표현하기도 한다.
- Infinite set 중 countable인 것들은 모두 그 크기가 $$\aleph_0$$이다.

#### Examples

- 자연수 집합 $$\mathbb{N}$$
- 정수 집합 $$\mathbb{Z}$$
- 유리수 집합 $$\mathbb{Q}$$

### Uncountable Set

집합의 Cardinality가 $$\aleph_0$$보다 큰 경우. [^fn5]

#### Examples

- 실수 집합 $$\mathbb{R}$$

<br><br><br>

2024.05.07

## References

---

[https://blog.naver.com/duxogn08/221154831584](https://blog.naver.com/duxogn08/221154831584){:target=”\_blank”}

[^fn1]: [https://en.wikipedia.org/wiki/Finite_set](https://en.wikipedia.org/wiki/Finite_set){:target=”\_blank”}
[^fn2]: [https://en.wikipedia.org/wiki/Bijection](https://en.wikipedia.org/wiki/Bijection){:target=”\_blank”}
[^fn3]: [https://en.wikipedia.org/wiki/Infinite_set](https://en.wikipedia.org/wiki/Infinite_set){:target=”\_blank”}
[^fn4]: [https://en.wikipedia.org/wiki/Countable_set](https://en.wikipedia.org/wiki/Countable_set){:target=”\_blank”}
[^fn5]: [https://en.wikipedia.org/wiki/Uncountable_set](https://en.wikipedia.org/wiki/Uncountable_set){:target=”\_blank”}
