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

> [!proof]-
> We have:
> 1. **Claim 1:** 
>    
>    Let $X\in \mathfrak{gl}(V)$ and $X=X_{s}+X_{n}$ be the [[Jordan decomposition]]. Then, we show that $\text{ad}(X)=\text{ad}(X_{s})+\text{ad}(X_{n})$ is the Jordan decomposition of $\text{ad}(X)$. 
>    
>    We already know that $\text{ad}(X_{n})$ is nilpotent by [[Nilpotent Lie Algebra|Proof of Engel Theorem Claim 1]]. In addition, $$[\text{ad}(X_{s}),\text{ad}(X_{n})]=\text{ad}([X_{s},X_{n}])=0$$Let $e_{1},\dots,e_{n}$ be a basis of $V$ consisting of eigenvectors of $X_{s}$ with corresponding eigenvalues $\lambda_{1},\dots,\lambda_{n}$. Then, $[X_{s},E_{ij}]=(\lambda_{i}-\lambda_{j})E_{j}$. Therefore, $\text{ad}(X_{s})$ is diagonalizable.
>    
>   
>   By [[Nilpotent Lie Algebra|Engel's Theorem]], it suffices to show that every $X\in\mathfrak{g}^{(1)}$ is nilpotent. By the [[Jordan decomposition]] $X=X_{s}+X_{n}$, it is enough to show that $X_{s}=0$. We will show that for $X_{s}=\text{diag}(\lambda_{1},\dots,\lambda_{n})$ and $\text{tr}(X_{s}X_{s}^{*})=\sum_{i=1}^{n}\left| \lambda_{i} \right|^{2}=0$, which should prove that $X_{s}=0$. 
>   
>   We have: $$\text{tr}(X_{s}X_{s}^{*})=\text{tr}((X-X_{n})X_{s}^{*})=\text{tr}(XX^{*}_{s})-\text{tr}(X_{n}X^{*}_{s})$$Consider the following polynomial: $$p(x):=\sum_{j=1}^{n}\overline{\lambda_{j}}\prod_{i\neq j}^{}\frac{x-\lambda_{i}}{\lambda_{j}-\lambda_{i}}$$Then, $p(\lambda_{i})=\overline{\lambda}_{i}$ and $p(X_{s})=X_{s}^{*}$. Then, as $X\in \mathfrak{g}^{(1)}$, $X=\sum_{i=1}^{k}[A_{i},B_{i}]$ for $A_{i},B_{i}\in \mathfrak{g}$. Then, $$\text{tr}(XX^{*}_{s})=\text{tr}\left( \sum_{i=1}^{k}A_{i}B_{i}X^{*}_{s}-B_{i}A_{i}X^{*}_{s} \right)=\sum_{i=1}^{k}\text{tr}([B_{i},X^{*}_{s}]A_{i})=-\sum_{i=1}^{k}\text{tr}((\text{ad}(X^{*}_{s})B_{i})A_{i}) $$As $X_{s}^{*}=p(X_{s})$ and by Claim 1, $\text{ad}(p(X_{s}))=p'(\text{ad}(X_{s}))$. Therefore, $\text{ad}(X_{s}^{*})\mathfrak{g}\subseteq \mathfrak{g}$. Hence, $\text{ad}(X^{*}_{s})B_{i}$ and $A_{i}$ are both in $\mathfrak{g}$ and $\text{tr}(XX^{*}_{s})=0$.
>   
>   Further, as $[X_{s},X_{n}]=0$, $[X_{s}^{*},X_{n}]=0$ as $X^{*}_{s}=p(X_{s})$. Therefore, $X_{n}X^{*}_{s}$ is nilpotent and has trace 0. This proves the theorem.
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
##### Examples
> [!h] Example 1
> We have that:
> 1. $K_{\mathfrak{sl}(2,\mathbb{R})}(X,Y)=4\text{tr}(XY)$.

> [!proof]+
> We have that: $$X_{1}:=\begin{bmatrix}1&0\\0&-1\end{bmatrix},X_{2}:=\begin{bmatrix}0&1\\0&0\end{bmatrix},X_{3}:=\begin{bmatrix}0&0\\1&0\end{bmatrix}$$form a basis of $\mathfrak{sl}(2,\mathbb{R})$. Then, 
> 1. $\text{ad}\left( \begin{bmatrix}a&b\\c&-a\end{bmatrix} \right) X_{1}=\begin{bmatrix}0&-2b\\2c&0\end{bmatrix}$
> 2. $\text{ad}\left( \begin{bmatrix}a&b\\c&-a\end{bmatrix} \right) X_{2}=\begin{bmatrix}-c&2a\\0&c\end{bmatrix}$
> 3. $\text{ad}\left( \begin{bmatrix}a&b\\c&-a\end{bmatrix} \right) X_{2}=\begin{bmatrix}-c&2a\\0&c\end{bmatrix}$

> 4. $\text{ad}(X_{1})\begin{bmatrix}a&b\\c&-a\end{bmatrix}=\begin{bmatrix}0&2b\\-2c&0\end{bmatrix}$
> 5. $\text{ad}(X_{2})\begin{bmatrix}a&b\\c&-a\end{bmatrix}=\begin{bmatrix}c&-2a\\0&-c\end{bmatrix}$
> 6. $\text{ad}(X_{3})\begin{bmatrix}a&b\\c&-a\end{bmatrix}=\begin{bmatrix}-b&0\\2a&b\end{bmatrix}$
> 
> $$\begin{align}K_{\mathfrak{sl}(2,\mathbb{R})}\left( \sum_{i=1}^{3}a_{i}X_{i},\sum_{i=1}^{3}b_{i}X_{i}\right)&=\text{tr}\left( \left( \sum_{i=1}^{3}a_{i}\text{ad}(X_{i}) \right)\left( \sum_{i=1}^{3}b_{i}\text{ad}(X_{i}) \right)  \right) \end{align}$$