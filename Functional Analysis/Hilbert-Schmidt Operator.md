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

> [!proof]+
> We have that:
> 1. Oberseve that:$$\begin{align}\sum_{i=1}^{\infty } \sum_{j=1}^{\infty}\left| \braket{ Te_{i} , e_{j} }  \right| ^{2}=\sum_{i=1}^{\infty}\left\| Te_{i} \right\| ^{2}=\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} \left| \braket{ Te_{i},f_{j} }  \right| ^{2}=\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} \left| \braket{ e_{i},T^{*}f_{j} }  \right| ^{2}=\sum_{j=1}^{\infty}\left\| T^{*} f_{j} \right\| ^{2}\end{align}$$which is independent of the basis $\{ e_{i} \}_{i\geq 1}$.
> 2. Follows from 1.
> 3. for any $x \in \mathcal{H}$, $$\left\| (T+S)x \right\|^2\leq(\left\| Tx \right\| +\left\| Sx \right\| )^{2}\leq 2(\left\| Tx \right\| ^{2}+\left\| Sx \right\| ^{2}) $$Therefore, $T+S\in \text{HS}(\mathcal{H})$. Similarly, $\left\| \alpha Tx \right\|^{2}=\left| \alpha \right|^{2}\left\| Tx \right\|^{2}$. Hence, $\alpha T\in \text{HS}(\mathcal{H})$.
> 4. We have that: $$\left\| BT\right\| ^{2}_{2}=\sum_{i=1}^{\infty}\left\| BTe_{i} \right\| ^{2}\leq \left\| B \right\| ^{2}\sum_{i=1}^{\infty}\left\| Te_{i} \right\| ^{2}=\left\| B \right\| ^{2}\left\| T \right\| ^{2}_{2}$$Similarly, $\left\| TB \right\|_{2}=\left\| B^{*}T^{*} \right\|_{2}\leq \left\| B^{*} \right\|\left\| T^{*} \right\|_{2}= \left\| B\right\|\left\| T \right\|_{2}$.
> 5. Using Cauchy-Schwarz: $$\begin{align}\left\| Tx \right\| ^{2}&=\sum_{i=1}^{\infty}\left| \braket{ Tx , e_{i} }  \right| ^{2}\\&=\sum_{i=1}^{\infty}\left| \sum_{j=1}^{\infty}x_{j}\braket{ Te_{j} , e_{i} }  \right| ^{2}\\&\leq \sum_{i=1}^{\infty}\left( \sum_{j=1}^{\infty}\left| x_{j} \right| ^{2} \right) \left( \sum_{j=1}^{\infty}\left| \braket{ Te_{j} , e_{i} }  \right| ^{2} \right) \\&=\|x\|^{2}\|T\|^2_{2}\end{align}$$
> 6. Let $\{ e_{i} \}_{i\geq 1}$ be an orthonormal basis of $\mathcal{H}$. We define $T_{n}\in \mathcal{B}(\mathcal{H} ,\mathcal{H})$ by: 
> $$T_{n}e_{i}=\begin{cases}Te_{i}&1\leq i\leq n\\0&n<i\end{cases}$$ Then, $T_{n}$ has finite rank. In addition, $T-T_{n}$ is Hilbert-Schmidt with, $$\left\| T-T_{n} \right\| ^{2}\leq\left\| T-T_{n} \right\| ^{2}_{2}=\sum_{i=1}^{\infty}\left\| (T-T_{n})e_{i} \right\|^{2} =\sum_{i=n+1}^{\infty}\left\| Te_{i} \right\| ^{2}\xrightarrow {n\to \infty}0$$since $\sum_{i=1}^{\infty}\left\| Te_{i} \right\|^{2}<+\infty$. It follows that, $\left\| T-T_{n} \right\| \xrightarrow{n \to \infty}0$ and by [[Compact Operator|Proposition 1.3]], $T$ is compact.
---
> [!lemma] Proposition 2
> 
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
> Let $L^2(X,\mu)$ be a separable Hilbert space and $T_{K}\in \mathcal{B}(L^2(X,\mu))$ with $K\in L^2(X\times X,\mathbb{K},\mu \times \mu)$. Then, $T_{K}$ is Hilbert-Schmidt. 
> 
> Conversely, for any Hilbert-Schmidt operator $T\in \mathcal{B}(L^2(X,\mu))$ there exists $K\in L^2(X\times X,\mathbb{K},\mu \times \mu)$ s.t. $T=T_{K}$.

