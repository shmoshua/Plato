#Definition #FunctionalAnalysis 
> [!definition]
> A [[Hilbert space operator]] $T\in \mathcal{B}(\mathcal{H})$ is ***positive*** if $\braket{ Tx , x }\geq 0$ for all $x\in \mathcal{H}$, denoted as $T\geq 0$.
- **Remark**: For any $T\in \mathcal{B}(\mathcal{H})$, $T^{*}T\geq 0$ as $\braket{ T^{*}T x, x }=\left\| Tx \right\|^{2}$
---
##### Properties
> [!lemma] Theorem 1
> Let $T\in \mathcal{B}(\mathcal{H})$. Then, the following are equivalent:
> 1. $T$ is positive.
> 2. $T$ is [[Adjoint Linear Map|self-adjoint]] and $\text{Sp}(T)\subseteq[0,+\infty)$

> [!proof]-
> Let $T\geq 0$. Then,  $\braket{ x , Tx }=\overline{\braket{ Tx , x }}=\braket{ Tx , x }$ and $T=T^{*}$. Especially, $\text{Sp}(T)\subseteq \mathbb{R}$. Let $\lambda>0$. Then, $$\lambda \|x\|^{2}=\lambda \braket{ x , x } \leq\lambda \braket{ x , x } +\braket{ Tx , x } =\braket{ (T+\lambda \text{id}_{\mathcal{H}})x , x }\leq \left\| (T+\lambda\text{id}_{\mathcal{H}})x \right\|  \cdot \|x\|$$Therefore, $\lambda\|x\|\leq \left\| (T+\lambda\text{id}_{\mathcal{H}})x \right\|$ for all $x\in \mathcal{H}$. Since $T+\lambda \text{id}_{\mathcal{H}}$ is normal, $T+\lambda \text{id}_{\mathcal{H}}$ invertible and $-\lambda\notin \text{Sp}(T)$. 
> 
> Conversely, assume $T$ is self-adjoint and $\text{Sp}(T)\subseteq[0,+\infty)$. Let $E$ be the resolution of identity s.t. $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$Then for $x\in \mathcal{H}$, $$\braket{ Tx ,x  }=\int_{\text{Sp}(T)}\lambda \, dE_{x,x}(\lambda)  $$As $E_{x,x}$ is a positive Borel measure, $\braket{ Tx , x }\geq 0$. 
---
> [!lemma] Theorem 2
> Every $T\geq 0$ has a unique square root $S\geq 0$. If $T$ is invertible, so is $S$.

> [!proof]- (Incomplete)
> Let $E$ be the resolution of identity on $\text{Sp}(T)$ with $T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda)$. Define $$S:=\int_{\text{Sp}(T)}^{} \sqrt{ \lambda } \, dE(\lambda) $$Then, $$\braket{ S^{2}x , y } =\int_{\text{Sp}(T)}^{\infty}  \sqrt{ \lambda }\, dE_{Sx,y}=T $$
---
> [!lemma] Theorem 3 (Polar Decomposition)
> Let $T\in \mathcal{B}(\mathcal{H})$ be invertible. Further, let $P$ be the unique square root of $T^{*}T$. Then, $$T=UP$$where $U$ is unitary and $P\geq 0$. Moreover, this decomposition is unique.

> [!proof]-
> Let $P$ be the positive square root of $T^{*}T$. Since $T$ is invertible, so is $T^{*}$ hence $T^{*}T$ and $P$. Set $U:=TP ^{-1}$. Then, $U$ is invertible and $$U^{*}U=P ^{-1}T^{*}T P ^{-1}=P ^{-1} P^{2} P ^{-1}=\text{id}_{\mathcal{H}}$$The uniqueness follows from the uniqueness of inverse.
---