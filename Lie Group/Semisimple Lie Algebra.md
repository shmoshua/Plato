#Definition #LieGroups 

> [!definition]
> A $\mathbb{K}$-[[Lie algebra]] $\mathfrak{g}$ is ***semisimple*** if there are [[Simple Lie Algebra|simple]] [[Ideal (Lie Algebra)|ideals]] $\mathfrak{h}_{1},\dots,\mathfrak{h}_{r}\unlhd \mathfrak{g}$ s.t. 
> 1. $\mathfrak{g}=\mathfrak{h}_{1}\oplus\dots \oplus \mathfrak{h}_{r}$ and 
> 2. $\left[ \sum_{i=1}^{r}X_{i},\sum_{i=1}^{r}Y_{i} \right]_{\mathfrak{g}}=\sum_{i=1}^{r}[X_{i},Y_{i}]_{\mathfrak{h_{i}}}$
- **Related definition**: A connected [[Lie group]] is ***semisimple*** if $\mathfrak{g}$ is semisimple.
---
##### Properties
> [!lemma] Theorem 1
> For a Lie algebra $\mathfrak{g}$, the following are equivalent:
> 1. $\mathfrak{g}$ is semisimple.
> 2. $K_{\mathfrak{g}}$ is non-degenerate, i.e. $\text{rad}(K_{\mathfrak{g}}):=\{ v\in \mathfrak{g}:K_{\mathfrak{g}}(v,w)=0, \forall w\in \mathfrak{g} \}=(0)$ or $\mathfrak{g}^{\bot}=(0)$.

