#Series #Analysis 

> [!definition] Problem 1
> Inner product spaces: 
> 1. Consider the Frobenius product on $\text{M}_{n,n}(\mathbb{C})$: $$\braket{ A , B } =\text{Tr}(AB^H)=\sum_{i=1}^{n}\sum_{j=1}^{n}a_{ij}\overline{b_{ij}}$$Show that $(V,\braket{ \cdot , \cdot })$ is an inner product space.
> 2. Consider $n$ inner product spaces $(V_{i},\braket{ \cdot , \cdot }_{i})_{i}$. Is $(V,\braket{ \cdot , \cdot })$ where $V=V_{1}\times\dots \times V_{n}$ and: $$\braket{ (v_{1},\dots,v_{n}) , (w_{1},\dots,w_{n}) } :=\sum_{i=1}^{n}\braket{ v_{i} , w_{i} } _{i}$$an inner product space?
> 3. Let $W:=\text{M}_{n,n}(L^2(\mathbb{R},\mathbb{C}))$ be the space of $n\times n$ matrices whose entries are square integrable functions from $\mathbb{R}$ to $\mathbb{C}$. Which product would make $W$ an inner product space?

We have that:
1. For any $A,B,C\in \text{M}_{n,n}(\mathbb{C})$ and $\alpha\in \mathbb{C}$: $$\begin{align}\braket{ \alpha A+B , C } =\sum_{i=1}^{n}\sum_{j=1}^{n}(\alpha a_{ij}+b_{ij})\overline{c_{ij}}=\alpha\sum_{i,j=1}^{n}a_{ij}\overline{c_{ij}}+\sum_{i,j=1}^{n}b_{ij}\overline{c_{ij}}=\alpha\braket{  A, C }+\braket{ B , C }  \end{align}$$For $A,B\in \text{M}_{n,n}(\mathbb{C})$, $$\braket{ A , B } =\sum_{i,j=1}^{n}a_{ij}\overline{b_{ij}}=\overline{\sum_{i,j=1}^{n}\overline{a_{ij}}b_{ij}}=\overline{\braket{ B , A } }$$Lastly, We have that $\braket{ A , A }=\sum_{i,j=1}^{n}a_{ij}\overline{a_{ij}}=\sum_{i,j=1}^{n}\left| a_{ij} \right|^{2}>0$ if $A\neq 0$. Therefore, $\braket{ \cdot , \cdot }$ is an inner product on $\text{M}_{n,n}(\mathbb{C})$.
2. Linearity in the first argument and conjugate symmetry can be easily seen as addition is continuous under these operations. For positive definiteness, if $(v_{1},\dots,v_{n})\neq 0$, $$\braket{ (v_{1},\dots,v_{n}) , (v_{1},\dots,v_{n}) } =\sum_{i=1}^{n}\braket{ v_{i} , v_{i} } _{i}>0$$
3. We can define: $$\braket{ F , G } =\sum_{i,j=1}^{n}\int_{\mathbb{R}}^{} f_{ij}(x)\overline{g_{ij}(x)} \, dx  $$One can easily check that analogously to part 1, this forms an inner product space on $W$.
---
> [!def] Problem 2
> An inner product space $(V,\braket{ \cdot , \cdot })$ is also a metric space under the norm $\|\cdot\|:=\sqrt{ \braket{ \cdot , \cdot } }$, hence it has a natural topology. Prove that $\braket{ \cdot , \cdot }$ and the vector space operations $(\cdot,+)$ are continuous from $V\times V$ (resp. $V\times \mathbb{C}$, $V\times V$) endowed with the natural product topology, to $\mathbb{C}$ (resp. $V$ ,$V$). 

We have:
1. **Showing the continuity of $\braket{ \cdot , \cdot }$**:
   Let $(v_{n},w_{n})_{n}\subseteq V\times V$ s.t. $(v_{n},w_{n})\to(v,w)$. Then, for any $(a,b)\in V\times V$
   $$\|a\|\leq\|a\|+\|b\|=\|(a,b)\|$$Therefore, $v_{n}\to v$ and $w_{n}\to w$ as well. Therefore, $$\begin{align}\left| \braket{ v_{n} , w_{n} } -\braket{ v , w }  \right|&=\left| \braket{ v_{n} , w_{n} } -\braket{ v_{n} , w } +\braket{ v_{n} , w }  -\braket{ v , w } \right| \\&\leq\left|\braket{ v_{n} , w_{n}-w }   \right|+\left|\braket{ v_{n}-v , w }\right|\\&\leq \left\| v_{n} \right\| \left\| w_{n}-w \right\| +\left\| v_{n}-v \right\| \|w\|  \end{align} $$As $\sup_{n\geq 1}\left\| v_{n} \right\|<+\infty$, $$\limsup_{ n \to \infty } \left| \braket{ v_{n} , w_{n} } -\braket{ v , w }  \right|\leq \sup_{n\geq 1}\left\| v_{n} \right\|\limsup_{ n \to \infty } \left\| w_{n}-w \right\| +\limsup_{ n \to \infty } \left\| v_{n}-v \right\| \|w\|=0$$
2. **Showing the continuity of addition**:
   Let $(v_{n},w_{n})_{n}\subseteq V\times V$ s.t. $(v_{n},w_{n})\to(v,w)$. Similarly as above, $v_{n}\to v$ and $w_{n}\to w$ as well. Therefore, $$\limsup_{ n \to \infty } \|v+w-v_{n}-w_{n}\|\leq\limsup_{ n \to \infty }\|v-v_{n}\|+\limsup_{ n \to \infty }\left\| w-w_{n} \right\| =0 $$
