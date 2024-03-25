#Definition #DifferentialGeometry 

> [!definition]
> Let $(M,g)$ be a [[Riemannian manifold]] and $\gamma:[a,b]\to M$ be a $C^1$-curve. Then, the ***length*** of $\gamma$ is:
> $$L(\gamma):=\int_{a}^{b} \sqrt{ g_{\gamma(t)}(\gamma'(t),\gamma'(t)) } \, dt  $$For a piecewise $C^1$-curve $\gamma:[a,b]\to M$ with $a=a_{0}<a_{1}<\dots<a_{n}=b$ with $\gamma|_{[a_{i},a_{i+1}]}\in C^1$ for all $i$, $$L(\gamma):=\sum_{i=0}^{n-1}L(\gamma|_{[a_{i},a_{i+1}]})$$
> If $(M,g)$ is connected and $p,q\in M$, the ***distance*** between $p,q$ is defined as:$$d(p,q):=\inf\{ L(\gamma)|\gamma:[a,b]\to M\text{ piecewise }C^1,\gamma(a)=p,\gamma(b)=q \}$$
- **Remark**: Since $t\mapsto g_{\gamma(t)}(\gamma'(t),\gamma'(t))$ is bounded, $L(\gamma)<+\infty$.
- **Remark**: If $\alpha:[\tilde{a},\tilde{b}]\to[a,b]$ is a $C^1$-diffeomorphism and $\tilde{\gamma}:=\gamma \circ\alpha$ is a reparametrization of $\gamma$, then $L(\tilde{\gamma})=L(\gamma)$. 
---
##### Properties
> [!lemma] Theorem 1
> Let $(M,g)$ be a connected [[Riemannian manifold]]. Then, 
> 1. $(M,d)$ is a [[metric space]] where $d$ is the distance.
> 2. the topology $\mathcal{T}_{d}$ equals the topology of the [[topological manifold]] $M$.

> [!proof]+
> We have: 
> 1. **Showing that $d(p,q)<+\infty$ for $p,q\in M$**:
>    Since $M$ is connected and locally path connected, there exists a continuous path $\gamma:[0,1]\to M$ s.t. $\gamma(0)=p$ and $\gamma(1)=q$. Therefore, we can cover the compact set $\gamma([0,1])$ with a finite number of charts $(U_{i},\varphi_{i})_{i=1}^N$ s.t. $\varphi_{i}(U_{i})=B_{<1}(0)$ with $p\in U_{1}$, $U_{i}\cap U_{i+1}\neq \varnothing$ and $q\in U_{N}$. Choose $p_{i}\in U_{i}\cap U_{i+1}$. Then, $\tilde{\gamma}$ is a curve concatenating $\gamma_{1},\dots,\gamma_{N}$ where: $$\gamma_{i}:[0,1]\to M,s\mapsto \varphi_{i}^{-1}(\varphi(p_{i-1})+s(\varphi_{i}(p_{i})-\varphi_{i}(p_{i-1})))$$Then, $d(p,q)\leq L(\tilde{\gamma})=\sum_{i=1}^{N}L(\gamma _{i})<+\infty$.
> 2. **Showing that $d(p,q)\geq 0$ with equality if and only if $p=q$**:
> 	Suppose $p\neq q$. Let $(U,\varphi)$ be a chart at $p$ s.t. $\varphi(p)=0$. Then, there exists $\varepsilon>0$ s.t. $q\notin \varphi ^{-1}(B_{\leq \varepsilon}(0))$
>    
>    