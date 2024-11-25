#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. The ***sparsest cut*** problem is given as: $$S^{*}\in \underset{ S\subseteq V }{ \text{argmin} } \frac{\left| E(S,V \backslash S) \right| }{\left| S \right| \cdot \left| V \backslash S \right| }$$
---
##### Properties
> [!lemma] Theorem (LP)
> Consider the following LP: $$\begin{array}{rll} \min& \sum_{\{ u,v \}\in E}^{}d_{uv}\\\text{subject to}& d_{u,v}\geq 0,\quad d_{uv}=d_{vu}&\forall u,v\in V\\&d_{u,v}\leq d_{v,w}+d_{w,v}&\forall u,v,w\in V\\&\sum_{u,v}^{}d_{uv}=1\end{array}$$
> Let $d^{*}$ be the LP minimum. 

> [!proof]+
> Firstly, notice that $d^{*}$ is a pseudo-metric. Hence, there exists a metric embedding $\phi:V\to \mathbb{R}^k$ for $k\in \text{O}(\log n)$ s.t. $\frac{d(u,v)}{\log n}\leq \|\phi(u)-\phi(v)\|_{1}\leq d(u,v)$ for all $u,v\in V$.
> 
> Let $\phi:=(\phi_{1},\dots,\phi_{k})$ and $j:=\arg\min_{i\in[k]} \frac{\sum_{\{ u,v \}\in E}\left| \phi_{i}(u)-\phi_{i}(v) \right|}{\sum_{u,v\in V}^{}\left| \phi_{i}(u)-\phi_{i}(v) \right|}$. Let $a=\min_{v}\phi_{j}(v)$ and $b=\max_{v}\phi_{j}(v)$. Then, let $\tau \sim \text{Uniform}([a,b])$ and we define: $$S_{\tau}:=\{ v\in V:\phi_{j}(v)\leq \tau \}$$Then, $$\left| \chi_{S_{\tau}}(u)- \chi_{S_{\tau}}(v) \right|=\begin{cases}1& \min\{ \phi_{j}() \}\end{cases}$$


> [!lemma] Lemma 1
> Let $a_{1},\dots,a_{k},b_{1},\dots,b_{k}\geq 0$ for which $\sum_{i=1}^{k}b_{i}\neq 0$. Then, $$\frac{\sum_{i=1}^{k}a_{i}}{\sum_{i=1}^{k}b_{i}}\geq \min_{i\in[k]} \frac{a_{i}}{b_{i}}$$

> [!proof]-
> Let $k=2$. Then, let $p:=\min\left\{  \frac{a}{b}, \frac{c}{d}  \right\}$
> $$\frac{a+c}{b+d}=\frac{\frac{a}{b}+\frac{c}{d}\cdot \frac{d}{b}}{1+\frac{d}{b}}\geq p$$This proves the statement as it holds with $k=1$.  