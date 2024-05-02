#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be an abelian [[Locally Compact Topological Group|locally compact Hausdorff group]]. Then, $L^1(G)$ is a commutative [[C*-Algebra|involutive Banach algebra]]. For $f\in L^1(G)$ and $\chi\in \widehat{G}$, the ***Fourier transform*** $\widehat{f}$ is defined as: $$\widehat{f}(\chi):=\int_{G}^{} f(x)\overline{(x,\chi)} \, d\mu(x) $$where $\mu$ is some fixed [[Haar measure]] on $G$.
- **Related definition**: Let $\widehat{G}$ be the space of continuous characters $\chi:G \to \mathbb{T}$. 
- **Notation**: For $x\in G$ and $\gamma\in \widehat{G}$, we define $(x,\gamma):=\gamma(x)$. 
---
##### Properties
> [!lemma] Lemma 1
> $\widehat{G}$ can be equipped with a abelian group structure. More precisely,
> 1. for two characters $\chi_{1},\chi_{2}\in \widehat{G}$, $\chi_{1}\chi_{2}(x):=\chi_{1}(x)\chi_{2}(x)$ defines a mutiplication. 
> 2. $\widehat{e}\in \widehat{G}$, defined as $\widehat{e}\equiv 1$ defines a neutral element.
> 3. $(\gamma ^{-1})(x):=\gamma(x)^{-1}$ defines the inverse of $\gamma$.
---
> [!lemma] Lemma 2
> We have that:
> 1. $(x_{1}x_{2},\gamma)=(x_{1},\gamma)(x_{2},\gamma)$
> 2. $(x,\gamma_{1}\gamma_{2})=(x,\gamma_{1})(x,\gamma_{2})$
> 3. $(e,\gamma)=1$ and $(x,\widehat{e})=1$.
---
> [!lemma] Theorem 3
> The following map: $$\begin{array}{cccc} {}&{\widehat{G}}&\to&{\widehat{L^1(G)}}\\&{\chi} &\mapsto & {f\mapsto \widehat{f}(\chi)} \end{array}{}$$is a bijection.

> [!proof]+
> For $\chi\in \widehat{G}$, since $\left| \chi(x) \right|=1$ for all $x\in G$, we have that $f\to \widehat{f}(\chi)$ is in $L^1(G)^{*}$.
> 
> Let $f_{1},f_{2}\in L^1(G)$. Then, $$\begin{align}\widehat{(f_{1}*f_{2})}(\chi)&=\int_{G}^{} (f_{1}*f_{2})(x)\overline{(x,\chi)} \, d\mu(x)\\&=\int_{G}^{} f_{1}(xy)f_{2}(y^{-1}) \, d\mu(y)\overline{(x,\chi)}d\mu(x)\\&=\int_{G}^{} f_{2}(y ^{-1}) \int_{G}f_{1}(xy) \overline{(x,\chi)} \, d\mu(x) \, d\mu(y)  \end{align}$$
- **Remark**: This endows $\widehat{G}$ with two different structures: 1) that of an abelian group from Lemma 1, 2) a locally compact Hausdorff group inherited from $\widehat{L^1(G)}$.