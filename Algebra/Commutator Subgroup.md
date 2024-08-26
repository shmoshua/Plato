#Definition #Algebra #LieGroups 

> [!definition]
> Let $G$ be a [[group]]. For $g,h\in G$, the ***commutator*** is defined as $[g,h]=g^{-1}h^{-1}gh\in G$. Then, the ***commutator subgroup*** of $G$ is defined as: $$[G,G]:=\left\langle [g,h]:g,h\in G \right\rangle\leq G$$
- ***Related definition***: A ***derived series*** of a group $G$ is $(G^{(i)})_{i}$ where $G^{(0)}=G$ and $G^{(i+1)}=[G^{(i)},G^{(i)}]$.
---
##### Properties
> [!lemma] Lemma 1
> We have:
> 1. Let $\pi:G\to H$ be a [[group homomorphism]]. Then, $\pi(G^{(i)})=\pi(G)^{(i)}$.
> 2. For $N\unlhd G$, $G / N$ is abelian if and only if $[G,G]\leq N$.
> 3. For $H\unlhd G$, $[H,H]\unlhd G$

> [!proof]-
> We have:
> 1. Follows from $\pi([g,h])=[\pi(g),\pi(h)]$. Therefore, $\pi(G^{(1)})=\pi(G)^{(1)}$ and the statement follows.
> 2. Let $N\unlhd G$ and $\pi:G\to G / N$ the canonical projection. If it is abelian, then: $$\pi([G,G])=[\pi(G),\pi(G)]=[G / N,G / N]=\{ N \}$$Therefore, $[G,G]\leq N$. Conversely, if $[G,G]\leq N$, then: $[G /N, G / N]=\{ N \}$ and $G / N$ is abelian.
> 4. For $h_{1},h_{2}\in H$ and $x\in G$, $$\begin{align}x[h_{1},h_{2}]x ^{-1}&=xh_{1}^{-1}h_{2}^{-1}h_{1}h_{2}x ^{-1}\\&=(xh^{-1}_{1}x ^{-1})(x h_{2}^{-1}x ^{-1})(xh_{1}x ^{-1})(xh_{2} x ^{-1})\\&=[xh_{1}x ^{-1},xh_{2}x ^{-1}]\\&\in [H,H]\end{align}$$
- **Corollary**: For all $i\geq 1$, $G^{(i+1)}\unlhd G^{(i)}$.
---
> [!lemma] Lemma 2
> Let $G$ be a topological group. If $G$ is connected, then 
> 1. $[G,G]$ is connected and
> 2. $G^{(i)}$ is connected for all $i\geq 1$.

> [!proof]-
> As $G\times G\to G,(g,h)\mapsto[g,h]$ is a continuous map, $V:=\{ [g,h]:g\in G,h\in G \}$ is connected. Then, $V^n$ is also connected and as $e\in V^n$ for all $n\geq 1$, $$[G,G]=\bigcup_{n\geq 1}^{}V^n$$is connected.
---
##### Examples
> [!h] Example 1
> Let: $$G:=\{ kA\in \text{GL}(n,\mathbb{R}): k>0, A\in \text{UT}(n,\mathbb{R})\}$$Then,
> 1. $G^{(1)}=\text{UT}(n,\mathbb{R})$.
> 2. $G^{(2)}=\{ A\in \text{UT}(n,\mathbb{R}) :A_{i,j+1}=0\}$.
> 3. $G^{(k)}=\{ A\in \text{UT}(n,\mathbb{R}) :A_{i,j+\ell}=0,1\leq\ell< k\}$.
> 4. $G^{(n)}=\{ \text{id} \}$
> 5. $G$ is [[Solvable Group|solvable]]. 

> [!proof]-
> We have:
> 1. We have: $[kA,sB]=k^{-1}s ^{-1}ks A^{-1}B^{-1}AB=A^{-1}B^{-1}AB\in \text{UT}(n,\mathbb{R})$. $
---
> [!h] Example 2
> Consider: $$G:=\left\{ \begin{bmatrix}a&b\\0&c\end{bmatrix} :a,c\neq 0\right\}$$
> Then, 
> 1. $G^{(1)}=\left\{ \begin{bmatrix}1&*\\0&1\end{bmatrix} :*\in \mathbb{R}\right\}$
> 2. $G^{(2)}=\{ \text{id} \}$
> 3. $G$ is solvable.
---
> [!h] Example 3 (Heisenberg Lie Group)
> Consider: $$H:=\left\{ \begin{bmatrix}1&a&b\\0&1&c\\0&0&1\end{bmatrix} :a,b,c\in \mathbb{R}\right\}$$
> Then, 
> 1. $H^{(1)}=\left\{ \begin{bmatrix}1&0&*\\0&1&0\\0&0&1\end{bmatrix} :*\in \mathbb{R}\right\}$
> 2. $H^{(2)}=\{ \text{id} \}$
> 3. $H$ is solvable.
---
> [!h] Example 4 (Special Linear Group)
> For $\text{SL}(2,\mathbb{R})$ we have:
> 1. $$\begin{bmatrix}a^{-1}&0\\0&a\end{bmatrix}^{-1}\begin{bmatrix}1&-1\\0&1\end{bmatrix}^{-1}\begin{bmatrix}a^{-1}&0\\0&a\end{bmatrix}\begin{bmatrix}1&-1\\0&1\end{bmatrix}=\begin{bmatrix}a&a\\0&a^{-1}\end{bmatrix}\begin{bmatrix}a^{-1}&-a^{-1}\\0&a\end{bmatrix}=\begin{bmatrix}1&a^{2}-1\\0&1\end{bmatrix}$$
> 2. $$\begin{bmatrix}a&0\\0&a^{-1}\end{bmatrix}^{-1}\begin{bmatrix}1&0\\-1&1\end{bmatrix}^{-1}\begin{bmatrix}a&0\\0&a^{-1}\end{bmatrix}\begin{bmatrix}1&0\\-1&1\end{bmatrix}=\begin{bmatrix}a^{-1}&0\\a&a\end{bmatrix}\begin{bmatrix}a&0\\-a^{-1}&a^{-1}\end{bmatrix}=\begin{bmatrix}1&0\\a^{2}-1&1\end{bmatrix}$$
> 3. $$\begin{bmatrix}a^{-1}&0\\0&a\end{bmatrix}^{-1}\begin{bmatrix}0&1\\-1&0\end{bmatrix}^{-1}\begin{bmatrix}a^{-1}&0\\0&a\end{bmatrix}\begin{bmatrix}0&1\\-1&0\end{bmatrix}=\begin{bmatrix}0&-a\\a^{-1}&0\end{bmatrix}\begin{bmatrix}0&a^{-1}\\-a&0\end{bmatrix}=\begin{bmatrix}a^{2}&0\\0&a^{-2}\end{bmatrix}$$
> 
> As these three elements generate a neighborhood of $\text{id}$ and $\text{SL}(2,\mathbb{R})$ is connected, we have that: $$[\text{SL}(2,\mathbb{R}),\text{SL}(2,\mathbb{R})]=\text{SL}(2,\mathbb{R})$$ and $\text{SL}(2,\mathbb{R})$ is not solvable.
---

