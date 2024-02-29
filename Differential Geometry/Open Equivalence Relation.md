#Definition #DifferentialGeometry 

> [!definition]
> Let $X$ be a [[topological space]]. An equivalence relation $\sim$ on $X$ is ***open*** if $\pi:X \to X \backslash \sim$ is an [[Open and Closed Maps|open map]].
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a topological space and $\sim$ an open equivalence relation on $X$.
> 1. If $X$ is second-countable, then so is $X \backslash \sim$.
> 2. $X \backslash \sim$ is Hausdorff if and only if $R:=\{ (x,y)|x\sim y \}\subseteq X^{2}$ is closed.

> [!proof]-
> We have: 
> 1. Let $\mathcal{B}$ be the basis of open subsets of $X$ and set $\mathcal{B}':=\{ \pi(U):U\in \mathcal{B} \}$. Since $\pi$ is open, $\pi(U)$ are open sets. Therefore, for any open set $V\subseteq X \backslash \sim$, we have: $$\pi ^{-1}(V)=\bigcup_{U\in \mathcal{B},U\subseteq \pi ^{-1}(V)}^{}U,\quad V=\bigcup_{U\in \mathcal{B},U\subseteq \pi ^{-1}(V)}^{}\pi(U)$$Therefore, $\mathcal{B}'$ is a basis as well.
> 2. First, suppose that $X \backslash \sim$ is Hausdorff. We will show that $X \times X \backslash R$ is open. Let $(x,y)\in X\times X \backslash R$. Then, $\pi(x)\neq \pi(y)$. Therefore, there exists disjoint open subsets $U_{x},U_{y}\subseteq X \backslash\sim$ containing $\pi(x)$ and $\pi(y)$ respectively. It follows that $\pi ^{-1}(U_{x})\times \pi ^{-1}(U_{y})$ is an open subset containing $(x,y)$.
>    
>    Finally, observe that $\pi ^{-1}(U_{x})\times \pi ^{-1}(U_{y})$ does not intersect $R$. Suppose $(z_{1},z_{2})\in R\cap\pi ^{-1}(U_{x})\times \pi ^{-1}(U_{y})$. Then, $\pi (z_{1})=\pi (z_{2})$ and $\pi(z_{1})\in U_{x}$ while $\pi(z_{2})\in U_{y}$ which is a contradiction.
>    
>    Conversely, assume that $R$ is closed. Let $x,y\in X$ s.t. $\pi(x)\neq \pi(y)$. Then, $(x,y)\notin R$. SInce $R$ is closed, there is an open set $V_{x},V_{y}\subseteq X$ containing $x,y$ s.t. $V_{x}\times V_{y}\subseteq X\times X \backslash R$. In other words, $\pi(V_{x})\cap \pi(V_{y})=\varnothing$. As $\pi$ is open, $\pi(V_{x}),\pi(V_{y})$ separates $\pi(x),\pi(y)$. Therefore, $X \backslash \sim$ is Hausdorff.
---
##### Example
> [!h] Example 1 (Real Projective Space)
> The projective space $\mathbb{P}^n \mathbb{R}$ is defined as the quotient of $X= \mathbb{R}^{n+1} \backslash \{ 0 \}$ with the equivalence relation: $$x\sim y\iff \exists\lambda\in \mathbb{R}^{*}: x=\lambda y$$
> 1. $\sim$ is open.
> 2. $R$ is closed.
> 3. $\mathbb{P}^n\mathbb{R}$ is a [[smooth manifold]] of dimension $n$.

> [!proof]-
> We have that:
> 1. Let $A\subseteq \mathbb{R}^{n+1} \backslash\{ 0 \}$ be open. Then, $$\pi^{-1}(\pi(A))=\bigcup_{\lambda\in \mathbb{R}^{*}}^{}\lambda A$$is open.
> 2. We define: $$\begin{array}{cccc} {f:}&{\mathbb{R}^{n+1}\times \mathbb{R}^{n+1}}&\to&{\mathbb{R}}\\&{(x,y)} &\mapsto & {\sum_{i,j=1}^{n+1}(x_{i}y_{j}-x_{j}y_{i})^{2}} \end{array}{}$$Then, $R=f^{-1}(\{ 0 \})$ which is closed.
> 3. We will equip $\mathbb{P}^n\mathbb{R}$ with charts. Define $\tilde{U}_{i}:=\{ x=(x_{1},\dots,x_{n+1})\subseteq \mathbb{R}^{n+1}:x_{i}=1 \}$. Then, $\pi ^{-1}(\pi(\tilde{U}_{i}))=\{ (x_{1},\dots,x_{n+1})|x_{i}\neq 0 \}$ is open and $U_{i}:=\pi(\tilde{U}_{i})\subseteq \mathbb{P}^n\mathbb{R}$ is open as well. Therefore, $$\pi|_{\tilde{U}_{i}}:\tilde{U}_{i}\to U_{i}$$is continuous by definition, injective and open, i.e. it is a homeomorphism. Consider another map: $$\begin{array}{cccc} {\text{pr}_{i}:}&{\mathbb{R}^{n+1}}&\to&{\mathbb{R}^n}\\&{x} &\mapsto & {(x_{1},\dots,x_{i-1},x_{i+1},\dots,x_{n+1})} \end{array}$$Then, $\text{pr}_{i}|_{\tilde{U}_{i}}$ is a homeomorphism. Therefore, $\varphi_{i}=\text{pr}_{i}\circ(\pi|_{\tilde{U}_{i}})^{-1}$ is a homeomorphism. Combined with the fact that $\bigcup_{i=1}^{n+1}U_{i}=\mathbb{P}^n\mathbb{R}$, $(U_{i},\varphi_{i})$ is an atlas on $\mathbb{P}^n\mathbb{R}$.
>    
>    Now let $i<j\in [n+1]$ and we have:
>    1. $\varphi_{i}(U_{i}\cap U_{j})=\{ y\in \mathbb{R}^n:y_{j-1}\neq 0 \}$
>    2. $\varphi_{j}(U_{i}\cap U_{j})=\{ y\in \mathbb{R}^n:y_{i}\neq 0 \}$
>    
>    Then, $$\begin{array}{cccc} {\theta_{ji}:}&{\varphi_{i}(U_{i}\cap U_{j})}&\to&{\varphi_{j}(U_{i}\cap U_{j})}\\&{y} &\mapsto & {\frac{1}{y_{j-1}}(y_{1},\dots,y_{i-1},1,y_{i},\dots,y_{j-1},y_{j+1},\dots,y_{n})} \end{array}{}$$and hence is smooth. 
---
