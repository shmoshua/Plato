#Definition #DifferentialGeometry 

> [!definition]
> Let $1\leq k\leq n$ and the ***Grassmannian*** $G(k,n)$ is the set of all subspaces of $\mathbb{R}^n$ of dimension $k$. 
---
##### Properties
> [!lemma] Proposition 1
> $G(k,n)$ is a smooth manifold.

^af4191


> [!proof]-
> We have:
> 1. We first define the topology on $G(k,n)$. Let: $$F(k,n):=\{ (v_{1},\dots,v_{k})\in (\mathbb{R}^n)^k:v_{1},\dots,v_{k}\text{ are linearly independent} \}$$Then, there exists a surjective map: $$\begin{array}{cccc} {\pi:}&{F(k,n)}&\to&{G(k,n)}\\&{(v_{1},\dots,v_{k})} &\mapsto & {\mathbb{R} v_{1}\oplus \dots \oplus \mathbb{R}v_{k}} \end{array}{}$$For $k$ vectors in $\mathbb{R}^n$, we can define a map: $$\begin{array}{cccc} {M:}&{(\mathbb{R}^n)^k}&\to&{\text{M}_{k,n}(\mathbb{R})}\\&{(w_{1},\dots,w_{k})} &\mapsto & {\begin{bmatrix}w_{1}^\top\\ \vdots\\w_{k}^\top\end{bmatrix}} \end{array}{}$$Then, $w_{1},\dots,w_{k}$ are linearly independent if and only if $\text{rank }M(w_{1},\dots,w_{k})=k$. Therefore, $F(k,n)$ is identified with $\{ A\in \text{M}_{k,n}(\mathbb{R}):\text{rank }A=k \}$ which is open as it is equal to: $$\left\{ A\in \text{M}_{k,n}(\mathbb{R})\left|\exists 1\leq j_{1}<\dots<j_{k}\leq n:\det \begin{bmatrix}A_{1j_{1}}&\dots&A_{1j_{k}}\\ \vdots&&\vdots\\A_{kj_{1}}&\dots&A_{kj_{k}}\end{bmatrix}\neq 0\right. \right\}$$which is a union of open subsets over different multi-indices.
>    
>    Now, $\pi(v_{1},\dots,v_{k})=\pi(v'_{1},\dots,v'_{k})$ if and only if there exists $B\in \text{GL}(k,\mathbb{R})$ s.t. $$M(v_{1},\dots,v_{k})=BM(v_{1}',\dots,v_{k}')$$Therefore, we can define an open equivalence relation: $$(v_{1},\dots,v_{k})\sim(v_{1}',\dots,v'_{k})\iff \exists B\in \text{GL}(k,\mathbb{R}):M(v_{1},\dots,v_{k})=BM(v_{1}',\dots,v_{k}')$$
> 
> 2. Given $B\in \text{GL}(k,\mathbb{R})$, $L_{B}:\text{M}_{k,n}(\mathbb{R})\to \text{M}_{k,n}(\mathbb{R}),A\mapsto BA$ is a homeomorphism with inverse $L_{B^{-1}}$. Therefore, for any open subset $\Omega \subseteq F(k,n)$: $$\pi ^{-1}(\pi(\Omega))=\bigcup_{B\in \text{GL}(k,\mathbb{R})}^{}L_{B}(M(\Omega))$$Further, the graph of $\sim$ is a closed subset of $F(k,n)\times F(k,n)$. Therefore, $G(k,n)$ is equipped with a second-countable Hausdorff topology.
> 3. We now define charts on $G(k,n)$ which gives it a smooth structure. For any multi-index $J=(j_{1},..,j_{k})$ where $1\leq j_{1}<\dots<j_{k}\leq n$, set: $$\tilde{U}_{J}:=\left\{ \begin{bmatrix}w_{1}^\top\\ \vdots\\w^\top_{k}\end{bmatrix}\in \text{M}_{k,n}(\mathbb{R})\left|\begin{bmatrix}w_{1j_{1}}&\dots&w_{1j_{k}}\\ \vdots&&\vdots\\w_{kj_{1}}&\dots&w_{kj_{k}}\end{bmatrix}=I_{k}\in \text{M}_{k,k}(\mathbb{R})\right. \right\}$$Then, $\pi|_{\tilde{U}_{j}}:\tilde{U}_{j}\to G(k,n)$ is injective and: $$\pi ^{-1}(\pi(\tilde{U}_{j}))=\tilde{U}_{J}:=\left\{ \begin{bmatrix}w_{1}^\top\\ \vdots\\w^\top_{k}\end{bmatrix}\in \text{M}_{k,n}(\mathbb{R})\left|\det\begin{bmatrix}w_{1j_{1}}&\dots&w_{1j_{k}}\\ \vdots&&\vdots\\w_{kj_{1}}&\dots&w_{kj_{k}}\end{bmatrix}\neq 0\right. \right\}$$Therefore, $\pi(\tilde{U}_{j})\subseteq G(k,n)$ is open and $\bigcup_{J}^{}\pi(\tilde{U}_{j})=G(k,n)$. By defining the projection maps $\text{pr}_{J}:\tilde{U}_{J}\to \text{M}_{k,n-k}(\mathbb{R})$, $\{ (\pi(\tilde{U}_{j}),\text{pr}_{J}\circ(\pi|_{\tilde{U}_{j}})^{-1}) \}_{J}$ is a smooth atlas on $G(k,n)$.

^a87389

---