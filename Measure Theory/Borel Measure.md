#Definition #MeasureTheory 

> [!definition]
> Let $X$ be a [[Locally Compact Hausdorff Space|locally compact Hausdorff space]]. A [[Measure| measure]] $\mu$ on $X$ is ***Borel*** if every [[Borel Sigma-Algebra|Borel set]] $V\in \mathcal{B}(X)$ is $\mu$-measurable.
> 
> Further, a Borel measure $\mu$ on $X$ is called ***Borel regular*** if for all $A \subseteq X$ there exists $B\in \mathcal{B}(X)$ with $A \subseteq B$ s.t. $$\mu(B)=\mu(A)$$
---
##### Properties
> [!lemma] Theorem 1 (Carathéodory's criterion)
> A [[Measure|metric measure]] $\mu$ on $\mathbb{R}^n$ is Borel.

> [!proof]-
> It is enough to show that all closed sets $F\subseteq \mathbb{R}^n$ is $\mu$-measurable, i.e. for every $B \subseteq \mathbb{R}^n$: $$\mu(B)\geq \mu(B \cap F)+ \mu(B \backslash F)$$
> Wlog assume $\mu(B)<+\infty$. For $k \geq 0$, define: $$F_{k}:=\left\{  x\in \mathbb{R}^n:d(x,F)\leq \frac{1}{k}  \right\}$$Then, as $\mu$ is metric, $$d(B\backslash F_{k}, B \cap F)\geq \frac{1}{k} > 0$$Therefore, $$\mu(B \cap F)+\mu(B \backslash F_{k})=\mu((B\cap F)\cup(B \backslash F_{k}))\leq\mu(B)$$Now, let's show that $\lim_{ k \to \infty }\mu(B \backslash F_{k})=\mu(B \backslash F)$. For $k\in \mathbb{N}$, we have: $$R_{k}:=(F_{k} \backslash F_{{k+1}}) \cap B=\left\{  x\in B: \frac{1}{k+1}< d(x,F)\leq \frac{1}{k}  \right\}$$Then, $$B \backslash F=(B \backslash F_{k}) \cup \bigcup_{\ell=k}^{\infty}R_{\ell}$$Therefore, $$\mu(B \backslash F_{k})\leq \mu(B \backslash F)\leq \mu(B \backslash F_{k})+\sum_{\ell=k}^{\infty}\mu(R_{\ell})$$It follows that $\lim_{ k \to \infty }\mu(B \backslash F_{k})=\mu(B \backslash F)$, which proves the statement.
---
> [!lemma] Theorem 2
> A Borel measure $\mu$ on $\mathbb{R}^n$ is metric.

> [!proof]-
> For $A,B \in \mathbb{R}^n$, we will show that if $$d(A,B):=\inf \{ |a-b|: a\in A,b\in B\}>0$$then $\mu(A \cup B)=\mu(A)+\mu(B)$. Let $U$ be an open set s.t. $A \subseteq U$ and $B \cap U = \varnothing$. Then, $$\mu(A \cup B)=\mu((A\cup B)\cap U)+\mu((A\cup B)\backslash U)=\mu(A)+\mu(B)$$
---
> [!lemma] Lemma 3
> Let $X$ be a compact [[Hausdorff space]] and $C(X,\mathbb{R})=C_{0}(X,\mathbb{R})$. Further, let $M(X,\mathbb{R})$ be the set of all [[Signed Measure|signed]] [[Borel Regular Measure|Borel-regular measures]] on $X$. Then, 
> 1. The set: $$\left\{  \mu\in  M(X,\mathbb{R}): \left| \int_{X}^{} f \, d\mu  \right| \leq 1,\forall f\in C(X,\mathbb{R}), \left\| f \right\| _{b}\leq 1 \right\}$$
>  is weak\*-closed.
> 2. The space of probability measures, $$M^1(X):=\{ \mu\in M(X,\mathbb{R}):\mu \text{ is non-negative, }\mu(X)=1 \}$$is weak\*-closed.
		
> [!proof]-
> We have: 
> 1. From the [[Analysis/Complex Measure|Riesz representation theorem]], there exists a bijection: $$\begin{array}{cccc}R:&{(M(X,\mathbb{R}),\|\cdot \|)}&\to&{(C(X,\mathbb{R})^{*},\|\cdot \|_{b})}\\&{\mu} &\mapsto & {\Phi_{\mu}} \end{array}{}$$
> where $\Phi_{\mu}(f)=\int_{X}^{} f \, d\mu$ and $\|\mu\|=\left| \mu \right|(X)$.
> 
>    On $C(X,\mathbb{R})^{*}$, the weak\*-topology is the [[initial topology]] with $\mathcal{F}:=\{ (J(f),\mathbb{R}) \}_{f\in C(X,\mathbb{R})}$ with $$\begin{array}{cccc} {J(f):}&{C(X,\mathbb{R})^*}&\to&{\mathbb{R}}\\&{\Phi} &\mapsto & {\Phi(f)} \end{array}{}$$
> 
>    Therefore, we can extend the weak\*-topology onto $M(X,\mathbb{R})$ as the initial topology with $\mathcal{F}:=\{ (J(f),\mathbb{R}) \}_{f\in C(X,\mathbb{R})}$ where: $$\begin{array}{cccc} {J(f):}&{M(X,\mathbb{R})}&\to&{\mathbb{R}}\\&{\mu} &\mapsto & {\int_{X}f  \, d\mu } \end{array}{}$$Then, we have that the unit closed ball: $$M_{\leq 1}:=\left\{  \mu\in  M(X,\mathbb{R}): \left| \int_{X}^{} f \, d\mu  \right| \leq 1,\forall f\in C(X,\mathbb{R}), \left\| f \right\| _{b}\leq 1 \right\}$$is closed with respect to the extended topology. 
> 
> 2. We define the space of probability measures:
> $$\begin{align}M^1(X)&:=\{ \mu\in M(X,\mathbb{R}):\mu \text{ is non-negative, }\mu(X)=1 \}\\&=\left\{  \mu\in M(X,\mathbb{R}):\int_{X}^{} f \, d\mu \geq 0,\forall f\geq 0\text{ and }\int_{X}^{} 1 \, d\mu =1  \right\}\end{align}$$
> which is a weak\*-closed subset of $M_{\leq 1}$.
---
##### Examples
1. [[Lebesgue Measure]]
2. [[Lebesgue-Stieltjes Measure]]