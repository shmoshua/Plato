#Definition #LieGroups 

> [!definition]
> For a $\mathbb{K}$-[[Lie algebra]] $\mathfrak{g}$, the ***Killing form*** of $\mathfrak{g}$ is the symmetric bilinear form: $$K_{\mathfrak{g}}:\mathfrak{g\times g}\to \mathbb{K},\quad (x,y)\mapsto \text{tr}(\text{ad}(x)\text{ad}(y))$$
---
##### Properties
> [!lemma] Proposition 1
> For a $\mathbb{K}$-Lie algbera:
> 1. $K_{\mathfrak{g}}(\text{ad}(z)x,y)+K_{\mathfrak{g}}(x,\text{ad}(z)y)=0$ for all $x,y,z\in \mathfrak{g}$.
> 2. for $\mathfrak{h}\unlhd \mathfrak{g}$, $K_{\mathfrak{g}}|_{\mathfrak{h}\times \mathfrak{h}}=K_{\mathfrak{h}}$

> [!proof]-
> We have that: 
> 1. For 1. $$\begin{align}K_{\mathfrak{g}}(\text{ad}(z)x,y)+K_{\mathfrak{g}}(x,\text{ad}(z)y)&=\text{tr}(\text{ad}([z,x])\text{ad}(y))+\text{tr}(\text{ad}(x)\text{ad}([z,y]))\\&=\text{tr}([\text{ad}(z),\text{ad}(x)]\text{ad}(y))+\text{tr}(\text{ad}(x)[\text{ad}(z),\text{ad}(y)])\\&=\text{tr}(\text{ad}(z)\text{ad}(x)\text{ad}(y))-\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))\\&=\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))-\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))\\&=0\end{align}$$using the cyclic property of the trace.
> 2. Let $\mathfrak{g}=\mathfrak{h}\oplus V$. If $x\in \mathfrak{h}$, then $\text{ad}(x):\mathfrak{g}\to \mathfrak{g}$ where $\text{ad}(x)(y)=[x,y]\in \mathfrak{h}$ as it is an ideal. Therefore, there exists a basis for which we can write: $$\text{ad}(x)=\begin{bmatrix}\text{ad}_{\mathfrak{h}}(x)&*\\0&0\end{bmatrix}$$Therefore, for $x,y\in \mathfrak{h}$, $$K_{\mathfrak{g}}(x,y)=\text{tr}_{\mathfrak{g}}(\text{ad}_{\mathfrak{g}}(x)\text{ad}_{\mathfrak{g}}(y))=\text{tr}_{\mathfrak{h}}(\text{ad}_{\mathfrak{h}}(x)\text{ad}_{\mathfrak{h}}(y))=K_{\mathfrak{h}}(x,y)$$
---
> [!lemma] Lemma 2
> For a connected [[Lie group]] $G$ with Lie algebra $\mathfrak{g}$, $$K_{\mathfrak{g}}(\text{Ad}(g)x,\text{Ad}(g)y)=K_{\mathfrak{g}}(x,y),\quad \forall g\in G, x,y\in \mathfrak{g}$$

> [!proof]-
> Let $z\in \mathfrak{g}$. Then, $$\text{ad}(\text{Ad}(g)x)z=[\text{Ad}(g)x,z]=\text{Ad}(g)[x,\text{Ad}(g^{-1})z]=\text{Ad}(g)\text{ad}(x)\text{Ad}(g^{-1})z$$Then, $$\begin{align}K_{\mathfrak{g}}(\text{Ad}(g)x,\text{Ad}(g)y)&=\text{tr}(\text{ad}(\text{Ad}(g)x)\text{ad}(\text{Ad}(g)y))\\&=\text{tr}(\text{Ad}(g)\text{ad}(x)\text{ad}(y)\text{Ad}(g^{-1}))\\&=\text{tr}(\text{Ad}(g^{-1})\text{Ad}(g)\text{ad}(x)\text{ad}(y))\\&=\text{tr}(\text{ad}(x)\text{ad}(y))\\&=K_{\mathfrak{g}}(x,y)\end{align}$$
---
> [!lemma] Theorem 3
> Let $V$ be a finite dimensional $\mathbb{C}$-vector space and $\mathfrak{g}<\mathfrak{gl}(V)$ a sub-algebra. If $\text{tr}(XY)=0$ for all $X,Y\in \mathfrak{g}$, then $\mathfrak{g}^{(1)}$ can be made strictly upper triangular.

> [!proof]+
> We have:
> 1. Let $X\in \mathfrak{gl}(V)$ and $X=X_{s}+X_{n}$ be the [[Jordan decomposition]]. Then, we show that $\text{ad}(X)=\text{ad}(X_{s})+\text{ad}(X_{n})$ is the Jordan decomposition of $\text{ad}(X)$. 
>    
>    As 
---
> [!lemma] Theorem 4 (Cartan's Criterion)
> For a $\mathbb{K}$-[[Lie algebra]] $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is solvable.
> 2. $K_{\mathfrak{g}}|_{\mathfrak{g}^{(1)}\times \mathfrak{g}^{(1)}}=0$

> [!proof]-
> We have that:
> 1. (1=>2): if $\mathfrak{g}$ is solvable, then by [[Solvable Lie Algebra|Lie's theorem]] $\text{ad}(\mathfrak{g})$ can be made upper triangular. However, then: $\text{ad}(\mathfrak{g}^{(1)})=(\text{ad}(\mathfrak{g}))^{(1)}$ is strictly upper triangular. Therefore, $$K_{\mathfrak{g}}(x,y)=\text{tr}(\text{ad}(x)\text{ad}(y))=0,\quad \forall x,y\in \mathfrak{g}^{(1)}$$
> 2. (2=>1): If $\text{tr}(\text{ad}(x)\text{ad}(y))=0$ for all $x,y\in \mathfrak{g}^{(1)}$, then by applying Theorem 3 to $\text{ad}(\mathfrak{g}^{(1)})$, $\text{ad}(\mathfrak{g}^{(2)})$ can be made strictly upper triangular. Therefore, by [[Nilpotent Lie Algebra|Corollary 6]], $\mathfrak{g}^{(2)}$ is nilpotent and solvable.
> 	
> 	Since $\mathfrak{g}^{(2)}$ is a solvable ideal in $\mathfrak{g}^{(1)}$, and $\mathfrak{g}^{(1)} / \mathfrak{g}^{(2)}$ is abelian hence solvable, $\mathfrak{g}^{(1)}$ is solvable by [[Solvable Lie Algebra|Lemma 3]]. Analogously, we can continue to prove that $\mathfrak{g}$ is solvable.
---
