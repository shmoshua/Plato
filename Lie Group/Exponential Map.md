#Definition #Analysis #LieGroups 

> [!definition]
> The ***exponential map*** is a function $\exp:\text{Mat}_{n,n}(\mathbb{R})\to \text{Mat}_{n,n}(\mathbb{R})$ given as: $$\exp(A):=\sum_{n=0}^{\infty}\frac{A^n}{n!}$$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the power series $\exp(A)$ converges uniformly on balls of finite radius in $\text{Mat}_{n,n}(\mathbb{R})$ to a smooth map.
> 2. if $[A,B]=0$, $\exp(A+B)=\exp(A)\exp(B)$ and $\exp(A)\in \text{GL}(n,\mathbb{R})$.
> 3. for any $A\in \text{GL}(n,\mathbb{R})$, $$\varphi_{A}:\mathbb{R}\to \text{GL}(n,\mathbb{R}),\quad t\mapsto \exp(tA)$$is a smooth homomorphism with $\varphi_{A}'(0)=A$. 
> 4. any smooth homomorphism $\psi:\mathbb{R}\to \text{GL}(n,\mathbb{R})$ is of the form $\psi(t)=\exp(t\psi'(0))$.

> [!proof]+
> We have:
> 1. Let $r>0$ and for all $A\in \text{Mat}_{n,n}(\mathbb{R})$ with $\|A\|\leq r$ and $N\geq 1$, we have: $$\left\| \sum_{n=0}^{N} \frac{A^n}{n!} \right\| \leq \sum_{n=0}^{N}\frac{\|A\|^n}{n!}\leq\exp(\|A\|)\leq \exp(r)$$