> [!proof]-
> We have: 
> 1. By Fubini's theorem, $K_{x}\in L^2(X,\mu)$. Therefore, $$(T_{K}e_{i})(x)=\int_{X}^{} f(y)K(x,y) \, d\mu(y)=\braket{ K_{x} , \overline{e}_{i} }  $$ By DCT, $$\sum_{i=1}^{\infty}\left\| T_{K}e_{i} \right\| ^{2}=\sum_{i=1}^{\infty}\int_{X}^{} \left| \braket{ K_{x} , \overline{e}_{i} }  \right|^{2}  \, d\mu(x)=\int_{X}^{} \sum_{i=1}^{\infty}\left| \braket{ K_{x} , \overline{e}_{i} }  \right|^{2}  \, d\mu(x)  $$As $\{ \overline{e}_{i} \}_{i}$ is also an ONB and $\left\| K_{x} \right\|^{2}=\sum_{i=1}^{\infty}\left| \braket{ K_{x} , \overline{e}_{i} } \right|^{2}$, we have: $$\sum_{i=1}^{\infty}\left\| T_{K}e_{i} \right\| ^{2}=\int_{X}^{} \left\| K_{x} \right\| ^{2} \, d\mu(x) =\int_{X}^{} \int_{X}^{} \left| K(x,y) \right|^{2}  \, d\mu(y)  \, d\mu(x)=\left\| K \right\| ^2 _{2}<+\infty$$
> 2. Let $T$ be a Hilbert-Schmidt operator on $L^2(X,\mu)$. We define, $$K(x,y)=\sum_{i,j=1}^{\infty}\braket{ Te_{i} , e_{j} } e_{j}(x)\overline{e_{i}(y)}$$We will show that $K\in L^2(X\times X,\mathbb{K},\mu \times \mu)$ by showing that $\{ E_{ij}:=e_{j}(x)\overline{e_{i}(y)} \}_{ij}$ is an ONB of $L^2(X\times X)$. 
> 	- **They are orthonormal**: 
> 		$$\begin{align}\braket{ E_{ij} , E_{pq} }&=\int_{X\times X}^{} e_{j}(x)\overline{e_{i}(y)}\overline{e_{q}(x)}e_{p}(y) \, d\mu \times \mu  \\&=\left( \int_{X}^{} e_{j}(x)\overline{e_{q}(x)} \, d\mu(x) \right)\left( \int_{X}^{} e_{p}(y)\overline{e_{i}(y)} \, d\mu(x) \right)\\&=\braket{ e_{j} , e_{q} } \braket{ e_{p} , e_{i} }\\&=\delta_{jq}\delta_{ip}  \end{align}$$
> 	- **They form a basis**:
> 		Assume $h\in L^2(X\times X)$ s.t. $\braket{ h , E_{ij} }=0$ for all $i,j$. Then, $$\begin{align}0=\int_{X\times X}h(x,y)e_{i}(y)\overline{e_{j}(x)} \, d\mu \times \mu &=\int_{X}^{} \left( \int_{X}^{} h_{x}(y)e_{i}(y) \, d\mu(y)  \right) \overline{e_{j}(x)} \, d\mu(x) \\&=\left\langle{ x\mapsto\int_{X}h_{x}e_{i}  \, d\mu(y)  , e_{j} }\right\rangle \end{align}$$Therefore, $\int_{X}h_{x}e_{i}  \, d\mu(y)=0$ for a.e. $x$. Let $$E_{i}:=\left\{  x\in X:\int_{X}^{} h_{x}e_{i}d\mu(y) \neq 0 \right\}$$Then $\mu(E_{i})=0$ and for $E:=\bigcup_{i=1}^{\infty}E_{i}$, $\mu(E)\leq \sum_{i=1}^{\infty}\mu(E_{i})=0$. Therefore, for each $x\in X \backslash E$, $h(x,y)=0$ $\mu \times \mu$.a.e. This means that: $$\begin{align}\int_{X\times X}^{} \left| h(x,y) \right| ^{2} \, d\mu \times \mu&=\int_{X}^{} \left( \int_{X}^{} \left| h(x,y) \right| ^{2} \, d\mu(y)  \right)  \, d\mu(x) \\&=\int_{X \backslash E}^{} \left( \int_{X}^{} \left| h(x,y) \right| ^{2} \, d\mu(y)  \right)  \, d\mu(x) \\&=0\end{align}$$This proves that $h=0$ in $L^2(X\times X)$.
> 		
> 	Therefore, we have that: $$\left\| K \right\| ^{2}_{L^2(X\times X)}=\sum_{i,j=1}^{\infty}\left| \braket{ Te_{i} , e_{j} }  \right| ^{2}<+\infty$$and $K\in L^2(X\times X)$. Then, for any $f\in L^2$, by DCT, $$\begin{align}(Tf)(x)&=T\left( \sum_{i=1}^{\infty}\braket{ f , e_{i} } e_{i} \right) (x)\\&=\sum_{i=1}^{\infty}\left( \int_{X}^{} f(y) \overline{e_{i}}(y) \, d\mu(y) \right)(Te_{i})(x)\\&=\int_{X}^{} f(y)\left( \sum_{i=1}^{\infty}(Te_{i})(x)\overline{e}_{i}(y) \right) \, d\mu(y)\\&=\int_{X}^{} f(y)K(x,y) \, d\mu(y) \\&=(T_{K}f)(x) \end{align} $$