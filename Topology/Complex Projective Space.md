#Definition #AlgebraicTopology #Topology 

> [!definition]
> The ***complex projective space*** $\mathbb{C}\mathbb{P}^n$ is given by the [[Quotient Topology|quotient space]]:$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) /\{(z,\lambda z):z\in \mathbb{C}^{n+1} \backslash \{ 0 \},\lambda \in \mathbb{C}^{\times} \}$$Alternatively, it can be written as orbits$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) / \mathbb{C}^\times$$given by the [[group action]] $(\lambda,z)\mapsto \lambda z$.
- **Notation**: For the quotient map $\pi:\mathbb{C}^{n+1} \backslash \{ 0 \}\to \mathbb{C}\mathbb{P}^n$, we have that $[z_{0}:\dots :z_{n}]:=\pi(z_{0},\dots,z_{n})$.

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\pi$ is an open map.
> 1. $\mathbb{C}\mathbb{P}^n$ is compact Hausdorff.

> [!proof]-
> We have that:
> 1. let $U\subseteq \mathbb{C}^{n+1} \backslash \{ 0 \}$ be open. Then, we claim that: $$\pi ^{-1}(\pi(U))=\{ \lambda x:\lambda\in \mathbb{C}^\times,x\in U \}=\bigcup_{\lambda\in \mathbb{C}^\times}^{}\lambda U$$where we have an open set on the right. Indeed, if $\pi(z)\in \pi(U)$, then $\pi(z)=\pi(x)$ for some $x\in U$ and $z=\lambda x$ for some $\lambda\in \mathbb{C}^\times$. Conversely, we have for $\lambda\in \mathbb{C}^\times$ and $x\in U$, $\pi(\lambda x)=\pi(x)$ and $\pi(\lambda x)\in \pi(U)$.
> 1. To show that it is compact, we show that $\pi(S^{2n+2})=\mathbb{C}\mathbb{P}^n$. For $[z_{0}:\dots:z_{n}]\in \mathbb{C}\mathbb{P}^n$, we have that: $$\left( \frac{z_{0}}{\|z\|} ,\dots,\frac{z_{n}}{\|z\|} \right)\in S^{2n+2}$$As $S^{2n+2}$ is compact, $\mathbb{C}\mathbb{P}^n$ is compact.
>   
> 	  To show that it is Hausdorff, let $[z_{0}:\dots:z_{n}]$ an $[y_{0}:\dots:y_{n}]$ be two disjoint points in $\mathbb{C}\mathbb{P}^n$. Then, there exist disjoint $U,V\subseteq \mathbb{C}^{n+1} \backslash \{ 0 \}$ s.t. $z:=(z_{0},\dots,z_{n})\in U$ and $y:=(y_{0},\dots,y_{n})\in V$. Then, $\pi(U)$ and $\pi(V)$ are open neighborhoods of $\pi(z),\pi(y)$. We are left to show that they are disjoint. Assume that $\pi(x)\in \pi(U)\cap \pi(V)$. Then, 
> 2. 
---
> [!lemma] Lemma 2
> Consider the map $$f:B^{2n}\to \mathbb{C}\mathbb{P}^n,(w_{0},\dots,w_{n-1})\mapsto \pi(w_{0},\dots,w_{n-1},\sqrt{ 1-\|w\|^{2} })$$Then, 
> 1. $f$ is continuous 
> 2. $f$ is an embedding on $(B^{2n})^\circ$
> 3. $f(\partial B^{2n})\cong\mathbb{C}\mathbb{P}^{n-1}$

^70cd5d

