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

> [!proof]-
> Consider the map: $$\Psi:\text{GL}(n,\mathbb{R})\to \text{Aut}(\mathbb{R}^n),\quad A\mapsto (x\mapsto Ax)$$
> Then, 
> 1. **Showing $\Psi(A)\in \text{Aut}(\mathbb{R}^n)$:**
>    We know that $\Psi(A)$ is continuous, bijective with a continuous inverse. Further, the linearity guarantees that it is a homomorphism.
> 2. **Showing $\Psi$ is injective**:
>    Let $\Psi(A)(x)=x$ for all $x\in \mathbb{R}^n$. Then, $Ax=x$ for all $x\in \mathbb{R}^n$ and $A=I_{n}$.
> 3. **Showing $\Psi$ is surjective**:
>    Let $\varphi\in \text{Aut}(\mathbb{R}^n)$. Let $A:=[A_{1}|\dots|A_{n}]$ where $A_{i}:=\varphi(e_{i})$. Then, for any $x:=\sum_{i=1}^{n}\xi_{i}e_{i}\in \mathbb{R}^n$, $$\Psi(A)(x)=\sum_{i=1}^{n}\xi_{i}A_{i}=\sum_{i=1}^{n}\xi_{i}\varphi(e_{i})=\varphi\left( \sum_{i=1}^{n}\xi_{i}e_{i} \right)=\varphi(x)$$
> 4. **Showing that $\Psi$ is continuous**:
>    We want to show that if $A_{n}\to A$, $\Psi(A_{n})\to \Psi(A)$ in $\text{Aut}(\mathbb{R}^n)$. 
>    
>    As $\mathbb{R}^n$ is metric, the compact open topology coincides with the topology of compact convergence. Let $K$ compact $\varepsilon>0$ s.t $$\mathcal{U}(\Psi(A),K,\varepsilon):=\{g:\mathbb{R}^n\to \mathbb{R}^n|\ \text{sup}_{x\in K}\|Ax-g(x)\|_{2}<\varepsilon  \}$$As we have $\|(A_{n}-A)x\|_{2}\leq\|A_{n}-A\|\|x\|_{2}\leq\|A_{n}-A\|_{F}\|x\|_{2}$, if we let $c:=\sup_{x\in K}\|x\|_{2}$, we find $N$ s.t. $\|A_{n}-A\|_{F}< \varepsilon /c$ for all $n\geq N$. Then, for any $x\in K$, $\|(A_{n}-A)x\|_{2}<\varepsilon$ and $\Psi(A_{n})\in \mathcal{U}(\Psi(A),K,\varepsilon)$. This proves the statement.
> 5. **Showing that $\Psi ^{-1}$ is continuous**:
>    Let $B_{<\varepsilon}(I)$ be an open ball. Then, let $K:= B_{\leq 1}(0)$ and $A\in B_{<\varepsilon}(I)$. From the equivalence of norm, there exists $\varepsilon'$ s.t. if $\|A-B\|<\varepsilon'$ then $\|A-B\|_{F}<\varepsilon$. Then, $$\mathcal{U}(\Psi(A),K,\varepsilon')\subseteq \Psi(B_{<\varepsilon}(I))$$This proves the statement.

>    