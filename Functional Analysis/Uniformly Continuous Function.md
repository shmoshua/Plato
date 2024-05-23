#Definition #FunctionalAnalysis 

> [!definition]
> Let $(X,d_{X})$ and $(Y,d_{Y})$ be [[Metric Space|metric spaces]]. A function $f:X\to Y$ is ***uniformly continuous*** if for all $\varepsilon>0$, there exists $\delta>0$ s.t. $$d_{X}(x,y)<\delta\implies d_{Y}(f(x),f(y))<\varepsilon,\quad \forall x,y\in X$$
> Similarly, with a [[topological group]] $G$ and $X$ metric, a function $f:G\to X$ is called ***left (right) uniformly continuous*** if for all $\varepsilon>0$, there exists a neighborhood $V$ of $e_{G}$ s.t. $$d(f(x),f(y))<\varepsilon, \quad \forall y^{-1}x\in V \quad (\text{resp. }xy^{-1}\in V)$$
- **Remark**: This implies that $d(f(gx),f(gy))<\varepsilon$ for all $y^{-1}x\in V$; this is why it is called *left* uniformly continuous.
---
##### Properties
> [!lemma] Lemma 1
> We have:
> 1. For all $f\in C_{00}(G)$, $$\begin{array}{cccc} {}&{G}&\to&{C_{00}(G)}\\&{x} &\mapsto & {\lambda(x)f} \end{array}{}$$is left uniformly continuous w.r.t. $\|\cdot\|_{\infty}$.
> 2. For $1\leq p<+\infty$ and $f\in L^p(G)$, $\|\lambda(x)f\|_{p}=\|f\|_{p}$ and: $$\begin{array}{cccc} {}&{G}&\to&{L^p(G)}\\&{x} &\mapsto & {\lambda(x)f} \end{array}{}$$is left uniformly continuous w.r.t. $\|\cdot\|_{p}$.

^9177e0

> [!proof]-
> We have: 
> 1. For $x,y\in G$, $$\|\lambda(x)f-\lambda(y)f\|_{\infty}=\|\lambda(y^{-1}x)f-f\|_{\infty}$$Therefore, we are reduced to show that for every $\varepsilon>0$, there exists $W\ni e$ open s.t. $$\left| f(zg)-f(g) \right| <\varepsilon,\quad \forall g\in G,z\in W$$Let $K:=\text{supp}(f)$ and there exists $V_{0}\ni e$ open s.t. $V_{0}=V_{0}^{-1}$ and $\overline{V_{0}}$ compact. Fix $\varepsilon>0$. Then, for all $x\in G$, we can find $V_{x}\ni e$ open, with $V_{x}\subseteq V_{0}$ s.t. $$\left| f(zx)-f(x) \right| <\varepsilon /2,\quad \forall z\in V_{x}$$Let $U_{x}\ni e$ open with $U_{x}^{2}\subseteq V_{x}$. Then, we have: $$\overline{V_{0}}\cdot K \subseteq \bigcup_{x\in G}^{}U_{x}\cdot x=G$$Since $\overline{V_{0}}\cdot K$ is compact, there exists $x_{1},\dots,x_{n}\in G$ s.t. $$\overline{V_{0}}\cdot K\subseteq \bigcup_{i=1}^{n}U_{x_{i}}\cdot x_{i}$$Let $W:=\bigcap_{i=1}^{n}U_{x_{i}}$ and $z\in W$ and $g\in G$: 
> 	1. if $g\notin \overline{V_{0}}\cdot K$, then since $\text{supp}(f)\subseteq \overline{V_{0}}\cdot K$, $f(g)=0$. Further, if $f(zg)\neq 0$, then $zg\in \text{supp}(f)$ and $g\in z^{-1}\text{supp}(f)\subseteq W^{-1}\text{supp}(f)$. However, $W\subseteq V_{0}$ and $W^{-1}\subseteq V_{0}^{-1}=V_{0}$. This is a contradiction and $f(zg)=0$.
> 	2. if $g\in \overline{V_{0}}\cdot K\subseteq \bigcup_{x=1}^{n}U_{x_{i}}x_{i}$, then $g\in U_{x_{i}}x_{i}$ for some $i\in[n]$. Then, as $U_{x_{i}}\subseteq U_{x_{i}}^{2}\subseteq V_{x_{i}}$, $$\left| f(g)-f(x_{i}) \right|=\left| f(zx_{i})-f(x_{i}) \right| <\varepsilon /2  $$If $z\in W\subseteq U_{x_{i}}$, then $zg\in U_{x_{i}}^{2} x_{i}\subseteq V_{x_{i}}\cdot x_{i}$ Therefore, $$\left| f(zg)-f(x_{i}) \right| <\varepsilon /2$$This shows that $\left| f(zg)-f(g) \right|<\varepsilon$.
> 2. Let $1\leq p<+\infty$. We will use that $C_{00}(G)$ is dense in $L^p(G)$. For $f\in L^p$ and $\varepsilon>0$, pick $g\in C_{00}(G)$ s.t. $\|f-g\|_{p}<\varepsilon$. Then, $$\begin{align}\left\| \lambda(x)f-\lambda(y)f \right\| _{p}&=\left\| \lambda(x)(f-g)+\lambda(x)g-\lambda(y)g+\lambda(y)(g-f) \right\|\\&\leq 2\|f-g\|_{p}+\|\lambda(x)g-\lambda(y)g\|_{p}\\&<2\varepsilon+\|\lambda(x)g-\lambda(y)g\|_{p}\end{align} $$Then, $$\|\lambda(x)g-\lambda(y)g\|_{p}^p=\|\lambda(y^{-1}x)g-g\|^p_{p}=\int_{G}^{} \left| g(x ^{-1}yt)-g(t) \right|^p  \, d\mu(t) $$Fix $V_{0}=V_{0}^{-1}\ni e$ open with $\overline{V_{0}}$ compact and restrict $y^{-1}x\in \overline{V_{0}}$. Let $C:=\overline{V_{0}}\cdot \text{supp}(g)$. 
> 		1. if $t\notin C$, then $g(x ^{-1}yt)=0$ and $g(t)=0$. 
> 		   
> 		Therefore, $$\|\lambda(x)g-\lambda(y)g\|_{p}^p=\int_{C}\left| \lambda(y^{-1}x)g(t)-g(t) \right| ^p  \, d\mu(t)\leq \|\lambda(y^{-1}x)g-g\|_{\infty}\cdot \mu(C) $$Now we are done because there exists $W\ni e$ open s.t.  $$\|\lambda(y^{-1}x)g-g\|_{\infty}< \varepsilon /\mu(C),\quad \forall y^{-1}x\in W$$
