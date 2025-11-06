 > [!definition]
> Let $\Omega:=\{ \pm 1 \}^n$ and $G$ be an [[graph|undirected graph]]. 
> 1. the ***MaxCut problem*** is the problem: $$x\in \underset{ x\in \Omega }{ \arg\max }\sum_{(u,v)\in E(G)}^{}\frac{1-x_{u}x_{v}}{2}=\underset{ x\in \Omega }{ \arg\min }\ x^\top Ax$$
---
##### Properties
> [!lemma] Proposition 1 
> Let $A$ be the symmetric adjacency matrix. Define: $$\mu_{\beta}(x)\propto \exp \left( \frac{\beta}{2}x^\top Lx \right) $$
> Then, $\lim_{ \beta \to \infty }\mu_{\beta}$ gives us a uniform distribution on the max cuts. 

We have that: $$\mu_{\beta}=\mathbb{E}_{z\sim\rho}[\mu]$$