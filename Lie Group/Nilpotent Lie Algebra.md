#Definition #LieGroups 

> [!definition]
> A [[Lie algebra]] $\mathfrak{g}$ is ***nilpotent*** if there exists a sequence of subspaces: $$\mathfrak{g}=\mathfrak{g}_{0}\supseteq \mathfrak{g}_{1}\supseteq\dots \supseteq\mathfrak{g}_{r}=(0)$$s.t. $[\mathfrak{g},\mathfrak{g}_{i-1}]:=\text{span}\{  [x,y]:x\in \mathfrak{g},y\in \mathfrak{g}_{i-1}\}\subseteq \mathfrak{g}_{i}$ for all $i\in [r]$. 
- **Related definition**: For any Lie algebra $\mathfrak{g}$, the ***central series*** of $\mathfrak{g}$ is a sequence $(C^i(\mathfrak{g}))_{i}$ where $C^0(\mathfrak{g})=\mathfrak{g}$ and $C^{i+1}(\mathfrak{g}):=[\mathfrak{g},C^i(\mathfrak{g})]$.
---
##### Properties
> [!lemma] Lemma 1
> For a nilpotent Lie algebra $\mathfrak{g}$, 
> 1. $\mathfrak{g}_{i}\unlhd \mathfrak{g}$ for all $i\in[r]$.
> 2. $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}\subseteq Z(\mathfrak{g} / \mathfrak{g}_{i})$, the [[Center of a group|center]] of $\mathfrak{g} / \mathfrak{g}_{i}$.
> 3. $C^{i-1}(\mathfrak{g}) / C^{i}(\mathfrak{g})\subseteq Z(\mathfrak{g} / C^i(\mathfrak{g}))$

> [!proof]-
> We have that:
> 1. $[\mathfrak{g},\mathfrak{g}_{i}]\subseteq \mathfrak{g}_{i+1}\subseteq \mathfrak{g}_{i}$. 
> 2. Consider $\pi:\mathfrak{g}\to \mathfrak{g} / \mathfrak{g}_{i}$ the canonical projection. Then, $$[\mathfrak{g / \mathfrak{g}_{i}},\mathfrak{g}_{i-1}/ \mathfrak{g}_{i}]=\pi([\mathfrak{g} , \mathfrak{g}_{i-1}])\subseteq \pi(\mathfrak{g}_{i})=(0)$$Therefore, $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}\subseteq Z(\mathfrak{g} / \mathfrak{g}_{i})$.
> 3. Analogous to 2.
---
> [!lemma] Proposition 2
> For a Lie algebra $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is nilpotent.
> 2. $C^r(\mathfrak{g})=(0)$ for some $r\geq 1$.
> 3. there exists $m\geq 1$ s.t. $$\text{ad}(x_{1})\dots \text{ad}(x_{m})y=0,\quad \forall x_{1},\dots,x_{m},y\in \mathfrak{g}$$

