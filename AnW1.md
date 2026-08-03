

$X$ is a random variable.

$\mathbb{E}[X]$ measures the expected value.

we want to know how would $X-\mathbb{E}[X]$ behaves. We only care about the squared distance, i.e. $(X-\mathbb{E}[X])^{2}$.
$$\begin{aligned}
Var(X)&:=\mathbb{E}[(X-\mathbb{E}[X])^{2}]
\\&=\mathbb{E}[X^2 - 2\mathbb{E}[X]X + (\mathbb{E}[X])^2]
\\&=\mathbb{E}[X^2]-2\mathbb{E}[X]^2+\mathbb{E}[X]^2
\\&=\mathbb{E}[X^2]-\mathbb{E}[X]^2
\end{aligned}$$

For every random variable $X$, $\mathbb{E}[X^2] = \mathbb{E}[X]^{2}$. In other words, 
$$
Var(X)=\mathbb{E}[X^2]-\mathbb{E}[X]^2 = 0
$$


---
#### Coupon Collector

$X_{i}:=$ the number of draws until after we pick the $i-1$th new card, to pick the $i$-th new card.

$X:=\sum_{i=1}^{n}X_{i}$.

$$\mathbb{E}[X]=\mathbb{E}\left[ \sum_{i=1}^{n}X_{i} \right]=\sum_{i=1}^{n}\mathbb{E}[X_{i}]=\sum_{i=1}^{n} \frac{n}{n-i+1}=n\sum_{i=1}^{n} \frac{1}{n-i+1}=n \sum_{i=1}^{n} \frac{1}{i}=nH_{n}$$

$$X_{i}\sim \text{Geo}\left( \frac{n-(i-1)}{n} \right),\quad \mathbb{E}[X_{i}]=\frac{n}{n-i+1}$$

$Y:=\sum_{i= n / 2 + 1}^{n}X_{i}$
$$\mathbb{E}[Y]=n\sum_{i= \frac{n}{2}+1}^{n} \frac{1}{n-i+1}=n\sum_{i=1}^{n/2} \frac{1}{i}=n H_{\frac{n}{2}}$$