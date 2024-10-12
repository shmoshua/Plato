#Definition #ML 
> [!definition]
>  For a set $X$, a ***Gaussian process*** is the set  $f:=\{ f(x) \}_{x\in X}\subseteq \mathbb{R}$ with the ***mean function*** $\mu:X\to \mathbb{R}$ and the ***covariance function*** $k:X \times X\to \mathbb{R}$ s.t. 
>  1. for every finite $A=\{ x_{1},\dots,x_{n} \}\subseteq X$, $$f(A):=(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}\left( \mu_{A},K_{AA}\right)$$where $\mu_{A}:=(\mu(x_{1}),\dots,\mu(x_{n}))$ and $K_{AA}:=\begin{bmatrix}k(x_{i},x_{j})\end{bmatrix}_{i,j\in [n]}$.
> 
> A Gaussian process is denoted as $f \sim \text{GP}(\mu,k)$.

^fc4049

---
##### Properties
> [!lemma] Proposition 1
> For a Gaussian process $\text{GP}(\mu,k)$ on $X$,
> 1. $k$ is a SPsD [[kernel]]. Conversely, any SPsD kernel $k:X\times X\to \mathbb{R}$ can be a covariance function on a Gaussian process of $X$. 

^acc53b

> [!proof]-
> We have that:
> 1. for all $x,y\in X$, $f(\{ x,y \}):=(f(x),f(y)) \sim \mathcal{N}(\mu_{\{ x,y \}},K_{\{ x,y \}})$ where: $$K_{\{ x,y \}}:=\begin{bmatrix}k(x,x)&k(x,y)\\k(y,x)&k(y,y)\end{bmatrix}$$As covariance matrices are symmetric, we have that $k(x,y)=k(y,x)$. 
>    
>    Further, the Gram matrix is positive semidefinite by definition. 

^d1890f

---
> [!lemma] Proposition 2 (Sum of Gaussian Processes)
> For independent $f\sim \text{GP}(\mu,k)$ and $f' \sim \text{GP}(\mu',k')$, we have that:
> 1. $f+f' \sim \text{GP}(\mu+\mu',k+k')$

^ec2539

> [!proof]-
> We have that for $A\subseteq\{ x_{1},\dots,x_{n} \}\subseteq X$, $$f(A)+f'(A)\sim \mathcal{N}(\mu_{A}+\mu'_{A},K_{AA}+K'_{A A})$$This proves the statement.

^f3ea71

- **Remark**: Hence, wlog we may assume that the prior has mean 0, i.e. $f \sim \text{GP}(0,k)$, as if otherwise we can express $g=f-\mu \sim \text{GP}(0,k)$ from $\mu \sim \text{GP}(\mu,0)$.  ^5ba3f5
---
> [!lemma] Proposition 3 (Conditional Gaussian Process)
> Let $f\sim \text{GP}(\mu,k)$ on $X$ and set $A:=\{ x_{1},\dots,x_{n} \}\subseteq X$. For $y_{i}:=f(x_{i})+\varepsilon_{i}$ for $\varepsilon_{i} \sim \mathcal{N}(0,\sigma^{2})$:
> $$p(f|x_{1:n},y_{1:n})=\text{GP}(f;\mu',k')$$ where:
> 1. $\mu'(x)=\mu(x)+[k(x,x_{i})]_{i}^\top (K_{A A}+\sigma^{2}I)^{-1}[y_{i}-\mu(x_{i})]_{i}$.
> 2. $k'(x,x')=k(x,x')-[k(x,x_{i})]_{i}^\top(K_{AA}+\sigma^{2}I)^{-1}[k(x',x_{i})]_{i}$.

^6676d7

> [!proof]-
> We have that:
> 1. for any $B:=\{ z_{1},\dots,z_{m} \}\subseteq X$, we have: $$(f(B),f(A))\sim \mathcal{N}\left((\mu_{B},\mu_{A}  ),\begin{bmatrix}K_{BB}&K_{BA}\\K_{A B}&K_{A A}\end{bmatrix}\right) $$where $K_{CD}=[k(a,b)]_{a\in C,b\in D}$. Then, $$(f(B),y_{1:n})\sim \mathcal{N}\left((\mu_{B},\mu_{A}  ),\begin{bmatrix}K_{ B B}&K_{BA}\\K_{AB}&K_{A A}+\sigma^{2}I\end{bmatrix}\right)$$Therefore, by [[Gaussian Distribution| Gaussian distribution marginals]], $$p(f(B)|y_{1:n})=\mathcal{N}(\mu'_{B},K'_{BB})$$ where :
> 	1. $\mu'_{B}:=\mu_{B}+K_{BA}(K_{ A A}+\sigma^{2}I)^{-1}(y_{1:n}-\mu_{A})$
> 	1. $K'_{B B}:=K_{B B }-K_{BA}(K_{AA}+\sigma^{2}I)^{-1}K_{AB}$.
> 	
> 	and $f|y_{1:n},x_{1:n}$ is a Gaussian process. We then simply check that when $B=\{ x \}$ and $B=\{ x,x' \}$
> 	1. $\mu'(x)=\mu(x)+[k(x,x_{i})]_{i}^\top (K_{A A}+\sigma^{2}I)^{-1}(y_{1:n}-\mu_{A})$.
> 	2. $k'(x,x')=k(x,x')-[k(x,x_{i})]_{i}^\top(K_{AA}+\sigma^{2}I)^{-1}[k(x',x_{i})]_{i}$

^9b4fed


---
> [!lemma] Proposition 4
> Let $f\sim \text{GP}(\mu,k)$ and $y=f(x)+\varepsilon$ where $\varepsilon \sim \mathcal{N}(0,\sigma_{n}^{2})$. Then, we have that: $$y_{1:n}|x_{1:n} \sim \mathcal{N}(\mu)$$
---
##### Examples
> [!h] Example 1 (Constant GP)
> We have that:
> 1. for any function $f:X \to \mathbb{R}$, $f \sim \text{GP}(f,0)$.

> [!proof]-
> Let $A:=\{ x_{1},\dots,x_{n} \}$. Then, we have that: $$(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}((f(x_{1}),\dots,f(x_{n})),0)$$
---
