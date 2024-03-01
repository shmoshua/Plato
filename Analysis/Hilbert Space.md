#Definition #FunctionalAnalysis 
> [!definition]
> An [[Inner Product Space|inner product space]] is a ***Hilbert space***, if the induced [[Analysis/Normed Space|normed space]] is [[Banach Space|Banach]].
---
##### Properties
> [!lemma] Theorem 1
> Let $\mathcal{H}$ be a [[separable]] Hilbert space with $\{ e_{k} \}$ as orthonormal basis. Then:
> 1. **Bessel's inequality**: for all $x\in \mathcal{H}$, $$\sum_{k=0}^{\infty}\left| \braket{ x , e_{k} }  \right| ^{2}\leq\|x\|^2$$
> 2. For all $x\in \mathcal{H}$, $\sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k}$ converges to  $\overline{x}\in\mathcal{H}$.
> 3. $\left\| \overline{x} \right\|^{2}=\sum_{k=0}^{\infty}\left| \braket{ x , e_{k} } \right|^{2}\leq \|x\|^{2}$
> 4. $x-\overline{x}$ is orthogonal to $\overline{\braket{ \{ e_{k} \}_{k}  }}$
> 5. **Parseval's identity**: The equality in Bessel's inequality holds if and only if $x=\overline{x}$.

> [!proof]+
---
> [!lemma] Theorem 1
> For a Hilbert space $\mathcal{H}$ and a closed convex subset $C\subseteq \mathcal{H}$. Then, for all $v\in \mathcal{H}$, there exists a unique $\rho_{C}(v)\in C$ s.t.
> $$\|v-\rho_{C}(v)\|=d(v,C)$$

> [!proof]-
> By translating the situation by $-v$, we may assume that $v=0$. Then, let:
> - $d:=d(0,C)$ and
> - $(v_{n})_{n\geq 1}\subseteq C$ s.t. $d^{2} \leq \left\| v_{n} \right\|^{2}< d^{2}+\frac{1}{n}$.
>   
> Then, we have: $$\left\| \frac{v_{n}+v_{m}}{2} \right\|^{2}+\left\| \frac{v_{n}-v_{m}}{2} \right\|^{2}=\frac{1}{2} (\| v_{n} \| ^{2}+\|  v_{m} \| ^{2})  <d^{2}+\frac{1}{2} \left( \frac{1}{n}+\frac{1}{m} \right)$$ Then, as $\frac{v_{n}+v_{m}}{2}\in C$, we have $\left\| \frac{v_{n}+v_{m}}{2} \right\|^{2}\ge d^{2}$ and $$\left\| \frac{v_{n}-v_{m}}{2} \right\|^{2}<\frac{1}{2} \left( \frac{1}{n}+\frac{1}{m} \right)$$ which implies that $(v_{n})_{n}$ is a Cauchy sequence. Since $\mathcal{H}$ is a Hilbert space, $x:=\lim_{ n \to \infty }v_{n}\in C$ exists and clearly, $d(0,C)=\|x\|$. Uniqueness follows directly from the strict convexity property.

---
> [!lemma] Proposition 2
> Let $V \subseteq \mathcal{H}$ be a closed subspace of a Hilbert space.  Then, $\mathcal{H}$ is the orthogonal direct sum of $V$ and $V^{\bot}$, i.e.: $$\mathcal{H}= V \oplus V^{\bot}$$
> Further, every $u\in \mathcal{H}$ can be uniquely written as: $$u=v+v^{\bot}$$for $v\in V,v^{\bot}\in V^{\bot}$ and $\|u\|^{2}=\|v\|^{2}+\|v^{\bot}\|^2$

