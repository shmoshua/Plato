#Definition #Example #FunctionalAnalysis 

> [!definition]
> Let $\mathcal{H}$ be a [[Separable Space|separable]] [[Hilbert Space| Hilbert space]] with an [[Hilbert Basis|Hilbert basis]] $\{ e_{i}\}_{i\geq 1}$. 
> 1. An operator $T\in \mathcal{B}(\mathcal{H})$ is called ***Hilbert-Schmidt*** if: $$\left\| T \right\| _{2}^{2}:=\sum_{i,j=1}^{\infty}\left| \braket{ Te_{j} , e_{i} }  \right| ^{2}=\sum_{i=1}^{\infty}\left\| Te_{i} \right\| ^2<+\infty$$

 - **Related definition**: $\left\| T \right\|_{2}$ is the ***Hilbert-Schmidt norm*** of $T$.

---
##### Properties
> [!lemma] Proposition 1 (Basic Properties of HS Operator)
> Let $\text{HS}(\mathcal{H})$ denote the space of Hilbert-Schmidt operators. For $T\in \text{HS}(\mathcal{H})$ and $B\in \mathcal{B}(\mathcal{H})$, 
> 1. $\left\| T \right\|_{2}$ is independent of the choice of the Hilbert basis.
> 2. $T^{*}$ is also Hilbert-Schmidt with $\left\| T^{*} \right\|_{2}=\left\| T \right\|_{2}$.
> 3. $\text{HS}(\mathcal{H})$ is a vector space.
> 4. $\text{HS}(\mathcal{H})\unlhd \mathcal{B}(\mathcal{H})$, i.e. $\left\| BT \right\|_{2}\leq \left\| B \right\|\left\| T \right\|_{2}$ and $\left\| TB \right\|_{2}\leq \left\| B \right\|\left\| T \right\|_{2}$
> 5. $\left\| T \right\|\leq \left\| T \right\|_{2}$
> 6. $T\in \mathcal{K}(\mathcal{H})$
> 

> [!proof]-
> We have that:
> 1. Oberseve that:$$\begin{align}\sum_{i=1}^{\infty } \sum_{j=1}^{\infty}\left| \braket{ Te_{i} , e_{j} }  \right| ^{2}=\sum_{i=1}^{\infty}\left\| Te_{i} \right\| ^{2}=\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} \left| \braket{ Te_{i},f_{j} }  \right| ^{2}=\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} \left| \braket{ e_{i},T^{*}f_{j} }  \right| ^{2}=\sum_{j=1}^{\infty}\left\| T^{*} f_{j} \right\| ^{2}\end{align}$$which is independent of the basis $\{ e_{i} \}_{i\geq 1}$.
> 2. Follows from 1.
> 3. for any $x \in \mathcal{H}$, $$\left\| (T+S)x \right\|^2\leq(\left\| Tx \right\| +\left\| Sx \right\| )^{2}\leq 2(\left\| Tx \right\| ^{2}+\left\| Sx \right\| ^{2}) $$Therefore, $T+S\in \text{HS}(\mathcal{H})$. Similarly, $\left\| \alpha Tx \right\|^{2}=\left| \alpha \right|^{2}\left\| Tx \right\|^{2}$. Hence, $\alpha T\in \text{HS}(\mathcal{H})$.
> 4. We have that: $$\left\| BT\right\| ^{2}_{2}=\sum_{i=1}^{\infty}\left\| BTe_{i} \right\| ^{2}\leq \left\| B \right\| ^{2}\sum_{i=1}^{\infty}\left\| Te_{i} \right\| ^{2}=\left\| B \right\| ^{2}\left\| T \right\| ^{2}_{2}$$Similarly, $\left\| TB \right\|_{2}=\left\| B^{*}T^{*} \right\|_{2}\leq \left\| B^{*} \right\|\left\| T^{*} \right\|_{2}= \left\| B\right\|\left\| T \right\|_{2}$.
> 5. Using Cauchy-Schwarz: $$\begin{align}\left\| Tx \right\| ^{2}&=\sum_{i=1}^{\infty}\left| \braket{ Tx , e_{i} }  \right| ^{2}\\&=\sum_{i=1}^{\infty}\left| \sum_{j=1}^{\infty}x_{j}\braket{ Te_{j} , e_{i} }  \right| ^{2}\\&\leq \sum_{i=1}^{\infty}\left( \sum_{j=1}^{\infty}\left| x_{j} \right| ^{2} \right) \left( \sum_{j=1}^{\infty}\left| \braket{ Te_{j} , e_{i} }  \right| ^{2} \right) \\&=\|x\|^{2}\|T\|^2_{2}\end{align}$$
> 6. Let $\{ e_{i} \}_{i\geq 1}$ be an orthonormal basis of $\mathcal{H}$. We define $T_{n}\in \mathcal{B}(\mathcal{H} ,\mathcal{H})$ by: 
> $$T_{n}e_{i}=\begin{cases}Te_{i}&1\leq i\leq n\\0&n<i\end{cases}$$ Then, $T_{n}$ has finite rank. In addition, $T-T_{n}$ is Hilbert-Schmidt with, $$\left\| T-T_{n} \right\| ^{2}\leq\left\| T-T_{n} \right\| ^{2}_{2}=\sum_{i=1}^{\infty}\left\| (T-T_{n})e_{i} \right\|^{2} =\sum_{i=n+1}^{\infty}\left\| Te_{i} \right\| ^{2}\xrightarrow {n\to \infty}0$$since $\sum_{i=1}^{\infty}\left\| Te_{i} \right\|^{2}<+\infty$. It follows that, $\left\| T-T_{n} \right\| \xrightarrow{n \to \infty}0$ and by [[Compact Operator|Proposition 1.3]], $T$ is compact.