> [!proof]-
> We have:
> 1. (1=>2): Assume $\mathfrak{g}=\mathfrak{g}_{1}\oplus\dots \oplus \mathfrak{g}_{r}$ with $\mathfrak{g}_{i}$ simple. Then, for all $X=\sum_{i=1}^{r}X_{i}\in \mathfrak{g}$, $$\text{ad}_{\mathfrak{g}}(X)=\begin{bmatrix}\text{ad}_{\mathfrak{g}_{1}}(X_{1})&\\&\ddots\\&&\text{ad}_{\mathfrak{g}_{r}}(X_{r})\end{bmatrix}$$Therefore, $K_{\mathfrak{g}}(X,Y)=\text{tr}(\text{ad}_{\mathfrak{g}}(X)\text{ad}_{\mathfrak{g}}(Y))=\sum_{i=1}^{r}\text{tr}(\text{ad}_{\mathfrak{g}_{i}}(X_{i})\text{ad}_{\mathfrak{g}_{i}}(Y_{i}))=\sum_{i=1}^{r}K_{\mathfrak{g}_{i}}(X_{i},Y_{i})$.
>    
>    Let $X\in \mathfrak{g}^{\bot}$. Then, $X_{i}\in (\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}:=\{ X\in \mathfrak{g}_{i}:K_{\mathfrak{g}_{i}}(X,Y)=0,\forall Y\in \mathfrak{g}_{i} \}$. Then, by [[Ideal (Lie Algebra)|Example 1]], $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}\unlhd \mathfrak{g}_{i}$ and by simpleness, $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=(0)$ or $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=\mathfrak{g}_{i}$. If $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=\mathfrak{g}_{i}$, then $K_{\mathfrak{g}_{i}}=0$ and by [[Killing Form|Cartan's criterion]], $\mathfrak{g}_{i}$ is solvable. Therefore, $\mathfrak{g}_{i}^{(1)}\neq \mathfrak{g}_{i}$ and as $\mathfrak{g}_{i}$ is simple, we have that $\mathfrak{g}_{i}^{(1)}=(0)$. Hence, $\mathfrak{g}_{i}$ is abelian, which is a contradiction. 
>    
>    This implies that $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=(0)$ for all $i$, which means $\mathfrak{g}^{\bot}=(0)$ and $K_{\mathfrak{g}}$ is non-degenerate. 
> 2. (2=>1): Assume that $K_{\mathfrak{g}}$ is non-degenerate. Then, 
> 	- **Claim 1: $\mathfrak{g}$ has no non-zero abelian ideal**: 
> 	  Let $\mathfrak{a}\unlhd \mathfrak{g}$ be an abelian ideal and $\mathfrak{g}=W\oplus \mathfrak{a}$. Then, for all $X\in \mathfrak{a}$, $$\text{ad}(X)=\begin{bmatrix}0&0\\ *&0\end{bmatrix}$$and for all $Y\in \mathfrak{g}$, $$\text{ad}(Y)=\begin{bmatrix}*&0\\ *&*\end{bmatrix}$$Therefore, $K_{\mathfrak{g}}(X,Y)=0$. Hence, $\mathfrak{a}\subseteq \mathfrak{g}^{\bot}=(0)$.
> 	- **Claim 2: If $\mathfrak{h}\unlhd \mathfrak{g}$ then $\mathfrak{h}\cap \mathfrak{h}^{\bot}=(0)$**:
> 	  Since $K_{\mathfrak{g}}$ is non-degenerate, we have $[X,Y]=0$ for all $X,Y\in \mathfrak{h}\cap \mathfrak{h}^{\bot}$. Therefore, $\mathfrak{h}\cap \mathfrak{h}^{\bot}$ is an abelian ideal of $\mathfrak{g}$ and by Claim 1, $\mathfrak{h}\cap \mathfrak{h}^{\bot}=(0)$.
> 	
> 	Since $K_{\mathfrak{g}}$ is non-degenerate, $\text{dim }\mathfrak{h}^{\bot}=\text{dim }\mathfrak{g}-\text{dim }\mathfrak{h}$ and hence as a vector space, $\mathfrak{g}=\mathfrak{h}\oplus \mathfrak{h}^{\bot}$. However, as $\mathfrak{h}$ and $\mathfrak{h}^{\bot}$ are both ideals, this is a Lie algebra direct sum. Therefore, we have: $$K_{\mathfrak{g}}=K_{\mathfrak{g}}|_{{\mathfrak{h}\times \mathfrak{h}}}\oplus K_{\mathfrak{g}}|_{{\mathfrak{h^{\bot}}\times \mathfrak{h^{\bot}}}}=K_{\mathfrak{h}}\oplus K_{\mathfrak{h}^{\bot}}$$by [[Killing Form|Proposition 1.2]]. Therefore, $K_{\mathfrak{h}}$ and $K_{\mathfrak{h}^{\bot}}$ are non-degenerate. We can conclude by recurrence on $\text{dim }\mathfrak{g}$.
---
##### Examples
> [!h] Example 1
> Let $V$ be a $\mathbb{K}$-inner product space. If $\mathfrak{g}\subseteq \mathfrak{gl}(V)$ is a $\mathbb{K}$-Lie subalgebra s.t. $Z(\mathfrak{g})=\{ 0 \}$ and self-adjoint, i.e. for all $A\in \mathfrak{g}$, $A^{*}\in \mathfrak{g}$. Then, 
> 1. $K_{\mathfrak{g}}$ is non-degenerate and $\mathfrak{g}$ is semisimple.

> [!proof]+
> In this proof, we assume $\mathbb{K}=\mathbb{R}$. The case $\mathbb{K}=\mathbb{C}$ is analogous. We can define an inner product on $\mathfrak{gl}(V)$ as: $$\braket{ A , B } :=\text{tr}_{V}(AB^{*}),\quad \forall A,B\in \mathfrak{gl}(V)$$We verify the positivity: Let $e_{1},\dots,e_{n}$ be the orthonormal basis of $V$. Then, $$\braket{ A , A } =\text{tr}_{V}(AA^{*})=\sum_{i,j=1}^{n}a_{ij}^{2}\geq 0$$with equality when $A=0$. Now, let's restrict this scalar product to $\mathfrak{g}$. Let $\theta:\mathfrak{gl}(\mathfrak{g})\to \mathfrak{gl}(\mathfrak{g})$ be the adjoint. If $T\in \mathfrak{gl}(\mathfrak{g})$ then: $$\braket{ TA , B } =\braket{ A , \theta(T)B },\quad \forall A,B\in \mathfrak{g} $$We now claim that $\text{ad}_{\mathfrak{g}}(X^{*})=\theta(\text{ad}_{\mathfrak{g}}(X))$ for all $X\in \mathfrak{g}$. Indeed, for all $A,B\in \mathfrak{g}$, $$\begin{align}\braket{ \text{ad}_{\mathfrak{g}}(X)A , B } &=\text{tr}_V([X,A]B^{*})\\&=\text{tr}_{V}(XAB^{*}-AXB^{*})\\&=\text{tr}_{V}(A(B^{*}X-XB^{*}))\\&=\text{tr}_{V}(A[X^{*},B]^{*})\\&=\braket{ A , \text{ad}_{\mathfrak{g}}(X^{*})B } \end{align}$$which shows the claim. Therefore, $\text{ad}(\mathfrak{g})$ is a $\theta$-invariant subalgebra of $\mathfrak{gl}(\mathfrak{g})$. Let then $E_{1},\dots,E_{m}$ be an orthonormal basis of $\mathfrak{g}$ w.r.t. $\braket{  ,  }$. Then, if $A\in \mathfrak{gl}(m,\mathbb{R})$, $\theta(A)=A^\top$. Hence, for all $X\in \mathfrak{g}$, $$K_{\mathfrak{g}}(X,X^{*})=\text{tr}_{\mathfrak{g}}(\text{ad}_{\mathfrak{g}}(X)\text{ad}_{\mathfrak{g}}(X^{*}))=\text{tr}_{\mathfrak{g}}(\underbrace{ \text{ad}_{\mathfrak{g}}(X) }_{ =:A }\theta(\text{ad}_{\mathfrak{g}}(X)))=\text{tr}(AA^\top)\geq 0$$ with equality when $A=0$. In other words, $\text{ad}_{\mathfrak{g}}(X)=0$. Therefore, $X\in Z(\mathfrak{g})=(0)$.
---
> [!h] Example 2 (Matrix Lie Algebras)
> We have that:
> 1. $\mathfrak{sl}(n,\mathbb{R}), \mathfrak{sl}(n,\mathbb{C})$ are semisimple.
> 2. $\mathfrak{o}(p,q)$ is semisimple.

> [!proof]-
> We have that:
> 1. 
> $\mathfrak{sl}(n,\mathbb{R}),\mathfrak{sl}(n,\mathbb{C})$ are invariant under $X\mapsto X^{*}$ and $Z(\mathfrak{sl}(n,\mathbb{R}))=\{ 0 \}$ and $Z(\mathfrak{sl}(n,\mathbb{C}))=\{ 0 \}$. Therefore, by Example 1, they are semisimple.
> 2. Let $X\in \mathfrak{o}(p,q)$. With $J_{p,q}:=\begin{bmatrix}-I_{p}&0\\0&I_{q}\end{bmatrix}$, we have $X^\top J_{p,q}+J_{p,q}X=0$. Then, by multiplying $J_{p,q}$ on both sides, $J_{p,q}X^\top+XJ_{p,q}=0$ and $X^\top\in \mathfrak{o}(p,q)$. Moreover, $Z(\mathfrak{o}(p,q))=\{ 0 \}$ and $\mathfrak{o}(p,q)$ is semisimple.