3. **Showing the continuity of scalar multiplication**:
	Let $(v_{n},\alpha_{n})\subseteq V\times \mathbb{C}$ s.t. $(v_{n},\alpha_{n})\to(v,\alpha)$. Similarly to above, $v_{n}\to v$ and $\alpha_{n}\to\alpha$ and: $$\|\alpha_{n} v_{n}-\alpha v\|=\|\alpha_{n}v_{n}-\alpha_{n}v+\alpha_{n}v-\alpha v\|\leq \left| \alpha_{n} \right| \left\| v_{n}-v \right\| +\left| \alpha_{n}-\alpha \right| \|v\|$$Therefore, the scalar multiplication is continuous.
---

> [!definition] Problem 3
> Determine whether the following sets $X$ are well-defined, open, close, subspaces and convex.
> 1. In the normed space $(C([0,1]),\|\cdot\|_{\infty})$ the subset $X$ of nowhere vanishing functions.
> 2. In the normed space $(C([0,1]),\|\cdot \|_{2})$, the subset $X$ of nowhere vanishing functions.
> 3. In the normed space $(L^2(0,1),\|\cdot\|_{2})$, the subset $X=\left\{  f:\int_{0}^{1} f \, dx =1  \right\}$.
> 4. In the normed space $(L^2(\mathbb{R}),\|\cdot\|_{2})$, the subset $\{ f:f(x)=f(-x)\text{ for a.e.}x\in \mathbb{R} \}$.
> 5. In the normed space $(L^2([0,1]),\|\cdot\|_{2})$, the subset $X=\left\{  f:f\geq 0\land \int_{0}^{1} \frac{2f}{1+f} \, dx \geq 1 \right\}$.


**Disclaimer**: what exactly is meant by *well-defined*? Is the "*subset*" defined as: 
1. $X:=\left\{  f\in L^2(0,1):\int_{0}^{1} f \, dx =1  \right\}$ or 
2. $X:=\left\{  f:(0,1)\to \mathbb{C}:\int_{0}^{1} f \, dx=1  \right\}$

If we define it as 1, then $X$ is well-defined, closed, convex but not linear subspace:
1. **$X$ is well-defined**.
2. **$X$ is closed**: Let $f_{n}\to f$ in $L^2$ where $(f_{n})_{n}\subseteq X$. Then, for $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. $\|f_{n}-f\|_{1}\leq \left\| f_{n}-f \right\|_{2}\mu([0,1])=\left\| f_{n}-f \right\|_{2}<\varepsilon$ by Hölder for all $n\geq N$. Therefore, $$\int_{0}^{1} f \, dx = \int_{0}^{1} f_{n}-f \, dx +\int_{0}^{\infty} f_{n} \, dx <\varepsilon+1$$By taking $\varepsilon\to {0}$, we get that $f\in X$. 
3. **$X$ is convex**: for $f,g\in X$ with $t\in[0,1]$, convexity follows from the linearity of integrals.
4. **$X$ is not a linear subspace**: for $f\in X$, $2f$ has integral $2$ and therefore not in $X$.

If we define it as 2, then $f(x)=\frac{1}{2\sqrt{ x }}$ gives us an counterexample. We have: $$\int_{0}^{1} \frac{1}{2\sqrt{ x }} \, dx =\sqrt{ x }|^1_{0}=1$$But $\left\| f \right\| _{2}^2=\int_{0}^{1} \frac{1}{4x} \, dx =\infty$.

---
> [!def] Problem 4
> Let $H$ be a $\mathbb{R}$-inner product space. 
> 1. Prove the identity: $$\left| x \right| \left| y \right| -\braket{ x , y } = \frac{\left| x \right| \left| y \right|}{2}\left| \frac{x}{\left| x \right| }-\frac{y}{\left| y \right| } \right| ^{2}\geq 0,\quad \forall x,y\in H$$
> 2. Characterize the set $C\subseteq H\times H$ of pair of vectors that saturate the Cauchy-Schwarz inequality, i.e. $\braket{ x , y }=\left| x \right|\left| y \right|$. Plot $C$ in the case $H=\mathbb{R}$.

We have: 
1. For any $x,y\in H$:$$\begin{align}\left| x \right| \left| y \right| -\braket{ x , y } &=\frac{\left| x \right| \left| y \right| }{2}\left( 2-\frac{2\braket{ x , y } }{\left| x \right| \left| y \right| } \right)\\&=\frac{\left| x \right| \left| y \right| }{2}\left( \left\langle \frac{x}{\left| x \right| } , \frac{x}{\left| x\right| } \right\rangle+\left\langle \frac{y}{\left| y \right| } , \frac{y}{\left| y \right| } \right\rangle -2 \left\langle \frac{x}{\left| x \right| } , \frac{y}{\left| y \right| } \right\rangle  \right)\\&=\frac{\left| x \right| \left| y \right| }{2}\left\langle \frac{x}{\left| x \right| } -\frac{y}{\left| y \right| }, \frac{x}{\left| x \right| } -\frac{y}{\left| y \right| }\right\rangle\\&=\frac{\left| x \right| \left| y \right| }{2}\left|\frac{x}{\left| x \right| } -\frac{y}{\left| y \right| }\right|^2\geq 0 \end{align}$$
2. From the above identity, $(x,y)\in C$ if and only if:
	1. $x=0$ or $y=0$ or
	2. $\frac{x}{\|x\|}-\frac{y}{\|y\|}=0$, 

	Therefore, on $H=\mathbb{R}$, $C:=\{ (x,y)\in \mathbb{R}^{2}: xy\geq 0 \}$.
	