> [!proof]-
> We have:
> 1. (1=>2): We show that $\mathfrak{g}_{i}\supseteq C^i(\mathfrak{g})$. We have that $\mathfrak{g}_{1}\supseteq[\mathfrak{g},\mathfrak{g}]=C^1(\mathfrak{g})$. Then, $$\mathfrak{g}_{i}\supseteq[\mathfrak{g},\mathfrak{g}_{i-1}]\supseteq[\mathfrak{g},C^{i-1}(\mathfrak{g})]=C^i(\mathfrak{g})$$and $C^r(\mathfrak{g})=(0)$. 
> 2. (2=>1): By definition.
> 3. (2<=>3): We claim that: $$C^k(\mathfrak{g})=\text{span}\{ \text{ad}(x_{1})\dots \text{ad}(x_{k})y: x_{1},\dots,x_{k},y\in \mathfrak{g} \}$$We have that: $$C^1(\mathfrak{g})=[\mathfrak{g},\mathfrak{g}]=\text{span}\{ [x,y]: x,y\in \mathfrak{g} \}=\text{span}\{\text{ad}(x)y: x,y\in \mathfrak{g} \}$$Further, $$\begin{align}C^k(\mathfrak{g})=[\mathfrak{g},C^{k-1}(\mathfrak{g})]&=\text{span}\{ [x,y]: x\in \mathfrak{g},y\in C^{k-1}(\mathfrak{g}) \}\\&=\text{span}\{ \text{ad}(x_{1})\dots \text{ad}(x_{k})y: x_{1},\dots,x_{k},y\in \mathfrak{g} \}\end{align}$$This proves the statement.
- **Related definition**: The ***nilpotency length*** of a nilpotent Lie algebra is $\text{nil}(\mathfrak{g}):=\text{min}\{ r\geq 1 :C^r(\mathfrak{g})=(0)\}$
- **Corollary**: For a nilpotent Lie algebra $\mathfrak{g}$ with $r:=\text{nil}(\mathfrak{g})\geq 1$, $(0)\subsetneq C^{r-1}(\mathfrak{g})\subseteq Z(\mathfrak{g})$ by Lemma 1.3 and the center is non-trivial.
---
![[Solvable Lie Algebra#^5ae9c5]]
![[Solvable Lie Algebra#^dc3d92|p]]

---
> [!lemma] Lemma 3
> For $\mathfrak{h}\unlhd \mathfrak{g}$,
> 1. if $\mathfrak{g}$ is nilpotent, then $\mathfrak{h}$ and $\mathfrak{g / h}$ are nilpotent.
> 2. if $\mathfrak{g / h}$ is nilpotent and $\mathfrak{h}\subseteq Z(\mathfrak{g})$, then $\mathfrak{g}$ is nilpotent.

> [!proof]-
> We have:
> 1. Follows from $C^j(\mathfrak{h})\subseteq C^j(\mathfrak{g})$ and $C^j(\mathfrak{g / h})=\pi(C^j(\mathfrak{g}))$.
> 2. Let $r\geq 1$ with $\pi(C^r(\mathfrak{g}))=C^r(\mathfrak{g / h})=(0)$. Then, $$C^r(\mathfrak{g})\subseteq \mathfrak{h}\subseteq Z(\mathfrak{g})$$Therefore, $C^{r+1}(\mathfrak{g})=[\mathfrak{g},C^{r}(\mathfrak{g})]=(0)$.
- **Remark**: $\mathfrak{g / h}$ and $\mathfrak{h}$ being nilpotent are not enough to guarantee $\mathfrak{g}$'s nilpotency (cf. Example 2)
---
> [!lemma] Theorem 4
> For a Lie algebra $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is solvable. 
> 2. $[\mathfrak{g},\mathfrak{g}]$ is nilpotent.

> [!proof]+
> 
---
##### Examples
> [!h] Example 1
> Let $\mathfrak{g}$ be the space of all $n\times n$ upper triangular matrices with zero diagonal. Then, 
> 1. $C^1(\mathfrak{g})$ is the space of all $n\times n$ upper triangular matrices with zero diagonal and zero upper diagonal.
> 2. $C^{(n-1)}=(0)$.
---
> [!h] Example 2 (Counterexample Lemma 3)
> Consider the Lie algebras: $$\mathfrak{g}:=\left\{ \begin{bmatrix}*&*\\0&*\end{bmatrix} :*\in \mathbb{R}\right\}\subseteq \mathfrak{gl}(n,\mathbb{R}),\quad \mathfrak{h}:=\left\{ \begin{bmatrix}0&*\\0&0\end{bmatrix} :*\in \mathbb{R}\right\}$$Then, 
> 1. $\mathfrak{h}\unlhd \mathfrak{g}$.
> 2. $\mathfrak{g} / \mathfrak{h}$ and $\mathfrak{h}$ are abelian and nilpotent.
> 3. $\mathfrak{g}$ is not nilpotent.

> [!proof]-
> We have that:
> 1. it holds that:$$\left[\begin{bmatrix}a&b\\0&c\end{bmatrix},\begin{bmatrix}0&x\\0&0\end{bmatrix}\right]=\begin{bmatrix}0&xa\\0&0\end{bmatrix}+\begin{bmatrix}0&cx\\0&0\end{bmatrix}\in \mathfrak{h}$$
> 2. we have: $$\mathfrak{g} / \mathfrak{h}=\left\{ \begin{bmatrix}*&0\\0&*\end{bmatrix} :*\in \mathbb{R}\right\}$$and one easily checks that they are abelian. Then, $C^1(\mathfrak{g / h})=[\mathfrak{g / h},\mathfrak{g / h}]=(0)$.
> 3. Assume $\mathfrak{g}$ is nilpotent. As $\mathfrak{g}$ is non-zero, we have that the center is non-trivial. However, we have: $$\begin{bmatrix}a&b\\0&c\end{bmatrix}\begin{bmatrix}x&y\\0&z\end{bmatrix}=\begin{bmatrix}ax&ay+bz\\0&cz\end{bmatrix},\quad\begin{bmatrix}x&y\\0&z\end{bmatrix}\begin{bmatrix}a&b\\0&c\end{bmatrix}=\begin{bmatrix}ax&bx+cy\\0&cz\end{bmatrix}$$and we have that $ay+bz=bx+cy$ for all $a,b,c\in \mathbb{R}$. Therefore, $Z(\mathfrak{g})=(0)$, which is a contradiction.
---
