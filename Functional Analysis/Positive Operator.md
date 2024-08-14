#Definition #FunctionalAnalysis 
> [!definition]
> A [[Hilbert Space Operator]] $T\in \mathcal{B}(\mathcal{H})$ is 
> 1. ***positive*** if $\braket{ Tx , x }\geq 0$ for all $x\in \mathcal{H}$, denoted as $T\geq 0$.
- **Remark**: For any $T\in \mathcal{B}(\mathcal{H})$, $T^{*}T\geq 0$ as $\braket{ T^{*}T x, x }=\left\| Tx \right\|^{2}$
---
##### Properties
> [!lemma] Theorem 1
> Let $T\in \mathcal{B}(\mathcal{H})$. Then, TFAE:
> 1. $T$ is positive.
> 2. $T$ is [[Adjoint Linear Map|self-adjoint]] and $\text{Sp}(T)\subseteq[0,+\infty)$

> [!proof]-
> We have:
> 1. (1=>2): Let $T\geq 0$. Then,  $\braket{ x , Tx }=\overline{\braket{ Tx , x }}=\braket{ Tx , x }$ and $T=T^{*}$. Especially, $\text{Sp}(T)\subseteq \mathbb{R}$. 
>    Let $\lambda>0$. Then, $$\lambda \|x\|^{2}=\lambda \braket{ x , x } \leq\lambda \braket{ x , x } +\braket{ Tx , x } =\braket{ (T+\lambda \text{id}_{\mathcal{H}})x , x }\leq \left\| (T+\lambda\text{id}_{\mathcal{H}})x \right\|  \cdot \|x\|$$Therefore, $\lambda\|x\|\leq \left\| (T+\lambda\text{id}_{\mathcal{H}})x \right\|$ for all $x\in \mathcal{H}$. Since $T+\lambda \text{id}_{\mathcal{H}}$ is normal, $T+\lambda \text{id}_{\mathcal{H}}$ invertible and $-\lambda\notin \text{Sp}(T)$. 
> 2. (2=>1): Assume $T$ is self-adjoint and $\text{Sp}(T)\subseteq[0,+\infty)$. By [[Guelfand Spectrum|Spectral theorem of normal operator]] let $E$ be the resolution of identity s.t. $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$Then for $x\in \mathcal{H}$, $$\braket{ Tx ,x  }=\int_{\text{Sp}(T)}\lambda \, dE_{x,x}(\lambda)  $$As $E_{x,x}$ is a positive Borel measure and $\text{Sp}(T)\subseteq[0,+\infty )$, $\braket{ Tx , x }\geq 0$. 
---
> [!lemma] Theorem 2 (Existence of Square Root)
> Let $T\geq 0$. 
> 1. there exists a unique $P\geq 0$ s.t. $P^{2}=T$. 
> 3. if $T$ is invertible, so is $P$.

> [!proof]+
> We have:
> 1. As $T$ is self-adjoint and hence normal, we can use the [[Guelfand Spectrum|spectral theorem on normal operators]] and let $E$ be the resolution of identity of $\text{Sp}(T)$ with: $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$As $\text{Sp}(T)\subseteq[0,+\infty)$ from 1, $f:\text{Sp}(T)\to \mathbb{C},\lambda\mapsto \sqrt{ \lambda }$ is a function in $C(\text{Sp}(T))$ and we can define:$$P:=f(T)=\int_{\text{Sp}(T)}\sqrt{ \lambda }  \, dE(\lambda)$$which is self-adjoint as $f$ is real and $\text{Sp}(P)\subseteq \text{Sp}(T)$. We also have that: $$P^{2}=f(T)^{2}=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda)=T $$
>    
>    To show that $P$ is unique, let $P'$ be another square root and $E'$ be the resolution of identity on $\text{Sp}(P')$ s.t. $$S'=\int_{\text{Sp}(S')}^{} \lambda \, dE'(\lambda) $$
> 
---
> [!lemma] Theorem 3 (Polar Decomposition)
> Let $T\in \mathcal{B}(\mathcal{H})$ be invertible. Further, let $P$ be the unique square root of $T^{*}T$. Then, $$T=UP$$where $U$ is unitary and $P\geq 0$. Moreover, this decomposition is unique.

> [!proof]-
> Let $P$ be the positive square root of $T^{*}T$. Since $T$ is invertible, so is $T^{*}$ hence $T^{*}T$ and $P$. Set $U:=TP ^{-1}$. Then, $U$ is invertible and $$U^{*}U=P ^{-1}T^{*}T P ^{-1}=P ^{-1} P^{2} P ^{-1}=\text{id}_{\mathcal{H}}$$The uniqueness follows from the uniqueness of inverse.
---