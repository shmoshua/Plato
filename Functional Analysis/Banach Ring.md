#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a normed [[ring]], i.e. it is equipped with a [[Seminorm|norm]] $\|\cdot\|$.
> 1. $A$ is a ***Banach ring*** if it is [[Banach Space|Banach]] w.r.t. the norm.

---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a Banach ring. For $x\in A$, we have that:
> 1. $\lim_{ n \to \infty }\|x^n\|^{1 / n}\leq \|x\|$.
> 2. if $\lim_{ n \to \infty }\|x^n\|^{1 / n}<1$, then $1-x$ is a unit, i.e. $(1-x)^{-1}=\sum_{n=0}^{\infty}x^n$ where $x^0=1$.

> [!proof]-
> We have:
> 1. $\|x^n\|\leq \|x\|^n$ by Banach ring for all $n$.
> 2. Let $q$ s.t. $\lim_{ n \to \infty }\|x^n\|^{1 / n}< q<1$. Then, there exists $n_{0}\geq 1$ s.t. $\|x^n\|^{1 /n}\leq q$ for all $n\geq n_{0}$, i.e. $\left\| x^n \right\|\leq q^n$. Hence, $$\sum_{n=N}^{\infty}\left\| x^n \right\| \leq \sum_{n=N}^{\infty}q^n=\frac{q^N}{1-q}$$and the series is absolutely convergent. Further, $$(1-x)\sum_{n=0}^{\infty}x^n=\sum_{n=0}^{\infty}x^n-\sum_{n=1}^{\infty}x^n=1$$
---
> [!lemma] Proposition 2 (Quotient and Product Banach Ring)
> Let $A$ and $(A_{i})_{i\in I}$ be Banach rings. 
> 1. for a proper closed ideal $I\unlhd A$, $A / I$ is Banach w.r.t. [[Seminorm|residue norm]].
> 2. $\prod_{i\in I}^{}A_{i}:=\{ (f_{i})_{i\in I}: \exists c>0, \|f\|_{i}\leq c, \forall i\in I \}$ is Banach w.r.t. $\|(f_{i})_{i\in I}\|:=\sup_{i\in I}\left\| f_{i} \right\|$.

> [!proof]+
> We have that:
> 1. By [[Seminorm|Proposition 2.3]] we have that $A / I$ is complete w.r.t. the residue norm as an additive group. Now, we only have to show that it is also a norm as a ring. Of course we have: $$\left\| 1+I \right\|\leq \left\| 1 \right\| =1 $$Now assume that $\left\| 1+I \right\|<1$. Then, there exists $m\in I$ s.t. $\left\| 1+m \right\|<1$. Then, by Proposition 1, $1-1-m=-m$ is a unit. This is a contradiction to the fact that $I$ is proper. Hence, $\left\| 1+I \right\|=1$. 
>    
>    Similarly, for $f,g\in A$, $\left\| fg+I \right\|\leq \left\| f+I \right\|\left\| g+I \right\|$. Indeed, let $m,m'\in I$ s.t. $\left\| f+m \right\|\leq \left\| f+I \right\|+\varepsilon$ and $\left\| g+m' \right\|\leq \left\| g+I \right\|+ \varepsilon$. Then, $$\begin{aligned}\left\| fg+I \right\|& \leq \left\| (f+m)(g+m') \right\| \\&\leq \left\| f+m \right\|\left\| g+m' \right\| \leq \left\| f+I \right\| \left\| g+I \right\| +\varepsilon(\left\| f+I \right\| +\left\| g+I \right\| )+\varepsilon^{2} \end{aligned}$$By taking $\varepsilon$ to zero, we have our statement. 
> 2. We have that $\left\| 0 \right\|=0$ and: $$\left\| f-g \right\| =\sup_{i\in I}\left\| f_{i}-g_{i} \right\| \leq \sup_{i\in I}\left\| f_{i} \right\| +\left\| g_{i} \right\| \leq \left\| f \right\| +\left\| g \right\| $$Further, $\left\| 1 \right\|=1$ and $\left\| fg \right\|\leq \left\| f \right\|\left\| g \right\|$ with the same argument as above. 

---
##### Examples
> [!h] Example 1
> We have that:
> 1. Any ring $A$ is a Banach ring with $\left| \cdot \right|_{0}:A \to \mathbb{R}_{\geq 0},f\mapsto \mathbb{1}_{f\neq 0}$.
> 2. $\mathbb{Z}$ is a Banach ring with absolute value $\left| \cdot \right|$.

> [!proof]-
> We have that:
> 1. Obviously $\left| \cdot \right|_{0}$ is a seminorm on $A$ as a ring. Further by definition it is a norm as well. Now, if we have a Cauchy sequence $(f_{n})_{n}$, by taking $\varepsilon = 1 /2$, there exists $n_{0}$ s.t. $\left| f_{m}-f_{n_{0}} \right|_{0}=0$, i.e. $f_{m}=f_{n_{0}}$ for all $m\geq n_{0}$. By taking $f:=f_{n_{0}}$, we have that $f_{n}\to f$.
> 2. $\left| \cdot \right|$ is a norm on $\mathbb{Z}$ as an abelian group. Further, it is a multiplicative norm. With the same arguments as above, for any Cauchy sequence $(n_{k})_{k}$ there exists $k_{0}$ s.t. $n_{\ell}=n_{k_{0}}$ for all $\ell\geq k_{0}$. Hence, the sequence converges. 
---