---
> [!lemma] Lemma 2
> If $T\in \mathcal{B}(\mathcal{H})$ is Hilbert-Schmidt and self-adjoint, then the [[Compact, Self-adjoint Operators|spectral theorem]] applies and: $$\left\| T \right\|_{2}=\sum_{n=1}^{\infty}\lambda_{n}^{2} $$

> [!proof]-
> We have: $$\|T\|_{2}=\sum_{i,j=1}^{\infty}\left| \braket{ Te_{j} , e_{i} }  \right| ^{2}=\sum_{i,j=1}^{\infty}| \lambda_{j}|^{2}\left| \braket{e_{j} , e_{i} }  \right| ^{2}=\sum_{i=1}^{\infty}\lambda_{i}^{2}$$
---
> [!lemma] Proposition 3
> For a separable Hilbert space $\mathcal{H}$, the space $\text{HS}(\mathcal{H})$ of all Hilbert-Schmidt operators  on $\mathcal{H}$ forms a Hilbert space w.r.t. the Hilbert-Schmidt norm.

> [!proof]-
> We show that:
> 1. **$\text{HS}(\mathcal{H})$ is an inner product space**: We show the parallelogram identity. For $T_{1},T_{2}\in \text{HS}(\mathcal{H})$, $$\begin{align}\left\| T_{1}+T_{2} \right\| ^2_{2}-\left\| T_{1}-T_{2} \right\| ^2_{2}&=\sum_{i=1}^{\infty}\left\| T_{1}e_{i}+T_{2}e_{i} \right\| ^{2}-\left\| T_{1}e_{i}-T_{2}e_{i} \right\| ^{2}\\&=2\sum_{i=1}^{\infty}\left\| T_{1}e_{i} \right\| ^{2}+\left\| T_{2}e_{i} \right\| ^{2}\\&=2(\left\| T_{1} \right\| ^2_{2}+\left\| T_{2} \right\| ^2_{2})\end{align}$$
> 
> Now we show that $\text{HS}(\mathcal{H})$ is Banach. Let $(T_{n})_{n}$ be a Cauchy sequence in $\text{HS}(\mathcal{H})$. As $\|\cdot\|\leq\|\cdot\|_{2}$, $(T_{n})_{n}$ is a Cauchy sequence w.r.t the operator norm and converges to $T\in \mathcal{B}(\mathcal{H})$. 
> 1. **Showing $T_{n}\to T$ in HS**: Let $\varepsilon>0$. Then, there exists $n_{0}:=n_{0}(\varepsilon)>0$ s.t. $$\sum_{i=1}^{N}\left\| T_{m}e_{i}-T_{k}e_{i} \right\| ^{2}\leq\left\| T_{m}-T_{k} \right\| _{\text{2}}^2<\varepsilon,\quad \forall m,k\geq n_{0}$$By letting $k\to \infty$, $$\sum_{i=1}^{N}\left\| T_{m}e_{i}-Te_{i} \right\|^{2}\leq\varepsilon$$Therefore, $$\left\| T_{m}-T \right\| ^{2}_{2}=\sum_{i=1}^{\infty}\left\| T_{m}e_{i}-Te_{i} \right\| ^{2}\leq \varepsilon$$This shows that $T_{m}\to T$ in HS-norm.
> 1. **Showing $T\in \text{HS}(\mathcal{H})$**: $\left\| T \right\|_{2}\leq \left\| T-T_{m} \right\|_{2}+\left\| T_{m} \right\|_{2}$.
> 	
---
> [!lemma] Proposition 4
> Let $\mathcal{H}:=L^2(X,\mu)$ be $\sigma$-finite. Then, for $T\in \mathcal{B}(\mathcal{H})$, we have that:
> 1. $T\in \text{HS}(\mathcal{H})$ if and only if there exists $K_{T}\in L^2(X\times X,\mu \otimes \mu)$ s.t. $$(Tf)(x)=\int_{X}^{} K_{T}(x,y)f(y) \, d\mu(y) ,\quad \forall f\in L^2(X,\mu)$$
> 2. In this case, $\left\| T \right\|_{2}=\left\| K_{T} \right\|_{L^2(X\times X)}$, i.e. there exists an isometric isomorphism between $\text{HS}(L^2(X,\mu))$ and $L^2(X\times X,\mu \otimes \mu)$.

