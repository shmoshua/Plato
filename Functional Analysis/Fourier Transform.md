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
> We have:
> 1. **Showing that the map is well-defined**:
>    For $\chi\in \widehat{G}$, since $\left| \chi(x) \right|=1$ for all $x\in G$, we have that $f\to \widehat{f}(\chi)$ is in $L^1(G)^{*}$.
>    
>    Let $f_{1},f_{2}\in L^1(G)$. Then, $$\begin{align}\widehat{(f_{1}*f_{2})}(\chi)&=\int_{G}^{} (f_{1}*f_{2})(x)\overline{(x,\chi)} \, d\mu(x)\\&=\int_{G}^{} f_{1}(xy)f_{2}(y^{-1}) \, d\mu(y)\overline{(x,\chi)}d\mu(x)\\&=\int_{G}^{} f_{2}(y ^{-1}) \int_{G}f_{1}(xy) \overline{(x,\chi)} \, d\mu(x) \, d\mu(y) \\&=\int_{G}^{} f_{2}(y ^{-1}) \int_{G}f_{1}(x) \overline{(xy^{-1},\chi)} \, d\mu(x) \, d\mu(y)  \\&=\int_{G}^{} f_{2}(y ^{-1}) \overline{(y^{-1},\chi)}\, d\mu(y) \cdot \int_{G}f_{1}(x) \overline{(x,\chi)} \, d\mu(x)\\&=\widehat{f}_{1}(\chi)\cdot \widehat{f}_{2}(\chi)  \end{align}$$Therefore, $f\mapsto \widehat{f}(\chi)$ is an algebra homomorphism for all $\chi\in \widehat{G}$. Furthermore, if $\widehat{f}(\chi)=0$ for all $f\in L^1(G)$, then, $$\int_{G}^{} f(x)\overline{\chi(x)} \, d\mu(x)=0,\quad \forall f\in L^1(G) $$Therefore, $\chi(x)=0$ for almost every $x\in G$, which is a contradiction.
> 2. **Showing that the map is injective**:
>    Assume $\chi_{1},\chi_{2}\in \widehat{G}$ s.t. $\widehat{f}(\chi_{1})=\widehat{f}(\chi_{2})$ for all $f\in L^1(G)$. Then, $$\int_{G}^{} f(x)\overline{(\chi_{1}(x)-\chi_{2})(x)} \, d\mu(x)=0,\quad \forall f\in L^1(G) $$Therefore, $\chi_{1}(x)=\chi_{2}(x)$ for $\mu$-a.e. $x\in G$. Since $\{ x\in G:\chi_{1}(x)\neq \chi_{2}(x) \}$ is open and of $\mu$-measure zero, it is empty, i.e. $\chi_{1}=\chi_{2}$.
> 3. **Showing that the map is surjective**.
>    Let $\varphi\in \widehat{L^1(G)}$. Then, $\varphi\in L^1(G)^{*}\cong L^\infty(G)$. Therefore, there exists a unique $\Phi\in L^\infty(G)$ s.t. $$\varphi(f)=\int_{G}^{} f(x)\Phi(x) \, d\mu(x),\quad \forall f\in L^1(G) $$We have that: $\varphi(f_{1}*f_{2})=\varphi(f_{1})\varphi(f_{2})$ for all $f_{1},f_{2}\in L^1(G)$, where: $$\begin{align}\varphi(f_{1}*f_{2})&=\int_{G}^{} (f_{1}*f_{2})\Phi \, d\mu\\&=\int_{G}^{} \int_{G} f_{1}(xy)f_{2}(y^{-1})\Phi(x) \, d\mu(x)d\mu(y) \\&=\int_{G}^{} \int_{G}f_{1}(xy^{-1})f_{2}(y)\Phi(x) \, d\mu(x)d\mu(y)  \\&=\int_{G}^{} \varphi(\lambda(y)f_{1})f_{2}(y)\, d\mu(y)  \end{align}$$and $$\varphi(f_{1})\varphi(f_{2})=\int_{G}^{}  \varphi(f_{1})f_{2}(y)\Phi(y)\, d\mu(y) $$Therefore, for all $f_{1} L^1(G)$ and $\mu$-a.e. $y\in G$, $$\varphi(f_{1})\Phi(y)=\varphi(\lambda(y)f_{1})$$By [[Uniformly Continuous Function#^9177e0|Lemma 1.2]], $G\to L^1(G),y\mapsto \lambda(y)f_{1}$ is continuous and therefore, $y\mapsto \varphi(\lambda(y)f_{1})$ is continuous. Pick any $f_{0}\in L^1(G)$ s.t.. $\varphi(f_{0})\neq 0$. Then, $$\Phi(y)=\frac{\varphi(\lambda(y)f_{0})}{\varphi(f_{0})},\quad \mu \text{-a.e. }y\in G$$Replacing $\Phi$ by the RHS, we assume that $\Phi$ is continuous. Therefore, we have that: $$\Phi(y)\varphi(f_{1})=\varphi(\lambda(y)f_{1}),\quad \forall f_{1}\in L^1(G), y\in G$$Then, $$\Phi(y_{1}y_{2})\varphi(f_{1})=\varphi(\lambda(y_{1}y_{2})f_{1})=\varphi(\lambda(y_{1})\lambda(y_{2})f_{1})=\Phi(y_{1})\varphi(\lambda(y_{2})f_{1})=\Phi(y_{1})\Phi(y_{2})\varphi(f_{2})$$and $\Phi(y_{1}y_{2})=\Phi(y_{1})\Phi(y_{2})$. Then, $\Phi:G\to \mathbb{C}$ is continuous bounded and $\Phi(y_{1}y_{2})=\Phi(y_{1})\Phi(y_{2})$ for all $y_{1},y_{2}\in G$. Therefore, we have: $\Phi(G)\subseteq \mathbb{C}^\times$. Otherwise, if $\Phi(x)=0$, then $$\Phi(xy)=\Phi(x)\Phi(y)=0$$for all $y\in G$ and $\Phi \equiv 0$, which is a contradiction.
>    
>    If there exists $y\in G$ with $\left| \Phi(y) \right|\neq 1$, then 
- **Remark**: This endows $\widehat{G}$ with two different structures: 1) that of an abelian group from Lemma 1, 2) a locally compact Hausdorff group inherited from $\widehat{L^1(G)}$.