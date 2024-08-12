#Definition #Example #FunctionalAnalysis 

> [!definition]
> Let $(X,\Sigma,\mu)$ be a [[Positive Measure|$\sigma$-finite]] measure space. Then, an ***integral operator***  is defined as 
> $$\begin{array}{cccc} {T}&{:L^2(X\times X,\mathbb{K},\mu \times \mu)}&\to&{\mathcal{B}(L^2(X,\mu))}\\&{K} &\mapsto & {T_{K}} \end{array}{}$$such that:
> 
> $$(T_{K}f)(x)=\int_{X}^{} f(y)K(x,y) \, d\mu(y)=\braket{ K_{x} , \overline{f} } $$with $K_{x}=K(x,\cdot)$.
---
##### Properties

> [!lemma] Proposition 1
> For all $f\in L^2(X)$, 
> 1. $T_{K}f$ is well-defined for all $f\in L^2(X)$
> 2. $T_{K}$ is bounded.
> 3. $T_{K}^{*}=T_{K^{*}}$ where $K^{*}(x,y)=\overline{K(y,x)}$
> 4. $T_{K}$ is [[Adjoint Linear Map|self-adjoint]] if and only if for all $x,y\in X$: $K(x,y)=\overline{K(y,x)}$.

> [!proof]-
> As $K\in L^2(X\times X,\mathbb{K},\mu \times \mu)$, we have:$$\int _{X}\int _{X}\left| K(x,y) \right| ^2 \, d\mu(x)  \, d\mu(y)<+\infty $$and by Fubini's theorem, we have for $\mu$-a.e. $x\in X$:$$\int _{X}\left| K(x,y) \right| ^2 \, d\mu(y) <+\infty$$This means, $K_{x}:=K(x,\cdot)$ is in $L^2(X,\mu)$ and thus for all $f\in L^2(X,\mu)$: $$(T_{K}f)(x):=\int _{X}f(y)K(x,y) \, d\mu(y) $$is well-defined for $\mu$-a.e. $x\in X$. Then, $(T_{K}f)(x)=\braket{ K_{x} ,\overline{f}  }$ and:
> $$\begin{align}\left\| T_{K}f \right\| ^2_{2}&=\int _{X} \left| \braket{ K_{x} , \overline{f} }  \right|^{2} \, d\mu(x) \\&\leq \int _{X}\left\| K_{x} \right\| ^2_{2}\left\| f \right\| ^2_{2} \, d\mu(x) \\&=\|f\|_{2}^2\int_{X}^{}\left( \int_{X}^{} \left| K(x,y) \right|^{2}  \, d\mu(y)  \right)  \, d\mu(x)\\&= \left\| K \right\| ^2_{2}\cdot \left\| f \right\| ^2_{2}\end{align}$$which shows that $T_{K}$ defines a bounded operator on $L^2(X,\mu)$ with norm: $$\left\| T_{K} \right\| \leq \left\| K \right\| _{2}$$
> The adjoint of $T_{K}$ would be:$$\begin{align}\braket{ T_{K}f , g } &=\int _{X}\overline{g(x)}(T_{K} f)(x)\, d\mu(x)\\&=\int _{X}\overline{g(x)}\int _{X}f(y)K(x,y) \, d\mu(y)  \, d\mu(x) \\&=\int _{X}f(y)\overline{\int _{X} g(x)\overline{K(x,y)}\, d\mu(x) } \, d\mu(y) \\&=\braket{ f , T_{K^*}g } \end{align}$$where $K^*(x,y)=\overline{K(y,x)}$.
---
> [!lemma] Proposition 2
> If $L^2(X,\mu)$ is separable, $T_{K}$ is a [[Hilbert-Schmidt Operator|Hilbert-Schmidt operator]] with norm $\left\| T_{K} \right\|_{2}=\left\| K \right\|_{L^2}$ for all $K$.

>[!proof]-
> Let $\{ e_{i} \}_{i\geq 1}$ be the orthonormal basis of $L^{2}(X)$. $$\begin{align}\left\| T_{K} \right\| ^{2}_{2}&=\sum_{i=1}^{\infty}\left\| T_{K}e_{i} \right\| ^{2}_{2}\\&=\sum_{i=1}^{\infty}\int_{X}^{}\left| T_{K}e_{i} \right|^{2}   \, d\mu\\&=\sum_{i=1}^{\infty}\int_{X}^{} \left| \braket{ K_{x} , \overline{e}_{i} }  \right|^{2}  \, d\mu(x)  \\&=\sum_{i=1}^{\infty}\int_{X}^{} \left| \overline{\braket{ K_{x} , \overline{e}_{i} }}  \right|^{2}  \, d\mu(x)  \\&=\int_{X}^{} \sum_{i=1}^{\infty}\left| {\braket{ \overline{K_{x}} , {e}_{i} } } \right|^{2}  \, d\mu(x) \\&=\int_{X}^{} \left\| \overline{K_{x} }\right\|_{2}^2  \, dx  \\&=\int_{X}^{} \left\|{K_{x} }\right\|_{2}^2  \, dx\\&=\int_{X}^{} \int_{X}^{} \left| K(x,y) \right| ^{2} \, d\mu(y)  \, d\mu(x) \\&=\left\| K \right\| _{2}^2  \end{align}$$
---
