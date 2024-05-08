---
title: "E[X^4] = 3σ^4"
date: 2024-05-08 16:27:52 +0900
categories: [Mathematics, etc]
tags: [Statistics] # TAG names should always be lowercase

author: rouxist
math: true
---

## 2024.05.08

---

[$$(dW_t)^2=dt$$ 인 이유](https://sine-qua-none.tistory.com/33){:target=”\_blank”}에 대해 보던 중, 확률변수 $$X \sim \mathcal{N}(0,\sigma^2)$$에 대해 $$\mathbb{E}[X^4]=3\sigma^4$$ 인 이유를 [stackexchange](https://math.stackexchange.com/questions/1917647/proving-ex4-3σ4){:target=”\_blank”}까지 찾아봐도 상세한 계산까지 설명된 건 없어서 직접 계산을 해봐야 했다.

$$
\begin{aligned}
\mathbb{E}[X^4] & := \int_{-\infty}^{\infty}{x^4\varphi(x)}dx \\
 & = \int_{-\infty}^{\infty}{x^4 \textstyle \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}}dx  && \text{(pdf of normal distribution)}\\
 & = \int_{-\infty}^{\infty}{x^3 (\textstyle \frac{\sigma \cdot x}{\sqrt{2\pi}\sigma^2}e^{-\frac{x^2}{2\sigma^2}})}dx \\
 & = \left[ x^3 \cdot (\textstyle -\frac{\sigma}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}) \right] _{-\infty} ^{\infty} - \int_{-\infty}^{\infty}{3x^2 (\textstyle -\frac{\sigma}{\sqrt{2\pi}}e^{-\frac{x^2}{2\sigma^2}})}dx && \text{(integration by parts)}\\
 & = 0 - \int_{-\infty}^{\infty}{3x^2 (\textstyle -\frac{\sigma^2}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}})}dx \\
 & = 3\sigma^2 \int_{-\infty}^{\infty}{x^2 (\textstyle \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}})}dx \\
 & = 3\sigma^2 \cdot \sigma^2 && \text{(definition of variance)} \\
 & = 3\sigma^4
\end{aligned}
$$

<br/><br/>
