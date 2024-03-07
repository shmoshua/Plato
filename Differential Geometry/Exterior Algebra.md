#Definition #DifferentialGeometry 
> [!definition]
> Let $V$ be a finite-dimensional $\mathbb{R}$-[[vector space]]. Then, 
> 1. $\Lambda^0(V^{*}):=\mathbb{R}$
> 3. $\Lambda^k(V^{*})$ is the vector space of all [[Multilinear k-Form|alternating multilinear $k$-forms]].
>  
>  With the above definition, the ***exterior algebra*** of $V^{*}$ is the graded vector space: $$\Lambda ^{*}(V^{*}):=\bigoplus_{{k\geq 0}}\Lambda^k(V^{*}) $$with the ***wedge vector product***: for $\alpha\in\Lambda^p(V^{*})$ and $\beta\in \Lambda^q(V^{*})$: $$(\alpha  \land\beta)(v_{1},\dots,v_{p+q}):= \frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})$$

- **Remark**: $\Lambda^1(V^{*})=V^{*}$.
---
##### Properties
> [!lemma] Lemma 1
> We have that: $$(\alpha  \land\beta)(v_{1},\dots,v_{p+q})=\sum_{\sigma\in S_{p+q}}^{}\mathbb{1}_{\text{increasing}}\cdot \text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})$$where $\mathbb{1}_{\text{increasing}}=1$ if and only if $\sigma(1)<\dots<\sigma(p)$ and $\sigma(p+1)<\dots<\sigma(p+q)$.

> [!proof]-
> We have: $$\begin{align}(\alpha  \land\beta)(v_{1},\dots,v_{p+q})&=\frac{1}{p!q!}\sum_{\sigma\in S_{p+q}}^{}\text{sgn}(\sigma)\alpha(v_{\sigma(1)},\dots,v_{\sigma(p)})\beta(v_{\sigma(p+1)},\dots,v_{\sigma(p+q)})\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\sum_{\sigma\in S_{p}}^{}\sum_{\rho\in S_{q}}^{}\text{sgn}(\sigma)\text{sgn}(\rho)\alpha(v_{a_{\sigma(1)}},\dots,v_{a_{\sigma(p)}})\beta(v_{b_{\rho(1)}},\dots,v_{b_{\rho(q)}})\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\left( \sum_{\sigma\in S_{p}}^{}\text{sgn}(\sigma)\alpha(v_{a_{\sigma(1)}},\dots,v_{a_{\sigma(p)}}) \right)\left( \sum_{\rho\in S_{q}}^{}\text{sgn}(\rho)\beta(v_{b_{\rho(1)}},\dots,v_{b_{\rho(q)}}) \right)\\&= \frac{1}{p!q!}\sum_{A\subseteq[p+q]:\left| A \right| =p}^{}\left( \sum_{\sigma\in S_{p}}^{}\alpha(v_{a_{1}},\dots,v_{a_{p}}) \right)\left( \sum_{\rho\in S_{q}}^{}\beta(v_{b_{1}},\dots,v_{b_{q}}) \right)\\&= \sum_{A\subseteq[p+q]:\left| A \right| =p}^{} \alpha(v_{a_{1}},\dots,v_{a_{p}}) \beta(v_{b_{1}},\dots,v_{b_{q}}) \end{align}$$
---
> [!lemma] Proposition 2
> $\Lambda ^{*}(V^{*})$ is an associative, graded commutative $\mathbb{R}$-algebra.