#ProbabilityTheory 

#### 1. Hypothesis

1. Null and Alternative hypotheses. (innocent guilty)
2. Tests and type 1 and 2 error. $$\phi:\Omega\to \{ 0,1 \}$$where $\phi(X)=0$ means $H_{0}$ is rejected. $\phi(X)=1$ not rejected. Level $\alpha$ means: $$\mathbb{P}_{\theta_{0}}(\phi(X)=1)\leq \alpha$$for all $\theta_{0}\in \Theta_{0}$. The power is a function $\beta:\Theta_{A}\to [0,1],\theta_{A}\mapsto \mathbb{P}_{\theta_{A}}(\phi(X)=1)$

	$X_{1},\dots,X_{n}\sim \text{Ber}(\theta)$ with $n=20$. $H_{0}:\theta\leq \frac{1}{2}$ and $H_{A}:\theta> \frac{1}{2}$. Let $\alpha=.05$. Then, $$\phi(X)=\begin{cases}1&S_{n}>c\\0&S_{n}\leq c\end{cases}$$
1. Significance level and power. We want 
2. Likelihood Ratio Test: $$T=\frac{L(X_{1},\dots,X_{n};\theta_{A})}{L(X_{1},\dots,X_{n};\theta_{0})},K=(c,\infty)$$

---
#### 2. Examples
1. $\theta_{0},\theta_{1}$ where $\theta_{1}>\theta_{0}$. Then, $$T=\left( \frac{\theta_{1}}{\theta_{0}} \right)^{\sum_{}^{}x_{i}}\left( \frac{1-\theta_{A}}{1-\theta_{0}} \right)^{n-\sum_{}^{}x_{i}} >c $$ Hence, $$\sum_{}^{}x_{i} (\log \theta_{1}-\log \theta_{0})+\left( n-\sum_{}^{}x_{i} \right)(\log (1-\theta_{A})-\log(1-\theta_{0}))> \log c$$$$\sum_{}^{}x_{i}>\frac{\log c_{0}-n\log\left( \frac{1-\theta_{1}}{1-\theta_{0}} \right)}{\log\left( \frac{\theta_{1} / (1-\theta_{1})}{\theta_{0} / (1-\theta_{0})}  \right)}=: c_{0}$$
2. Let $X_{1},\dots,X_{n}\sim \text{Poi}(\theta)$. with $H_{0}:\theta_{0}=1$ and $H_{1}:\theta=4$. 
3. Let $\mathcal{N}(\theta, 1/2)$ with $\theta_{0}=0$ and $\theta_{1}=1$. Show that $R(x_{1},\dots,x_{8})=\exp \left( 2\sum_{i=1}^{8}x_{i} \right)\exp(-8)$. , 
4. Let $T=\sum_{n=1}^{}X_{i}$ and we have 1.2, -0.7, 0.3, 2.5, -0.1, 1.7, 1.3, -0.2 with critical region $(3.3, \infty)$. Is the null hypothesis rejected or accepted?
5. Show that $(T,K)$ has significance level $.05$. $$\mathbb{P}(T> 3.3)=\mathbb{P}\left( \frac{T}{2} \right)$$