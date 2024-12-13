#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. For a [[Metric Space|metric]] $d$ on $V$ and a [[normed space|normed vector space]] $(W,\|\cdot\|)$, a ***$\alpha$-metric embedding*** is a map $\phi:V\to W$ s.t. 
> 1. there exists $\alpha\leq 1$ s.t. for all $u,v\in V$:  $\alpha\cdot d(u,v)\leq \left\| \phi(u)-\phi(v) \right\|\leq d(u,v)$

---
##### Properties
> [!lemma] Theorem 1 (Existence of l1-metric Embedding)
> For any pseudo-metric $d$ on $V$, consider:
> ```pseudo
> \begin{algorithm} \caption{$L^1$-Embedding$(d,G)$}
> \begin{algorithmic}
> \For{$i=1,\dots,L:=\log n$}
> \For{$h=1,\dots,H:=1000\log n$}
> \State $S_{i,h}\gets$ Subset of $V$ where each vertex is sampled independently with $\mathbb{P}(v\in S_{i,h})=2^{-i}$
> \State $\phi_{(i-1)H+h}(u)\gets \frac{d(u,S_{i,h}) }{LH}$ for all $u\in V$
>\EndFor\EndFor \Return $\phi:V\to \mathbb{R}^{LH}$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, it holds that
> 1. with high probability $L^1\text{-Embedding}(d,G)$ returns an $\alpha$-$L^1$ embedding for $\alpha=\Theta(\log n)$.

> [!proof]+
> Let $\phi_{i,h}:=\phi_{(i-1)H+h}$. Then, $$\left\| \phi(u)-\phi(v) \right\|_{1} =\sum_{i=1}^{L}\sum_{h=1}^{H}\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right|=\sum_{i=1}^{L}\sum_{h=1}^{H}\frac{\left| d(u,S_{i,h})-d(v,S_{i,h}) \right|}{LH}\leq d(u,v)$$
> Fix $u,v\in V$ and let $t\in\{ 0,1,\dots,\log n \}$ and define: $$\rho_{t}:=\min\{r\geq 0: \left| B_{\leq r} (u)\right|  ,\left| B_{\leq r} (v)\right| \geq 2^t\}$$Then, $\rho_{0}=0$ and $\rho_{t}\leq \rho_{t+1}$. Hence, there exists $j$ s.t. $\rho_{j}< \frac{d(u,v)}{2}\leq \rho_{j+1}$. Let $(\widehat{\rho}_{i})_{i}$ be.a sequence where $\widehat{\rho}_{i}:= \min\left\{  \rho_{i}, \frac{d(u,v)}{2}  \right\}$. 
> 
> We claim that $\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right|\geq (\widehat{\rho}_{i}-\widehat{\rho}_{i-1}) / LH$ for all $i\in[L]$.
> 1. For all $i> j+1$, $\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right| \geq  (\widehat{\rho}_{i}-\widehat{\rho}_{i-1}) / LH = 0$
> 2. For all $i\leq j+1$, we define the following events: 
> 	1. $A_{ih}:=\{ S_{i,h}\cap B_{<\widehat{\rho}_{i}}(u)=\varnothing \}$
> 	2. $B_{ih}:=\{ S_{i,h}\cap B_{<\widehat{\rho}_{i-1}}(v)\neq\varnothing \}$
> 	
> 	We first know that $B_{<\widehat{\rho}_{i}}(u)$ and $B_{<\widehat{\rho}_{i-1}}(v)$ are disjoint by construction. Hence, $A_{ih},B_{ih}$ are independent. Given $A_{ih}\cap B_{ih}$, we have that: $$\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right| =\frac{\left| d(u,S_{i,h})-d(v,S_{i,h}) \right|}{LH}\geq \frac{\widehat{\rho}_{i}-\widehat{\rho}_{i-1} }{LH}$$Further, wlog we may assume that $$\mathbb{P}(A_{ih})=\left( 1-\frac{1}{2^i} \right)^{\left| B_{\leq \widehat{\rho}_{i}} (u)\right| }\geq \left( 1-\frac{1}{2^i} \right) ^{2^i}$$
---
