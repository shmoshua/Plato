#Definition #LST #LinearAlgebra 

> [!definition]
> Let $(U,F)$ and $(V,F)$ be two linear spaces. The function $\mathcal{A}:U \to V$ is called a ***linear map*** if and only if for all $u_{1},u_{2}\in U$ and $a_{1},a_{2}\in F$: $$\mathcal{A}(a_{1}u_{1}+a_{2}u_{2})=a_{1}\mathcal{A}(u_{1})+a_{2}\mathcal{A}(u_{2})$$
---
##### Properties
> [!lemma] Theorem LinMap.1
> Any linear map $\mathcal{A}:U\to V$ between two finite-dimensional linear spaces can be represented as a matrix by fixing the bases for the two spaces.

> [!Proof]-
> Let $\{ u_{j} \}_{j=1}^n$ and $\{ v_{i} \}_{i=1}^m$ be the bases of $(U,F)$ and $(V,F)$ respectively. We define for all $j\in[n]$: $$y_{j}:=\mathcal{A}(u_{j})\in V$$
> Therefore, the vectors $y_{j}\in V$ can be represented using $\{ v_{i} \}_{i=1}^m$. In other words, for all $j=1,\dots,n$, there exists unique $a_{ij}\in F$ s.t. $$y_{j}=\sum_{i=1}^{m}a_{ij}v_{i}$$ Then, we can define a matrix $A:=[a_{ij}]_{i,j}\in F^{m,n}$, which is unique as representations are unique.
>
> Let $x\in U$. Then, we have a unique representation $\xi\in F^n$ of $x$ with $\{ u_{j} \}_{j=1}^n$ and a unique representation $\eta\in F^m$ of $\mathcal{A}(x)$ with $\{ v_{i} \}_{i=1}^m$. Then, we have:
> $$\mathcal{A}(x)=\mathcal{A}\left( \sum_{j=1}^{n} \xi_{j}u_{j} \right)=\sum_{j=1}^{n}\xi_{j}\mathcal{A}(u_{j})=\sum_{j=1}^{n}\xi_{j}\sum_{i=1}^{m}a_{ij}v_{i}=\sum_{i=1}^{m}v_{i}\sum_{j=1}^{n}\xi_{j}a_{ij}$$
> by uniqueness of representation, $\eta_{j}=\sum_{j=1}^{n}\xi_{j}a_{ij}$ and therefore $$\eta=A\xi$$
---
> [!lemma] Theorem LinMap.2
> Consider two [[Analysis/Normed Space]] $(U,F,\|\cdot\|_{U})$ and $(V,F,\|\cdot\|_{V})$ and a linear function $\mathcal{A}:U \to V$. The following statements are equivalent: 
> 1. $\mathcal{A}$ is [[Continuous Functions in Normed Spaces|continuous]]
> 2. $\mathcal{A}$ is continuous at 0.
> 3. $\mathcal{A}$ is [[Bounded Linear Map|bounded]], i.e. $\sup_{\|u\|_{U}=1}\|\mathcal{A}(u)\|_{V}<\infty$
> 4. $\mathcal{A}$ is [[Lipschitz Function|Lipschitz continuous]] with Lipschitz constant $\left\| \mathcal{A} \right\|$.
> 
> For more, visit [[Bounded Linear Map|bounded linear maps]].

