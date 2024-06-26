#Definition #RepresentationTheory 

> [!definition]
> Let $\mathfrak{g}$ be a [[Lie algebra]] with basis $x_{i}$ and $[,]$ defined as $[x_{i},x_{j}]=\sum_{k}^{}c_{ij}^kx_{k}$. The ***universal enveloping algebra*** $\mathcal{U}(\mathfrak{g})$ is the [[associative algebra]] generated by $\{ x_{i} \}$ with the defining relation: $$x_{i}x_{j}-x_{j}x_{i}=\sum_{k}^{}c_{ij}^kx_{k}$$
---
##### Examples
> [!h] Example 1
> Consider $\mathfrak{sl}_{2}(K)$ with the basis$$e:=\begin{bmatrix}0&1\\0&0\end{bmatrix},\quad f:=\begin{bmatrix}0&0\\1&0\end{bmatrix},\quad h:=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$$where $[h,e]=2e$, $[h,f]=-2f$ and $[e,f]=h$. Then, $\mathcal{U}(\mathfrak{sl}_{2}(K))$ is the algebra generated by $e,f,h$ with the relations: $$he-ef=2e,\quad hf-fh=-2f,\quad ef-fe=h$$
---
> [!h] Example 2
> Consider $\mathfrak{H}$, the [[Lie Algebra|Heisenberg Lie algebra]] defined as: $$\mathfrak{H}:=\left\{ A\in \text{M}_{3,3}(\mathbb{C}):A=\begin{bmatrix}0&*&*\\0&0&*\\0&0&0\end{bmatrix} \right\}$$with basis: $$x:=\begin{bmatrix}0&0&0\\0&0&1\\0&0&0\end{bmatrix},\quad y:=\begin{bmatrix}0&1&0\\0&0&0\\0&0&0\end{bmatrix},\quad c:=\begin{bmatrix}0&0&1\\0&0&0\\0&0&0\end{bmatrix}$$with $[y,x]=c$, $[y,c]=[x,c]=0$. Then, $\mathcal{U}(\mathfrak{H})$ is the algebra generated by $x,y,c$ and relations: $$yx-xy=c,\quad yc-cy=0,\quad xc-cx=0$$Then, the [[Weyl algebra]] is $\mathcal{U}(\mathfrak{H}) / (c-1)$.
---