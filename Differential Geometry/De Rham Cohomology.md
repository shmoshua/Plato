#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $d_{k}:\Omega^k(M)\to\Omega^{k+1}(M)$ the [[exterior derivative]] operator. Then, the ***$k$-th de Rham cohomology of $M$*** is the quotient vector space: $$\text{H}_{\text{dR}}^k(M):=\text{ker }d_{k}  /\text{im }d_{k-1}$$
- **Related definition**: The elements of $\text{Im }d_{k-1}$ are called the ***exact forms*** and the elements of $\text{ker }d_{k}$ are called ***closed forms***.
- **Related definition**: $\omega\in \Omega^m(M)$ with $\int_{M}^{} \omega =1$ is said to represent the ***fundamental class of $M$***.
- **Remark**: This is well defined as $\text{im } d_{k-1}\subseteq \text{ker }d_{k}$ given by [[Exterior Derivative|Theorem 3.3]].
- **Remark**: $\text{H}^0_{\text{dR}}(M)=\text{ker }d_{0}\cong\mathbb{R}^{\pi_{0}(M)}$ where $\pi_{0}(M)$ is the number of connected components in $M$.
- **Remark**: For smooth manifolds $M,N$ and a smooth map $F:N\to M$: $$\begin{CD} 0 @>>> \Omega^0(M)@>d_{0}>>\Omega^1(M)@>d_{1}>>\cdots @>d_{k-1}>>\Omega^k(M)@>d_{k}>>\cdots
  \\& @VF^{*}VV&@VF^{*}VV&&@VF^{*}VV
  \\0@>>> \Omega^0(N)@>d_{0}>>\Omega^1(N)@>d_{1}>>\cdots @>d_{k-1}>>\Omega^k(N)@>d_{k}>>\cdots\end{CD}$$where the above diagram commutes as well as pullback and exterior derivative commutes. Further, $$F^{*}(\text{ker }d_{k}^M)\subseteq \text{ker }d_{k}^N,\quad F^{*}(\text{Im }d_{k}^M)\subseteq \text{Im }d_{k}^N$$from which we get the pullback $F^{*}:\text{H}_{\text{dR}}^k(M)\to\text{H}_{\text{dR}}^k(N)$.

---
##### Properties
> [!lemma] Theorem 1
> Let $M$ be a compact, connected and [[Orientable Manifold|oriented manifold]]. Then, $$\Omega^{m-1}(M)\xrightarrow{d_{m-1}}\Omega^m(M)\xrightarrow{\int_{M}^{} }\mathbb{R}$$is exact, i.e. $\text{ker}\int_{M}^{}=\text{im }d_{m-1}$. In other words, $\text{H}^m_{\text{dR}}(M)\cong \mathbb{R}$.

> [!proof]-
> We first show that $\text{ker}\int_{M}^{}\supseteq\text{Im }d_{m-1}$. Let $\omega\in \Omega^{m-1}(M)$. Take a chart $(U,\varphi)$ s.t. $B_{\leq 1}(0)\subseteq\varphi(U)$ and $D:=\varphi^{-1}(B_{\leq 1}(0))$. Then, both $D$ and $\overline{M \backslash D}$ are regular domains. Further they share the same boundary with exactly opposite orientations. Therefore: $$\int_{M}^{} d\omega=\int_{D}d\omega+\int_{\overline{M \backslash D}}d\omega=\int_{\widetilde{\partial D}}\omega+\int_{\widetilde{\partial (\overline{M \backslash D})}}\omega=0  $$by [[Regular Domain|Stoke's theorem]].
> 
> Conversely, let $\omega\in \text{ker}\int_{M}^{}$ and let $(U,\varphi)$ be a chart s.t. $F\subseteq U$ satisfies $\varphi(F)=[0,1]^m$. Then, by [[Differential k-Form|Lemma 6]], there exists $\eta\in \Omega^{m-1}(M)$ with $\text{supp}(\omega+d \eta)\subseteq F$. Also, $\int_{M}\omega+d \eta=0$. Therefore, by [[Differential k-Form|Lemma 5]], there exists $\alpha\in \Omega^{m-1}(M)$ s.t. $\omega+d \eta=d\alpha$. Therefore, $\omega=d(\alpha-\eta)$.
---