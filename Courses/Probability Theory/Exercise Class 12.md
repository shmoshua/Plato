#ProbabilityTheory 

#### 1. Hypothesis

1. Null and Alternative hypotheses. (innocent guilty)
2. Tests and type 1 and 2 error. $$\phi:\Omega\to \{ 0,1 \}$$where $\phi(X)=0$ means $H_{0}$ is rejected. $\phi(X)=1$ not rejected. Level $\alpha$ means: $$\mathbb{P}_{\theta_{0}}(\phi(X)=1)\leq \alpha$$for all $\theta_{0}\in \Theta_{0}$. The power is a function $\beta:\Theta_{A}\to [0,1],\theta_{A}\mapsto \mathbb{P}_{\theta_{A}}(\phi(X)=1)$

	$X_{1},\dots,X_{n}\sim \text{Ber}(\theta)$ with $n=20$. $H_{0}:\theta\leq \frac{1}{2}$ and $H_{A}:\theta> \frac{1}{2}$. Let $\alpha=.05$. Then, $$\phi(X)=\begin{cases}1&S_{n}>c\\0&S_{n}\leq c\end{cases}$$
1. Significance level and power. We want 