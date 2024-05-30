#Definition #Analysis #LieGroups 

> [!definition]
> The ***exponential map*** is a function $\exp:\text{Mat}_{n,n}(\mathbb{R})\to \text{Mat}_{n,n}(\mathbb{R})$ given as: $$\exp(A):=\sum_{n=0}^{\infty}\frac{A^n}{n!}$$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the power series $\exp(A)$ converges uniformly on balls of finite radius in $\text{Mat}_{n,n}(\mathbb{R})$ to a smooth map.
> 2. if $[A,B]=0$, $\exp(A+B)=\exp(A)\exp(B)$ and $\exp(A)\in \text{GL}(n,\mathbb{R})$.
> 3. for any $A\in \text{Mat}_{n,n}(\mathbb{R})$, $$\varphi_{A}:\mathbb{R}\to \text{GL}(n,\mathbb{R}),\quad t\mapsto \exp(tA)$$is a smooth homomorphism with $\varphi_{A}'(0)=A$. 
> 4. any smooth homomorphism $\psi:\mathbb{R}\to \text{GL}(n,\mathbb{R})$ is of the form $\psi(t)=\exp(t\psi'(0))$.

> [!proof]-
> We have:
> 1. Let $r>0$ and for all $A\in \text{Mat}_{n,n}(\mathbb{R})$ with $\|A\|\leq r$ and $N\geq 1$, we have: $$\left\| \sum_{n=0}^{N} \frac{A^n}{n!} \right\| \leq \sum_{n=0}^{N}\frac{\|A\|^n}{n!}\leq\exp(\|A\|)\leq \exp(r)$$Therefore, $\exp(A)$ converges uniformly on $B_{\leq r}(0)$.
>    
>    For partial derivatives, we have:$$\frac{ \partial  }{ \partial x_{ij} } X^n=\sum_{k_{1}+k_{2}=n-1}^{}X^{k_{1}}E_{ij}X^{k_{2}}$$Therefore, $\left\| \frac{ \partial  }{ \partial x_{ij} }X^n \right\|\leq n\|X^{n-1}\|$. Now, for any partial derivation of order $k$, $$\left\| \frac{ \partial^\alpha }{ \partial x_{\alpha}}X^n  \right\|\leq n(n-1)\dots(n-k+1)\left\| X^{n-k} \right\|  $$for $n\geq k$. This shows that $\sum_{n=0}^{\infty}\frac{ \partial^\alpha }{ \partial x_{\alpha} }\frac{X^n}{n!}$ converges uniformly on balls of finite radius. This shows that $\exp$ is smooth.
> 2. if $AB=BA$ then: $$(A+B)^n=\sum_{k=0}^{n} {n \choose k}A^k B^{n-k}$$Therefore, $$\exp(A+B)=\sum_{n=0}^{\infty}(A+B)^n / n! =\sum_{n=0}^{\infty}\sum_{k=0}^{n}\frac{A^kB^{n-k}}{k!(n-k)!}=\sum_{k=0}^{\infty}\frac{A^k}{k!}\sum_{n=k}^{\infty}\frac{B^{n-k}}{(n-k)!}=\exp(A)\exp(B)$$Further, $I=\exp(0)=\exp(A-A)=\exp(A)\exp(-A)$ and $\exp(A)\in \text{GL}(n,\mathbb{R})$.
> 3. For $t,s\in \mathbb{R}$, $[tA,sA]=0$. Therefore, $$\exp(tA+sA)=\exp(tA)\exp(sA)$$and $\varphi$ is a homomorphism. Furthermore, $\varphi_{A}$ is smooth as $\exp$ is smooth. Lastly, $$\varphi'_{A}(0)=\left. \frac{d}{dt} \right| _{t=0}\exp(tA)=\left. \frac{d}{dt} \right| _{t=0}\sum_{n=0}^{\infty} \frac{A^nt^n}{n!}=\sum_{n=0}^{\infty}\frac{A^{n+1}0^{n}}{n!}=A$$
> 4. Let $\psi:\mathbb{R}\to \text{GL}(n,\mathbb{R})$. Then, $$\psi'(t)=\left. \frac{d}{ds} \right| _{s=0}\psi(t+s)=\psi(t) \left. \frac{d}{ds} \right| _{s=0}\psi(s)=\psi(t)\psi'(0)$$By uniqueness of the solution of ODEs, $\psi(t)=C\cdot \exp(t\cdot \psi'(0))$. As $\psi(0)=I$, $C=1$. 
