#Definition #PAI 

> [!definition]
> Let $p(x_{1:n})$ be a [[Distribution|joint distribution]]. A ***Bayesian network*** for $p$ is a [[directed acyclic graph]] $G$ on $[n]$ s.t. 
> 1. $v\to w\iff x_{v}\in S_{w}$ where $p(x_{1:n})=\prod_{i=1}^{n}p(x_{i}|S_{i})$ for $S_{i}\subseteq \{ x_{k}:k\in [i-1] \}$.
- **Remark**: One can also add dotted nodes to represent deterministic values, 
---
##### Properties
---
##### Examples
> [!h] Example 1 (Bayesian Linear Regression)
> Let us have the [[Linear Regression|BLR]] problem where: 
> 1. $p(w)=\mathcal{N}(0, \sigma^2_{p}I)$
> 2. $p(y_{1:n}|x_{1:n},w)=\prod_{i=1}^{n}p(y_{i}|x_{i},w)$ where $y_{i}=w^\top x_{i}+\varepsilon_{i}$ where $\varepsilon_{i} \sim \mathcal{N}(0,\sigma^{2}_{n})$
>    
> Then, the Bayesian network 