#Definition #DifferentialGeometry 

> [!definition]
> Let $1\leq k\leq n$ and the ***Grassmannian*** $G(k,n)$ is the set of all subspaces of $\mathbb{R}^n$ of dimension $k$. 
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $G(k,n)$ is a topological space.
> 2. 

> [!proof]+
> We have:
> 1. We first define the topology on $G(k,n)$. Let: $$F(k,n):=\{ (v_{1},\dots,v_{k})\in (\mathbb{R}^n)^k:v_{1},\dots,v_{k}\text{ are linearly independent} \}$$Then, there exists a surjective map: $$\begin{array}{cccc} {\pi:}&{F(k,n)}&\to&{G(k,n)}\\&{(v_{1},\dots,v_{k})} &\mapsto & {\mathbb{R} v_{1}\oplus \dots \oplus \mathbb{R}v_{k}} \end{array}{}$$For $k$ vectors in $\mathbb{R}^n$, we can define a map: $$\begin{array}{cccc} {M:}&{(\mathbb{R}^n)^k}&\to&{\text{M}_{k,n}(\mathbb{R})}\\&{(w_{1},\dots,w_{k})} &\mapsto & {\begin{bmatrix}w_{1}^\top\\ \vdots\\w_{k}^\top\end{bmatrix}} \end{array}{}$$Then, $w_{1},\dots,w_{k}$ are linearly independent if and only if $\text{rank }M(w_{1},\dots,w_{k})=k$. Therefore, $F(k,n)$ is identified with $\{ A\in \text{M}_{k,n}(\mathbb{R}):\text{rank }A=k \}$ which is open as it is equal to: $$\left\{ A\in \text{M}_{k,n}(\mathbb{R})\left|\exists 1\leq j_{1}<\dots<j_{k}\leq n:\det \begin{bmatrix}A_{1j_{1}}&\dots&A_{1j_{k}}\\ \vdots&&\vdots\\A_{kj_{1}}&\dots&A_{kj_{k}}\end{bmatrix}\neq 0\right. \right\}$$which is a union of open subsets over different multi-indices.
>    
>    Now, $\pi(v_{1},\dots,v_{k})=\pi(v'_{1},\dots,v'_{k})$ if and only if there exists $B\in \text{GL}(k,\mathbb{R})$ s.t. $$M(v_{1},\dots,v_{k})=BM(v_{1}',\dots,v)$$