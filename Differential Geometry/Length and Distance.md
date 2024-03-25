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

> [!proof]- Proof (Incomplete)
> We have: 
> 1. **Showing that $d(p,q)<+\infty$ for $p,q\in M$**:
>    Since $M$ is connected and locally path connected, there exists a continuous path $\gamma:[0,1]\to M$ s.t. $\gamma(0)=p$ and $\gamma(1)=q$. Therefore, we can cover the compact set $\gamma([0,1])$ with a finite number of charts $(U_{i},\varphi_{i})_{i=1}^N$ s.t. $\varphi_{i}(U_{i})=B_{<1}(0)$ with $p\in U_{1}$, $U_{i}\cap U_{i+1}\neq \varnothing$ and $q\in U_{N}$. Choose $p_{i}\in U_{i}\cap U_{i+1}$. Then, $\tilde{\gamma}$ is a curve concatenating $\gamma_{1},\dots,\gamma_{N}$ where: $$\gamma_{i}:[0,1]\to M,s\mapsto \varphi_{i}^{-1}(\varphi(p_{i-1})+s(\varphi_{i}(p_{i})-\varphi_{i}(p_{i-1})))$$Then, $d(p,q)\leq L(\tilde{\gamma})=\sum_{i=1}^{N}L(\gamma _{i})<+\infty$.
> 2. **Showing that $d(p,q)\geq 0$ with equality if and only if $p=q$**:
> 	Suppose $p\neq q$. Let $(U,\varphi)$ be a chart at $p$ s.t. $\varphi(p)=0$. Then, there exists $\varepsilon>0$ s.t. $q\notin \varphi ^{-1}(B_{\leq \varepsilon}(0))=:K$ which is a compact set. 
> 	
> 	Let $\gamma:[0,1]\to M$ be a piecewise $C^1$ curve with $\gamma(0)=p$ and $\gamma(1)=q$. By setting $T:=\sup\{ t\in[0,1]:\gamma([0,t])\subseteq K \}$. Then, $\gamma([0,T])\subseteq K$ as $K$ is closed and $M$ is Hausdorff. We have that $\gamma(T)\in \varphi ^{-1}(\partial B_{<\varepsilon}(0))$. 
> 	
> 	Now we define a curve in $\mathbb{R}^m$. $\tilde{\gamma}:=\varphi \circ\gamma|_{[0,T]}$. Then, by [[Inner Product Space|Cauchy-Schwarz]]:$$L_{\text{euch}}(\tilde{\gamma})=\int_{0}^{T}\left\| \tilde{\gamma}'(t) \right\|   \, dt \geq \int_{0}^{T} \tilde{\gamma}'(t) ^\top\frac{\tilde{\gamma}(T)-\tilde{\gamma}(0)}{\left\| \tilde{\gamma}(T)-\tilde{\gamma}(0) \right\| } \, dt=\left\| \tilde{\gamma}(T)-\tilde{\gamma}(0) \right\|=\varepsilon$$Let $e$ be the pullback of the euclidean metric with $\varphi:U\to \mathbb{R}^m$, which is a Riemannian metric on $U$. Since $K$ is compact, there exists $\lambda>0$ s.t. for all $v\in \text{T}_{p}M$ and $p\in K$: $$\lambda^{2}e(v,v)\leq g_{p}(v,v)$$Therefore, $$L_{g}(\gamma)\geq L_{g}(\gamma|_{[0,T]})\geq\lambda L_{e}(\gamma|_{[0,T]})=\lambda \varepsilon>0$$
> 3. **Triangle inequality is obvious**.
> 4. **Showing the equality of the topology**:
>    Consider $B^d_{<\delta}(p)$ for $\delta<\lambda \varepsilon$ from the previous part. 
> 	   
>    