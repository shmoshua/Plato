#Definition #RepresentationTheory 

> [!definition]
> For a field $K$ and $n\geq 0$, the ***special linear Lie algebra*** is $$\mathfrak{sl}_{n}(K):=\{ A\in \text{M}_{n,n}(K):\text{tr}(A)=0 \}$$with $[A,B]=AB-BA$. 
---
##### Examples
> [!h] Example 1 
> The basis of $\mathfrak{sl}_{2}(\mathbb{C})$ is given as: $$e:=\begin{bmatrix}0&1\\0&0\end{bmatrix},\quad f:=\begin{bmatrix}0&0\\1&0\end{bmatrix},\quad h:=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$$where $[h,e]=2e$, $[h,f]=-2f$ and $[e,f]=h$. Therefore, a representation of $\mathfrak{sl}_{2}(\mathbb{C})$ is a vector space $V$ with three operators $E,F,H$ s.t. 
> - $HE-EH=2E$
> - $HF-FH=-2F$
> - $EF-FE=H$
> 
> Let $V$ be a finite dimensional representation of $\mathfrak{sl}_{2}(\mathbb{C})$.
> 1. Let $\lambda$ be the eigenvalue of $H$ with the greatest real part. Then, $E|_{V_{\lambda}}=0$.

> [!proof]+
> Let $v\in V_{\lambda}$. Then, $Hv=\lambda v$ and $$HE(v)=(2+\lambda)E(v)$$