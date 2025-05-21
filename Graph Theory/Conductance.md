#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an unweighted connected [[graph]]. 
> 1. for $S\subseteq V$, the ***conductance*** $\phi(S)$ of $S$ is given by: $$\phi(S):=\frac{e(S, V \backslash S)}{\min \{ \text{vol}(S),\text{vol}(V \backslash S) \}}$$where $\text{vol}(A):=\sum_{v\in A}^{}d(v)$. 
> 2. the ***conductance*** of $G$ is given by: $$\phi(G):=\min _{S\subseteq V}\phi(S)$$

^3ce776

- **Remark**: $\phi(S)=\phi(V \backslash S)$ for all $S\subseteq V$. 
- **Remark**: Finding the conductance of a graph is NP-hard.
---
##### Properties
> [!lemma] Lemma 1
> Let $S\subseteq V$ with $\text{vol}(S)\leq \text{vol}(V) / 2$. Then, $$\phi(S)=\frac{1_{S}^\top L 1_{S}}{1_{S}^\top D 1_{S}}$$ where $L$ is the [[Graph Laplacian|Laplacian]] and $D:=\text{diag}(d)$. 

^618b9c

> [!proof]-
> We have that: $$\phi(S):=\frac{e(S, V \backslash S)}{\min \{ \text{vol}(S),\text{vol}(V \backslash S) \}}=\frac{e(S, V \backslash S)}{ \text{vol}(S)}$$Then,
> 1. For the numerator: $$e(S, V \backslash S)=\sum_{(u,v)\in E}^{}(1_{S}(u)-1_{S}(v))^{2}=1_{S}^\top L 1_{S}$$
> 2. For the denominator: $$\text{vol}(S)=1^\top_{S}d=1_{S}^\top D 1_{S}$$

^2b2dcf

- **Corollary**: It is given that:$$\phi(G)=\min_{\begin{array}. S\subseteq V\\\text{vol}(S)\leq \text{vol}(V) / 2\end{array}}\frac{1_{S}^\top L 1_{S}}{1_{S}^\top D 1_{S}}$$
---
> [!lemma] Theorem 2 (Cheeger)
>  Let $N:=D^{-1/2}LD^{-1/2}$ be the normalized Laplacian. Then, 
>  $$\frac{\lambda_{2}}{2}\leq \phi(G)\leq \sqrt{ 2\lambda_{2} }$$where $\lambda_{2}$ is the 2nd smallest eigenvalue of $N$. 

^1c0f8c

> [!proof]+
> Notice that: $y:=D^{1/2}1$ is an eigenvector of $\lambda_{1}(N)$. By Courant-Fischer, $$\lambda_{1}(N)=\min_{x\neq 0} \frac{x^\top Nx}{x^\top x}\leq \frac{y^\top D^{ -1/2}LD^{-1/2}y}{y^\top y}=\frac{1^\top L 1}{1^\top D 1}=0$$Further, as $N$ is PSD, $\lambda_{1}(N)=0$ and $\text{ker } N=\{ x: x^\top Nx = 0 \}$. Now, for $\lambda_{2}$, 
> 
> $$\lambda_{2}=\min_{0\neq x {\bot}D^{1/2}1}\frac{x^\top Nx}{x^\top x}=\min_{0\neq z {\bot}d}\frac{z^\top D^{1/2}ND^{1/2}z}{z^\top Dz}=\min_{0\neq z {\bot}d}\frac{z^\top Lz}{z^\top Dz}$$
> 
> We now show the lower bound first.
> 1. Let $S\subseteq V$ with $\text{vol}(S) \leq \text{vol}(V) / 2$. Let $\alpha:= \frac{\text{vol}(S)}{\text{vol}(V)}$. Define $z_{S}:=1_{S}-\alpha 1$. Then, we have: $$d^\top z_{S}=d^\top 1_{S}-\alpha d^\top 1=\text{vol}(S)-\alpha \cdot  \text{vol}(V)=0$$Then, we have that by $L 1 = 0$,  $$z_{S}^\top L z_{S}=1_{S}^\top L 1_{S}- 2\alpha 1_{S}^\top L 1+\alpha^{2} 1^\top L 1=1_{S}^\top L 1_{S}$$and by $\text{vol}(S)\leq \text{vol}(V) / 2$$$z^\top_{S} Dz_{S}=\text{vol}(S)-2\alpha \text{vol}(S)+\alpha^{2}\text{vol}(V)=\text{vol}(S)-\frac{\text{vol}(S)^{2}}{\text{vol}(V)}\geq \frac{1}{2}\text{vol}(S)=\frac{1}{2}1_{S}^\top D 1_{S}$$Hence, for any $S\subseteq V$ with $\text{vol}(S)\leq \text{vol}(V) / 2$, $$\phi(G)=\min_{\begin{array}. S\subseteq V\\\text{vol}(S)\leq \text{vol}(V) / 2\end{array}}\frac{1_{S}^\top L 1_{S}}{1_{S}^\top D 1_{S}}\geq \frac{1}{2} \min_{\begin{array}. S\subseteq V\\\text{vol}(S)\leq \text{vol}(V) / 2\end{array}}\frac{z_{S}^\top L z_{S}}{z_{S}^\top D z_{S}}\geq \frac{\lambda_{2}}{2}$$
> 2. It suffices to show that for any $0\neq z {\bot} d$, we can find $S\subseteq V$ with $\text{vol}(S)\leq \text{vol}(V) / 2$ s.t. $$\frac{1^\top _{S}L 1_{S}}{ 1^\top _{S}D 1_{S}}\leq \sqrt{ \frac{2 z^\top Lz}{z^\top D z} }$$To show this, modulo renumbering, we may assume that $z_{1}\leq\dots\leq z_{n}$. Let now 
> 	1. $z_{c}:=z-\alpha 1$ s.t. $\sum_{z_{c}(i)<0}^{}d(i)< \text{vol}(V) / 2$ and $\sum_{z_{c}(i)\leq 0}^{}d(i)\geq \text{vol}(V) / 2$. 
> 	2. $z_{sc}:=\beta z_{c}$ for some $\beta\in \mathbb{R}$ s.t. $z_{sc}(1)^{2}+z_{sc}(n)^{2}=1$. 
> 	
> 	We now claim that $\frac{z^\top Lz}{z^\top Dz}\geq \frac{z_{sc}^\top Lz_{sc}}{z_{sc}^\top Dz_{sc}}$. 

^6f10a3

