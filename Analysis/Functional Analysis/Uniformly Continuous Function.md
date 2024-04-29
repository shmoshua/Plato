#Definition #FunctionalAnalysis 

> [!definition]
> Let $(X,d)$ be a [[Metric Space|metric space]] and $G$ a [[Locally Compact Topological Group|locally compact Hausdorff group]]. A function $f:G\to X$ is ***left uniformly continuous*** if for all $\varepsilon>0$, there exists $V\ni e$ a neighborhood of $e$ s.t. $$d(f(x),f(y))<\varepsilon, \quad \forall y^{-1}x\in V$$
- **Remark**: This implies that $d(f(gx),f(gy))<\varepsilon$ for all $y^{-1}x\in V$; this is why it is called *left* uniformly continuous.
---
##### Properties
> [!lemma] Lemma 1
> We have:
> 1. For all $f\in C_{00}(G)$, $$\begin{array}{cccc} {}&{G}&\to&{C_{00}(G)}\\&{x} &\mapsto & {\lambda(x)f} \end{array}{}$$is left uniformly continuous w.r.t. $\|\cdot\|_{\infty}$.
> 2. For $1\leq p<+\infty$ and $f\in L^p(G)$, $\|\lambda(x)f\|_{p}=\|f\|_{p}$ and: $$\begin{array}{cccc} {}&{G}&\to&{L^p(G)}\\&{x} &\mapsto & {\lambda(x)f} \end{array}{}$$is left uniformly continuous w.r.t. $\|\cdot\|_{p}$.

> [!proof]+
> We have: 
> 1. For $x,y\in G$, $$\|\lambda(x)f-\lambda(y)f\|_{\infty}=\|\lambda(y^{-1}x)f-f\|_{\infty}$$Therefore, we are reduced to show that for every $\varepsilon>0$, there exists $W\ni e$ open s.t. $$\left| f(zg)-f(g) \right| <\varepsilon,\quad \forall g\in G,z\in W$$Let $K:=\text{supp}(f)$ and there exists $V_{0}\ni e$ open s.t. $V_{0}=V_{0}^{-1}$ and $\overline{V_{0}}$ compact.