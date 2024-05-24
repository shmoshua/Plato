#Definition #Algebra

> [!definition]
> Let $K$ be a field. The ***general linear group*** for $n\in \mathbb{N}$, denoted as $(\text{GL}(n,K),\cdot)$ is defined as: $$\text{GL}(n,K):=\{  A\in \text{M}(n,K):\det(A)\neq 0 \}$$
> where $\text{M}(n,K)$ is the set of all $n\times n$ matrices with elements in $K$ as entries.

- $\text{GL}(1,\mathbb{R})\cong (\mathbb{R}^*,\cdot)$ which means $\text{GL}(1)$ is abelian.
- For $n>1$, $\text{GL}(n,\mathbb{R})$ is non-abelian as matrix multiplications don't commute.
---
##### Properties
> [!lemma] Proposition 1
> Consider the injection: $$\begin{array}{cccc} {\Psi:}&{\text{GL}(n,\mathbb{R})}&\to&{\text{Homeo}(\mathbb{R}^n)}\\&{A} &\mapsto & {(x\mapsto Ax)} \end{array}{}$$Then, 
> 1. $\Psi(\text{GL}(n,\mathbb{R}))\subseteq \text{Homeo}(\mathbb{R}^n)$ is closed w.r.t. [[compact-open topology]].
> 2. the induced subspace topology coincides with the euclidean topology on $\text{GL}(n,\mathbb{R})$.

> [!proof]-
> We have: 
> 1. We can characterize: $$\Psi(\text{GL}(n,\mathbb{R}))=\{ f\in \text{Homeo}(\mathbb{R}^n): f(\lambda a+b)=\lambda f(a)+f(b), \forall\lambda,a,b\in \mathbb{R} \}$$Then, for $\lambda,a,b\in \mathbb{R}$, the evaluation map $f\mapsto f(\lambda a+b)-\lambda f(a)-f(b)$ is continuous and therefore, $$\Psi(\text{GL}(n,\mathbb{R}))=\bigcap_{\lambda,a,b\in \mathbb{R}}^{}\text{ker }\text{ev}_{\lambda,a,b}$$is a closed set.
---
> [!lemma] Proposition 2
> We have that:
> 1. $\text{GL}(n,\mathbb{R})\cong \text{Aut}(\mathbb{R}^n)$.

> [!proof]+
> Consider the map: $$\Psi:\text{GL}(n,\mathbb{R})\to \text{Aut}(\mathbb{R}^n),\quad A\mapsto (x\mapsto Ax)$$
> Then, 
> 1. **Showing $\Psi(A)\in \text{Aut}(\mathbb{R}^n)$:**
>    We know that $\Psi(A)$ is continuous, bijective with a continuous inverse. Further, the linearity guarantees that it is a homomorphism.
> 2. **Showing $\Psi$ is injective**:
>    Let $\Psi(A)(x)=x$ for all $x\in \mathbb{R}^n$. Then, $Ax=x$ for all $x\in \mathbb{R}^n$ and $A=I_{n}$.
> 3. **Showing $\Psi$ is surjective**:
>    Let $\varphi\in \text{Aut}(\mathbb{R}^n)$. Let $A:=[A_{1}|\dots|A_{n}]$ where $A_{i}:=\varphi(e_{i})$. Then, for any $x:=\sum_{i=1}^{n}\xi_{i}e_{i}\in \mathbb{R}^n$, $$\Psi(A)(x)=\sum_{i=1}^{n}\xi_{i}A_{i}=\sum_{i=1}^{n}\xi_{i}\varphi(e_{i})=\varphi\left( \sum_{i=1}^{n}\xi_{i}e_{i} \right)=\varphi(x)$$
> 4. **Showing that $\Psi$ is continuous**:
>    We want to show that if $A_{n}\to A$
>    
>    Let $K$ compact and $U$ open in $\mathbb{R}^n$, then: $$S(K,U):=\{ \varphi\in \text{Aut}(\mathbb{R}^n):\varphi(K)\subseteq U \}$$We want to show that $\Psi ^{-1}(S(K,U))$ is open. 
>    
>    
>    Let $r,\varepsilon>0$. Then, we define: $$S(r,\varepsilon):=\{ \varphi\in \text{Aut}(\mathbb{R}^n):\varphi(B_{\leq r}()) \}$$ $S(K,U)$ be 