> [!proof]-
> We have: 
> 1. Let $T\in \text{HS}(\mathcal{H})$. Then, $T$ is compact by Proposition 1.6 and we define, $$K_{T}(x,y)=\sum_{i,j=1}^{\infty}\braket{ Te_{i} , e_{j} } e_{j}(x)\overline{e_{i}(y)}$$From [[Hilbert Basis|Hilbert Basis Theorem 4]], we have that $\{ E_{ij}:=e_{j}(x)\overline{e_{i}(y)} \}_{i,j}$ is a Hilbert basis of $L^2(X\times X)$ and: $$\left\| K_{T} \right\|^2_{L^2(X\times X)}=\sum_{i,j=1}^{\infty}\left| \braket{ Te_{i} ,  e_{j}}  \right|^{2}=\left\| T \right\| _{2}^{2}<+\infty  $$
>    Then, for any $f\in L^2(X,\mu)$, by DCT, $$\begin{align}(Tf)(x)&=T\left( \sum_{i=1}^{\infty}\braket{ f , e_{i} } e_{i} \right) (x)\\&=\sum_{i=1}^{\infty}\left( \int_{X}^{} f(y) \overline{e_{i}}(y) \, d\mu(y) \right)(Te_{i})(x)\\&=\int_{X}^{} f(y)\left( \sum_{i=1}^{\infty}(Te_{i})(x)\overline{e}_{i}(y) \right) \, d\mu(y)\\&=\int_{X}^{} f(y)K_{T}(x,y) \, d\mu(y) \end{align} $$
> 
> 1. By Fubini's theorem, $K_{x}\in L^2(X,\mu)$. Therefore, consider $T_{K}\in \mathcal{B}(\mathcal{H})$ given as:$$ (T_{K}f)(x)=\int_{X}^{} K(x,y)f(y) \, d\mu(y) $$Then, $(T_{K}e_{i})(x)=\int_{X}^{}K(x,y) e_{i}(y)\, d\mu(y)=\braket{ K_{x} , \overline{e}_{i} }$. By DCT, $$\left\| T_{K} \right\|^2_{2}= \sum_{i=1}^{\infty}\left\| T_{K}e_{i} \right\| ^{2}=\sum_{i=1}^{\infty}\int_{X}^{} \left| \braket{ K_{x} , \overline{e}_{i} }  \right|^{2}  \, d\mu(x)=\int_{X}^{} \sum_{i=1}^{\infty}\left| \braket{ K_{x} , \overline{e}_{i} }  \right|^{2}  \, d\mu(x)  $$As $\{ \overline{e}_{i} \}_{i}$ is also an ONB and $\left\| K_{x} \right\|^{2}=\sum_{i=1}^{\infty}\left| \braket{ K_{x} , \overline{e}_{i} } \right|^{2}$, we have: $$\left\| T_{K} \right\| _{2}^2=\int_{X}^{} \left\| K_{x} \right\| ^{2} \, d\mu(x) =\int_{X}^{} \int_{X}^{} \left| K(x,y) \right|^{2}  \, d\mu(y)  \, d\mu(x)=\left\| K \right\| ^2 _{L^2(X\times X)}<+\infty$$

---