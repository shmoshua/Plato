#Definition #FunctionalAnalysis 
> [!definition]
> Let $(X,\Sigma,\mu)$ be a [[Measure Space|measure space]] and $\varphi\in$ [[Lp Space|$L^\infty(X)$]]. Then, $$\begin{array}{cccc} {M_{\varphi}:}&{L^p(X)}&\to&{L^p(X)}\\&{f} &\mapsto & {f \cdot   \varphi} \end{array}{}$$is called the ***multiplication operator*** with $\varphi$.

- **Remark**:  $M_{\varphi}$ is well-defined as, for $f\in L^p(X)$, $$ |f(x)\varphi(x)|=|f(x)|\cdot |\varphi(x)|\leq|f(x)|\cdot \|\varphi\|_{\infty}$$$\mu$-a.e. Therefore, $f\cdot\varphi\in L^p(X)$ where $\left\| f\cdot \varphi \right\|_{p}\leq \left\| f \right\|_{p}\left\| \varphi \right\|_{\infty}$.
---
##### Properties
> [!lemma] Proposition 1
> It holds that:
> $$\left\| M_{\varphi} \right\| =\left\| \varphi \right\| _{\infty}$$
> Therefore, $M_{\varphi}$ is a [[Bounded Linear Map|bounded linear map]].

> [!proof]-
> We have that:
> 1. $\leq$
>     $$\left\| M_{\varphi} \right\| =\sup_{\|f\|_{p}\leq 1}\left\| f\cdot \varphi \right\|_{p}\leq\|\varphi\|_{\infty}\sup_{\|f\|_{p}\leq 1}\left\| f\right\|_{p}=\|\varphi\|_{\infty} $$
> 2. $\geq$: We will construct $(f_{n})_n\subseteq L^p(X)$ with $\left\| f_{n} \right\|_{p}=1$ s.t. $$\left\| M_{\varphi}f_{n} \right\| _{p}=\left\| \varphi \cdot f_{n} \right\| _{p}\geq \left\| \varphi \right\| _{\infty}-\frac{1}{n}$$
> 	Let us define: $$E_{i}:=\left\{  x\in X:\left| \varphi(x) \right| >\left\| \varphi \right\|_{\infty}-\frac{1}{n}   \right\}$$and by definition, $\mu(E_{n})>0$. Further, we can assume that $\mu(E_{1})\le+\infty$ (otherwise start from the one where it is finite.)
> 	
> 	Now, set: $$f_{n}:=\left( \frac{1}{\mu(E_{n})} \right) ^{1/p}\chi_{E_{n}}$$Then, $\left\| f_{n} \right\|_{p}=1$ and $$\left\| M_{\varphi}f_{ n} \right\| _{p}= \left( \int_{X}^{} \left| \varphi\cdot f_{n}\right| ^p \, d\mu  \right) ^{1/p}>\left( \left\| \varphi \right\| _{\infty}-\frac{1}{n} \right) \left\| f_{n} \right\| _{p}= \left\| \varphi \right\| _{\infty}-\frac{1}{n} $$
> Therefore, $\left\| M_{\varphi} \right\|\geq \left\| \varphi \right\|_{\infty}$.
---