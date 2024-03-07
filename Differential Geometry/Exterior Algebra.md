#Definition #DifferentialGeometry 
> [!definition]
> Let $V$ be a finite-dimensional $\mathbb{R}$-[[vector space]]. Then, 
> 1. $\Lambda^0(V^{*}):=\mathbb{R}$
> 3. $\Lambda^k(V^{*})$ is the vector space of all [[Multilinear k-Form|alternating multilinear $k$-forms]].
>  
>  With the above definition, the ***exterior algebra*** of $V^{*}$ is the graded vector space: $$\Lambda ^{*}(V^{*}):=\bigoplus_{{k\geq 0}}\Lambda^k(V^{*}) $$with the ***wedge vector product***: for $\alpha\in\Lambda^p(V^{*})$ and $\beta\in \Lambda^q(V^{*})$: $$(\alpha  \land\beta)(v_{1},\dots,v_{p+q}):= \frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})$$

- **Remark**: $\Lambda^1(V^{*})=V^{*}$.
- **Remark**: if $p=0$, then $\alpha \land \beta=a\beta$.
---
##### Properties
> [!lemma] Lemma 1
> We have that: $$(\alpha  \land\beta)(v_{1},\dots,v_{p+q})=\sum_{\sigma\in S_{p+q}}^{}\mathbb{1}_{\text{increasing}}\cdot \text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})$$where $\mathbb{1}_{\text{increasing}}=1$ if and only if $\sigma(1)<\dots<\sigma(p)$ and $\sigma(p+1)<\dots<\sigma(p+q)$.

> [!proof]-
> We have: $$\begin{align}(\alpha  \land\beta)(v_{1},\dots,v_{p+q})&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\sum_{\sigma\in S_{p}}^{}\sum_{\rho\in S_{q}}^{}\text{sgn}(\sigma)\text{sgn}(\rho)\alpha(v_{a_{\sigma(1)}},\dots,v_{a_{\sigma(p)}})\beta(v_{b_{\rho(1)}},\dots,v_{b_{\rho(q)}})\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\left( \sum_{\sigma\in S_{p}}^{}\text{sgn}(\sigma)\alpha(v_{a_{\sigma(1)}},\dots,v_{a_{\sigma(p)}}) \right)\left( \sum_{\rho\in S_{q}}^{}\text{sgn}(\rho)\beta(v_{b_{\rho(1)}},\dots,v_{b_{\rho(q)}}) \right)\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\left( \sum_{\sigma\in S_{p}}^{}\alpha(v_{a_{1}},\dots,v_{a_{p}}) \right)\left( \sum_{\rho\in S_{q}}^{}\beta(v_{b_{1}},\dots,v_{b_{q}}) \right)\\&= \sum_{A\subseteq[p+q]:\left| A \right| =p}^{} \alpha(v_{a_{1}},\dots,v_{a_{p}}) \beta(v_{b_{1}},\dots,v_{b_{q}}) \end{align}$$
---
> [!lemma] Proposition 2
> $\Lambda ^{*}(V^{*})$ is a $\mathbb{R}$-algebra that is associative and graded-commutative, i.e. $\beta \land\alpha=(-1)^{pq}(\alpha \land\beta)$.

> [!proof]-
> We have:
> 1. **Associativity**: Let $\alpha\in \Lambda^p(V^{*}),\beta\in \Lambda^q(V^{*}),\gamma\in \Lambda^r(V^{*})$. Then, $$\small\begin{align}&((\alpha \land\beta)\land \gamma)(v_{1},\dots,v_{p+q+r})\\&=\frac{1}{(p+q)!r!}\sum_{\sigma\in S_{p+q+r}}^{}\text{sgn}(\sigma)(\alpha \land\beta)(v_{\sigma(1)},\dots,v_{\sigma(p+q)})\gamma(v_{\sigma(p+q+1)},\dots,v_{\sigma(p+q+r)})\\&=\frac{1}{(p+q)!p!q!r!}\sum_{\sigma\in S_{p+q+r}}^{}\sum_{\tau\in S_{p+q}}^{}\text{sgn}(\sigma)\text{sgn}(\tau)\alpha(v_{\sigma \tau(1)},\dots,v_{\sigma \tau(p)})\beta(v_{\sigma \tau(p+1)},\dots,v_{\sigma \tau(p+q)}) \gamma(v_{\sigma(p+q+1)},\dots,v_{\sigma(p+q+r)})\\&=\frac{1}{(p+q)!p!q!r!}\sum_{\sigma\in S_{p+q+r}}^{}\sum_{\tau\in S_{p+q}}^{}\text{sgn}(\sigma \hat{\tau})\alpha(v_{\sigma \hat{\tau}(1)},\dots,v_{\sigma \hat{\tau}(p)})\beta(v_{\sigma \hat{\tau}(p+1)},\dots,v_{\sigma \hat{\tau}(p+q)}) \gamma(v_{\sigma \hat{\tau}(p+q+1)},\dots,v_{\sigma \hat{\tau}(p+q+r)})\\&=\frac{1}{(p+q)!p!q!r!}\sum_{\sigma\in S_{p+q+r}}^{}\sum_{\tau\in S_{p+q}}^{}\text{sgn}(\sigma )\alpha(v_{\sigma (1)},\dots,v_{\sigma (p)})\beta(v_{\sigma (p+1)},\dots,v_{\sigma (p+q)}) \gamma(v_{\sigma (p+q+1)},\dots,v_{\sigma (p+q+r)})\\&=\frac{1}{p!q!r!}\sum_{\sigma\in S_{p+q+r}}^{}\text{sgn}(\sigma )\alpha(v_{\sigma (1)},\dots,v_{\sigma (p)})\beta(v_{\sigma (p+1)},\dots,v_{\sigma (p+q)}) \gamma(v_{\sigma (p+q+1)},\dots,v_{\sigma (p+q+r)})\end{align}$$where $\hat{\tau}$ extends $\tau$ with identity. Therefore, by symmetry, $\Lambda^{*}(V^{*})$ is associative.
> 2. **Graded-commutativity**: Let $\alpha\in \Lambda^p(V^{*})$ and $\beta\in\Lambda^q(V^{*})$. Further, we define $\tau\in S_{p+q}$ where $\tau(i)=i+q\mod p+q$. Then, $$\begin{align}(\alpha \land\beta)(v_{1},\dots,v_{p+q})&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})\\&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma \tau)\alpha(v_{\sigma \tau(1)},\dots,v_{\sigma \tau(p)})\beta(v_{\sigma \tau(p+1)},\dots,v_{\sigma \tau(p+q)})\\&=(-1)^{pq}\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\beta(v_{\sigma(1)},\dots,v_{\sigma(q)})\alpha(v_{\sigma(q+1)},\dots,v_{\sigma(q+p)})\\&=(-1)^{pq}(\beta \land\alpha)(v_{1},\dots,v_{p+q})\end{align}$$
---
##### Example
> [!h] Example 1
> Let $V$ be a finite-dimensional $\mathbb{R}$-vector space. Further, let $\phi_{1},\dots,\phi_{k}\in V^{*}$ and $v_{1},\dots,v_{k}\in V$.  Then, $$(\phi_{1}\land\dots \land \phi_{k})(v_{1},\dots,v_{k})=\det[\phi_{i}(v_{j})]_{i,j}$$

> [!proof]+
> We carry an induction over $k$. 
> 1. If $k=1$, then $\phi_{1}(v_{1})=\det(\phi_{1}(v_{1}))$.