> [!proof]-
> We have:
> 1. The map is continuous by definition. 
> 2. Now, to show the injectivity, let $(w_{0},\dots, w_{n-1})$ and $(z_{0},\dots,z_{n-1})\in (B^{2n})^\circ$. Then, if $$\pi(w_{0},\dots,w_{n-1},\sqrt{ 1-\|w\|^{2} })=\pi(z_{0},\dots,z_{n-1},\sqrt{ 1-\|z\|^{2} })$$Then, there exists $\lambda\in \mathbb{C}^\times$ s.t. $w_{i}=\lambda z_{i}$ and $\sqrt{ 1-\|w\|^{2} }=\lambda \sqrt{ 1-\|z\|^{2} }$. However, as $\sqrt{ 1-\|w\|^{2} }$ and $\sqrt{ 1-\|z\|^{2} }$ are both positive reals, we have that $\lambda$ is positive real. Hence, we have that: $$1-\lambda^{2}\|z\|^{2}=1-\|w\|^{2}=\lambda^{2}(1-\|z\|^{2})$$and $\lambda=1$. This shows the injectivity. Further, we have that $f$ is open as norm is an open map and so is $\pi$. Hence, $f$ is an embedding on $(B^{2n})^\circ$.
> 3. We have that: $$i:\mathbb{C}\mathbb{P}^{n-1}\to \mathbb{C}\mathbb{P}^n,\quad [z_{0}:\dots:z_{n-1}]\mapsto [z_{0}:\dots:z_{n-1}:0]$$is continuous and injective. As $\mathbb{C}\mathbb{P}^{n-1}$ is compact and $\mathbb{C}\mathbb{P}^{n}$ Hausdorff, we have that $i(\mathbb{C}\mathbb{P}^{n-1})$ is homeomorphic to $\mathbb{C}\mathbb{P}^{n-1}$. However, we have that $i(\mathbb{C}\mathbb{P}^{n-1})=f(\partial B^{2n})$.

^e573ab

---
> [!lemma] Theorem 3 (CW-complex)
> We have that:
> 1. $\mathbb{C}\mathbb{P}^n$ is a [[CW-complex]] of dimension $2n$.

^ae3d29

> [!proof]-
> Consider the following map: $$\Psi:\mathbb{C}\mathbb{P}^{n-1}\cup_{f_{\partial}}B^{2n}\to \mathbb{C}\mathbb{P}^n,\quad  [x]\mapsto \begin{cases}f(x)&x\in B^{2n}\\i(x)&x\in \mathbb{C}\mathbb{P}^{n-1} \end{cases}$$where $i:\mathbb{C}\mathbb{P}^{n-1}\to \mathbb{C}\mathbb{P}^n,[z_{0}:\dots:z_{n-1}]\mapsto [z_{0}:\dots: z_{n-1} : 0]$. Then, this is well-defined and continuous as $f$ and $i$ are and $f(\partial B^{2n})=i(\mathbb{C}\mathbb{P}^{n-1})$. We show that $\Psi$ is a homeomorphism. We have that $\mathbb{C}\mathbb{P}^{n-1}$ and $B^{2n}$ are both compact therefore, the LHS is compact. Further, $\mathbb{C}\mathbb{P}^{n}$ is Hausdorff. Therefore, it is left to show that $\Psi$ is a bijection. This can be done by showing that $f((B^{2n})^\circ)=\{ [z_{0}:\dots:z_{n}]\in \mathbb{C}\mathbb{P}^n :z_{n}\neq 0\}$ which is well-defined. 
> 
> Let $[z_{0}:\dots: z_{n}]\in \mathbb{C}\mathbb{P}^n$ with $z_{n}\neq 0$. Let $\alpha\in \mathbb{C}$ with $\left| \alpha \right|=1$ s.t. $\alpha z_{n}\in \mathbb{R}$. Then, let $$\lambda=\frac{1}{\sqrt{ \alpha^{2}z_{n}^{2}+\|z_{0:n-1}\|^{2} }}$$which is well-defined as $z_{n}\neq 0$ and $\alpha z_{n}\neq 0$. Then, we have that $$\begin{align}f(\lambda\alpha z_{0},\dots,\lambda\alpha z_{n-1})=[\lambda\alpha z_{0}:\dots:\lambda\alpha z_{n-1}:\sqrt{ 1- \lambda^{2}\|z_{0:n-1}\|^{2}}]\end{align}$$we conclude our proof by claiming that: $$(1- \lambda^{2}\|z_{0:n-1}\|^{2})=\lambda^{2}\alpha^{2}z_{n}^{2}$$
> 
> Now, we define a CW-complex where:
> 1. $K^{(0)}=\{ x \}=\mathbb{C}\mathbb{P}^{0}$ and
> 2. $I_{2n}:=\{ \sigma \}$ where $f_{\partial\sigma}=f|_{\partial B^{2n}}$.
> 
> Then, by above homeomorphism, we have that $K^{(2n)}\cong \mathbb{C}\mathbb{P}^n$. 

^7279ae

- **Corollary**: $\mathbb{C}\mathbb{P}^1\cong S^2$ given by $\mathbb{C}\mathbb{P}^1\to \mathbb{C}\cup \{ \infty \},[z_{1}:z_{2}]\mapsto \frac{z_{1}}{z_{0}}$.
---