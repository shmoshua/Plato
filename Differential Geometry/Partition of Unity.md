#Definition #DifferentialGeometry 

> [!definition]
> Let $X$ be a [[topological space]]. A ***partition of unity*** on $X$ is a collection $\{ f_{j} \}_{j}$ of continuous functions $f_{j}:X\to[0,1]$ s.t. $\sum_{j\in J}^{}f_{j}(x)=1$ for all $x\in X$.
---
##### Examples
> [!h] Example 1 (Smooth Manifolds)
> Let $M$ be a [[smooth manifold]] and $\{ V_{\alpha} \}_{\alpha}$ be an open cover of $M$. Then, there exists a countable partition of unity $\{ f_{i} \}_{i\in F}$ s.t.
> 1. $f_{i}\in C^\infty_{00}(M)$
> 2. $\{ \text{supp }f_{i}: i\in F\}$ is a locally finite cover of $M$ refining $\{ V_{\alpha} \}_{\alpha}$. 

> [!proof]-
> From [[Atlas|Lemma 4]], there is a countable family of charts $(U_{i},\varphi_{i})_{i}$ with the described properties. Then, by the smooth version of Urysohn's lemma, there exists a smooth function $g:\mathbb{R}^m\to [0,1]$ with: 
> 1. $g(x)=1$ for $x\in C_{\varepsilon}^m(0)$ and 
> 2. $g(x)=0$ for $x\notin C_{2\varepsilon}^m(0)$
> 
> Now, define $g_{i}:M\to \mathbb{R}$: $$g_{i}(x):=\begin{cases} g(\varphi(x))&x\in U_{i}\\0&x\notin U_{i}\end{cases}$$ Then, $\sum_{i\in I}^{}g_{i}$ is well-defined, smooth and strictly positive. Therefore, $$f_{i}:=\frac{g_{i}}{\sum_{j\in I}^{}g_{j}}$$has the desired properties.
---