> [!Proof]-
> (1 -> 2): By definition
> (2 -> 3): Assume that $\sup_{\|u\|_{U}=1}\|\mathcal{A}(u)\|_{V}=+\infty$. Then, for all $n>0$, there exists $u_{n}\in U$ with $\left\| u_{n} \right\|=1$ s.t. $\left\| \mathcal{A}(u_{n}) \right\|_{V}\geq n$. Consider $\hat{u}_{n}:=\frac{u_{n}}{n}\in U$. Clearly, $\left\| \hat{u}_{n} \right\|_{U}=\left\| u_{n} \right\|_{U}/n=1/n\to0$. Therefore, $\lim_{ n \to \infty }\hat{u}_{n}=0$. On the other hand, $$\left\| \mathcal{A}(\hat{u}_{n}) \right\| _{V}=\left\| \mathcal{A}(u/n) \right\|_{V}=\left\| \mathcal{A}(u) \right\| _{V}/n \geq \frac{n}{n}=1$$Therefore, $\lim_{ n \to \infty }\|\mathcal{A}(\hat{u}_{n})\|_{V}\neq 0=\mathcal{A}(0)$ and the function cannot be continuous at $0$.
> (3 -> 4): $$\left\| \mathcal{A}(x)-\mathcal{A}(y) \right\| _{V}=\left\| \mathcal{A}(x-y) \right\| _{V}\leq \left\| \mathcal{A} \right\| \left\| x-y \right\| _{U}$$
> (4 -> 1): Is obvious.
> (3 -> 1): From the definition we have that there exists $M$, for all $u\in U$, we have: $\left\|  \mathcal{A}(u) \right\|_{V}\leq M \|u\|_{U}$ (also holds for $0$ as $\mathcal{A}(0)=0$.) Therefore, for all $u,u'\in U$, $$\left\| \mathcal{A}(u)-\mathcal{A}(u') \right\|_{V} =\left\| \mathcal{A}(u-u') \right\|_{V}\leq M\left\| u-u' \right\|_{U}  $$
> It follows that for all $u\in U$ and for all $\varepsilon>0$, there exists $\delta>0$ s.t. $\left\| \mathcal{A}(u)-\mathcal{A}(u') \right\|_{V}<\varepsilon$ holds if $\left\| u-u' \right\|_{U}<\delta$ holds.
---
> [!lemma] Theorem LinMap.3
> All linear functions $\mathcal{A}:U \to V$ between two finite-dimensional normed spaces $(U,F,\|\cdot\|_{U})$, $(V,F,\|\cdot\|_{V})$ are continuous. If $U$ or $V$ is infinite-dimensional, the linear function need not be continuous.

> [!Proof]-
> Fix bases for the two spaces s.t. $\mathcal{A}$ is represented by a matrix $A$. As $U$ and $V$ are finite and from [[Equivalence of Norms|Theorem EquivNorm.3]], all norms are equivalent. So we will consider the [[infinity norm]].
> 
> If $A=0$, then the function is constant and continuous. Otherwise, consider $u\in U$ and note that: $$\left\|  \mathcal{A}(u)-\mathcal{A}(u') \right\| _{\infty}=\left\| A(u-u') \right\|_{\infty} \leq \|A\|_{\infty}\|u-u'\|_{\infty}$$As $\|A\|_{\infty}$ is always finite, for any $\varepsilon>0$, there exists $\delta:= \frac{\varepsilon}{\left\| A \right\|_{\infty}}$ s.t. $\left\| u-u' \right\|_{\infty}<\delta$ implies $\left\| \mathcal{A}(u)-\mathcal{A}(u') \right\|_{\infty}<\varepsilon$. Therefore, the function is continuous.
>
> We will also provide an example for the case $V$ is infinite-dimensional. Let $U=(\mathbb{R}^n,\mathbb{R},\|\cdot\|_{2})$ and $V=(C([0,\infty),\mathbb{R}^n),\mathbb{R},\|\cdot\|_{\infty})$ s.t. for every $x\in U$, $(\mathcal{A}(x))(t):=e^{\lambda t}x$. Then, for $\lambda>0$, we have for any $x\in U$ s.t. $x\neq 0$, every $\delta>0$ and $\|x\|_{2} < \delta$ but $\left\| \mathcal{A}(x) \right\|=\infty$. However, as $\mathcal{A}(0)=0$, the function is discontinuous at 0. 

---
> [!lemma] Theorem LinMap.4
> For two [[Continuous Functions|continuous]] linear maps $\mathcal{A},\tilde{\mathcal{A}}:(V,F,\|\cdot\|_{V})\to(W,F,\|\cdot\|_{W})$ and $\mathcal{B}:(U,F,\|\cdot\|_{U})\to(V,F,\|\cdot\|_{V})$ with the [[Induced Norm|induced norm]] $\|\cdot\|$, we have the followings:
> 1. For all $v\in V$: $\left\| \mathcal{A} (v)\right\|_{W} \leq \left\| \mathcal{A} \right\|\cdot \|v\|_{V}$
> 2. For all $a\in F$: $\left\| a\mathcal{A} \right\|=|a|\cdot \left\| \mathcal{A} \right\|$
> 3. $\left\| \mathcal{A}+\tilde{\mathcal{A}} \right\|\leq \left\| \mathcal{A} \right\|+\left\| \tilde{\mathcal{A}} \right\|$
> 4. $\left\| \mathcal{A} \right\|=0$ if and only if $\mathcal{A}(v)=0$ for all $v\in V$
> 5. $\left\| \mathcal{A} \circ \mathcal{B} \right\| \leq \left\| \mathcal{A} \right\|\cdot \left\| \mathcal{B} \right\|$
>    
> Then, the induced norm is a norm on all set of bounded and linear maps $\mathcal{A}:V \to W$, i.e. $\mathcal{B}(V,W)$ 

> [!Proof]-
> Everything is a direct consequence of the induced norm being a norm.

---

##### Related Definitions
- [[Kernel and Image]]
- [[Bounded Linear Map]]