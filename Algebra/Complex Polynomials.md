#Definition #Algebra 

> [!definition]
> ***Complex polynomials*** are elements in the [[polynomial ring]] $\mathbb{C}[X]$ on the field $\mathbb{C}$.
---
##### Properties
> [!lemma] Theorem 1 (Fundamental Theorem of Algebra)
> A polynomial $f\in \mathbb{C}[X]$ with $\deg(f)\geq 1$ has at least one root.

^25037e

> [!proof]- Proof (Topology)
> Wlog assume that $f$ is monic. Assume that $f$ has no root. Then, we can define: $$h:[0,1]\times \mathbb{R}\to S^1,\quad (s,t)\mapsto \frac{f(t\exp(2\pi is)) /f(t)}{\left| f(t\exp(2\pi is)) /f(t) \right| }$$which is well-defined as $f$ admits no roots. Then, 
> 1. $h(1,t)=1$ for all $t\in \mathbb{R}$.
> 2. $h(0,t)=1$ for all $t\in \mathbb{R}$.
> 3. $h(s,0)=1$ for all $s\in[0,1]$.
>    
> Therefore, for any $t\in \mathbb{R}$, $\gamma_{t}:[0,1]\to S^1, s\mapsto h(s,t)$ is a loop at $1$ with $\gamma_{0}=\varepsilon_{1}$. By rescaling the restriction of $h$ to $t\in [0,1]$, we see that $\gamma_{t}\sim_{p}\gamma_{0}=\varepsilon_{1}$ for all $t\in \mathbb{R}$. Hence, $\gamma_{t}\in \pi_{1}(S^1,1)$ for all $t\in \mathbb{R}$.
> 
> Now, take $R\in \mathbb{R}$ large and define $f_{t}\in \mathbb{C}[X]$ with: $$f_{t}(x):=x^n+t(f(x)-x^n)$$for $0\leq t\leq 1$. Then, $f_{t}$ does not vanish for $\left| x \right|=R$ and there exists a path homotopy: $$\tilde{h}(s,t):=\frac{f_{t}(Re^{2\pi is}) / f_{t}(R)}{\left| f_{t}(Re^{2\pi is}) / f_{t}(R) \right| }$$as $\tilde{h}(0,t)=1$ and $\tilde{h}(1,t)=1$ for all $t\in \mathbb{R}$ from $\tilde{h}(s,0)=e^{2\pi ins}$ to $\tilde{h}(s,1)=h(s,R)=\gamma_{R}(s)$. Therefore, $s\mapsto e^{2\pi ins}$ is path homotopic to $\varepsilon_{1}$ in $S^1$, which is a contradiction.

> [!proof]- Proof (Algebraic Topology)
> We extend $f$ into $\widehat{f}:\mathbb{C}\cup \{ \infty \}\to \mathbb{C}\cup \{ \infty \}$ where $\widehat{f}(\infty)=\infty$ and $\widehat{f}|_{\mathbb{C}}=f$. Then, using stereographic projections, we can express this as a smooth map $p:S^2\to S^2$.
> 
> Now, let $z\in \mathbb{C}$ be a [[Submersion|critical point]]. Then, $d_{z}p$ is not a isomorphism and $\text{ker }d_{z}p\neq 0$. As $p$ is holomorphic, $d_{z}p$ is linear in $\mathbb{C}$ and we have that $d_{z}p=0$. Hence, $p'(z)=0$. However, as $p$ is a polynomial and $\deg(p)\geq 1$, by Liouville, $p'\not\equiv 0$. Hence, there are finitely many critical points. However, $p(\mathbb{C})$ is an infinite set as $p$ is path connected and not constant. Hence, there exists a regular value $w\in \mathbb{C}$ in the image of $p$. 
> 
> We can then write $p(z)=u(z)+iv(z)$ and by CRE, $$\det d_{z}p=(\partial_{x}u)^{2}+(\partial_{y}v)^{2}>0$$for every regular point $z\in p ^{-1}(w)$. Therefore, $$\deg(p)=\sum_{z\in p ^{-1}(w)}^{}\underbrace{ \varepsilon_{z}(p) }_{ = 1 }>0$$This shows that $p$ is surjective and there exists a root.

^f27756

---