>[!proof]-
>Since $V$ is closed and convex, we have the nearest point projection: $$P_{V}:\mathcal{H} \to V$$from Theorem 1.  Then, for all $u\in V$, the polynomial $$\begin{array}{cccc} {}&{\mathbb{R}}&\to&{\mathbb{R}}\\&{t} &\mapsto & {\left\| v-(P_{V}(v)-tu) \right\| ^{2}} \end{array}{}$$attains a minimum at $t=0$. Then, then in the derivative, we should have: $$\text{Re}\braket{ v-P_{V}(v) , u } =0$$for all $u\in V$. Now, for $u\in V$, let $\alpha\in \mathbb{C}$ s.t. $$\left| \braket{ v-P_{V}(v) , u }  \right| =\alpha \cdot \braket{ v-P_{V}(v) , u }=\text{Re} \braket{ v-P_{V} (v), \overline{\alpha}u }=0  $$Therefore, $v-P_{V}(v)\in V^{\bot}$. It follows that: $$\|v\|^2=\left\| P_{V}(v)+(v-P_{V}(v)) \right\|^{2}=\left\| P_{V}(v) \right\| ^2+\left\| v-P_{V}(v) \right\| ^2$$
---
> [!lemma] Theorem 3 (Riesz Representation Theorem)
> For a Hilbert space $\mathcal{H}$, the Riesz map, defined as: $$\begin{array}{cccc} {i:}&{\mathcal{H}}&\to&{\mathcal{H}^{*}}\\&{u} &\mapsto & {i(u)} \end{array}{}$$s.t. $i(u)(v):=\braket{ v , u }$ is an anti-linear, norm-preserving bijection.

> [!proof]-
> Anti-linearity is clear. For the norm, we have: $$\left\| i(u) \right\| =\sup_{\|v\|\leq 1}\left| \braket{ v,u }  \right| \leq \|u\| $$Since, $i(u)\left( \frac{u}{\|u\|} \right)=\|u\|$, we have $\|i(u)\|=\|u\|$, i.e. $i$ is norm-preserving.
> 
> Now, let $\lambda\in \mathcal{H}^{*}$ s.t. $\lambda\neq 0$. Then, $\text{ker}\lambda$ is a closed, co-dimension 1 subspace of $\mathcal{H}$. By Proposition 2, we have: $$\text{ker}\lambda \oplus (\text{ker}\lambda)^{\bot}=\mathcal{H}$$Let $(\text{ker}\lambda)^{\bot}=\mathbb{K}\cdot e$ for some $\|e\|=1$. Further, let $u:=\overline{\lambda(e)}\cdot e$. Then, for any $v\in \mathcal{H}$, we have $v=v_{1} +r \cdot e$. for some $r\in \mathbb{K}$, $v_{1}\in \text{ker}\lambda$ and:$$i(u)(v)=\braket{ v , u } =\braket{ re ,  \overline{\lambda(e)}e}=r\lambda(e)=\lambda(re)=\lambda(v) $$which shows that $i(u)=\lambda$.
---
> [!lemma] Proposition 4
> Let $\mathcal{H}$ be a [[Separable Space|separable]] $\infty$-dimensional Hilbert space and $\{ e_{n} \}_{n\geq 1}$ an orthonormal basis. Then, $e_{n}\to 0$ weakly as $n\to \infty$.


> [!proof]-
> Recall that every $f\in \mathcal{H}^{*}$ is given by $f(v)=\braket{ v , x }$ for some $x\in \mathcal{H}$ from Riesz Representation theorem. Let $x=\sum_{n=1}^{\infty}\braket{ x , e_{n} }e_{n}$, with $\|x\|^{2}=\sum_{n=1}^{\infty}\left| \braket{ x , e_{n} } \right|^{2}$. Then, $$f(e_{n})=\braket{ e_{n} , x } $$Since $\|x\|^{2}=\sum_{n=1}^{\infty}|\braket{ e_{n} , x } |^{2}$, we have that $\lim_{ n \to \infty }\braket{ e_{n} , x } =0$. This shows that $f(e_{n})\to 0$. From [[Weak Topology|Lemma 2]], $e_{n}\to{0}$ in weak-topology.
- **Corollary**: $B_{\leq 1}^\mathcal{H}(0)$ is weakly closed, $S_{1}^\mathcal{H}(0)=\{ v\in \mathcal{H}:\|v\|=1 \}$ is not weakly closed.
---
