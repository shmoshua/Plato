#Series #Analysis 

> [!definition] Problem 1
> Inner product spaces: 
> 1. Consider the Frobenius product on $\text{M}_{n,n}(\mathbb{C})$: $$\braket{ A , B } =\text{Tr}(AB^H)=\sum_{i=1}^{n}\sum_{j=1}^{n}a_{ij}\overline{b_{ij}}$$Show that $(V,\braket{ \cdot , \cdot })$ is an inner product space.
> 2. Consider $n$ inner product spaces $(V_{i},\braket{ \cdot , \cdot }_{i})_{i}$. Is $(V,\braket{ \cdot , \cdot })$ where $V=V_{1}\times\dots \times V_{n}$ and: $$\braket{ (v_{1},\dots,v_{n}) , (w_{1},\dots,w_{n}) } :=\sum_{i=1}^{n}\braket{ v_{i} , w_{i} } _{i}$$an inner product space?
> 3. Let $W:=\text{M}_{n,n}(L^2(\mathbb{R},\mathbb{C}))$ be the space of $n\times n$ matrices whose entries are square integrable functions from $\mathbb{R}$ to $\mathbb{C}$. Which product would make $W$ an inner product space?

We have that:
1. For any $A,B,C\in \text{M}_{n,n}(\mathbb{C})$ and $\alpha\in \mathbb{C}$: $$\begin{align}\braket{ \alpha A+B , C } =\sum_{i=1}^{n}\sum_{j=1}^{n}(\alpha a_{ij}+b_{ij})\overline{c_{ij}}=\alpha\sum_{i,j=1}^{n}a_{ij}\overline{c_{ij}}+\sum_{i,j=1}^{n}b_{ij}\overline{c_{ij}}=\alpha\braket{  A, C }+\braket{ B , C }  \end{align}$$For $A,B\in \text{M}_{n,n}(\mathbb{C})$, $$\braket{ A , B } =\sum_{i,j=1}^{n}a_{ij}\overline{b_{ij}}=\overline{\sum_{i,j=1}^{n}\overline{a_{ij}}b_{ij}}=\overline{\braket{ B , A } }$$Lastly, We have that $\braket{ A , A }=\sum_{i,j=1}^{n}a_{ij}\overline{a_{ij}}=\sum_{i,j=1}^{n}\left| a_{ij} \right|^{2}>0$ if $A\neq 0$. Therefore, $\braket{ \cdot , \cdot }$ is an inner product on $\text{M}_{n,n}(\mathbb{C})$.
2. Linearity in the first argument and conjugate symmetry can be easily seen as addition is continuous under these operations. For positive definiteness, if $(v_{1},\dots,v_{n})\neq 0$, $$\braket{ (v_{1},\dots,v_{n}) , (v_{1},\dots,v_{n}) } =\sum_{i=1}^{n}\braket{ v_{i} , v_{i} } _{i}>0$$
3. 
---

> [!definition] Problem 3
> Determine whether the following sets $X$ are well-defined, open, close, subspaces and convex.
> 1. In the normed space $(C([0,1]),\|\cdot\|_{\infty})$ the subset $X$ of nowhere vanishing functions.
> 2. In the normed space $(C([0,1]),\|\cdot \|_{2})$, the subset $X$ of nowhere vanishing functions.
> 3. In the normed space $(L^2([0,1]),\|\cdot\|_{2})$, the subset $X=\left\{  f:\int_{0}^{1} f \, dx =1  \right\}$.
> 4. In the normed space $(L^2(\mathbb{R}),\|\cdot\|_{2})$, the subset $\{ f:f(x)=f(-x)\text{ for a.e.}x\in \mathbb{R} \}$.
> 5. In the normed space $(L^2([0,1]),\|\cdot\|_{2})$, the subset $X=\left\{  f:f\geq 0\land \int_{0}^{1} \frac{2f}{1+f} \, dx \geq 1 \right\}$.

We have:
**Bonus**: Well-defined, closed, convex but not linear subspace:
1. **$X$ is well-defined** assuming $X\subseteq L^2([0,1])$ otherwise we can have $\frac{1}{2\sqrt{ x }}$ as counterexample.
2. **$X$ is closed**: Let $f_{n}\to f$ in $L^2$ where $(f_{n})_{n}\subseteq X$. Then, for $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. $\|f_{n}-f\|_{1}\leq \left\| f_{n}-f \right\|_{2}\mu([0,1])=\left\| f_{n}-f \right\|_{2}<\varepsilon$ by Hölder for all $n\geq N$. Therefore, $$\int_{0}^{1} f \, dx = \int_{0}^{1} f_{n}-f \, dx +\int_{0}^{\infty} f_{n} \, dx <\varepsilon+1$$By taking $\varepsilon\to {0}$, we get that $f\in X$. 
3. **$X$ is convex**: for $f,g\in X$ with $t\in[0,1]$, convexity follows from the linearity of integrals.
4. **$X$ is not a linear subspace**: for $f\in X$, $2f$ has integral $2$ and therefore not in $X$.
---