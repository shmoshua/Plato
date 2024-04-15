#Definition #FunctionalAnalysis 
> [!definition]
> A [[Hilbert space operator]] $T\in \mathcal{B}(\mathcal{H})$ is ***positive*** if $\braket{ Tx , x }\geq 0$ for all $x\in \mathcal{H}$, denoted as $T\geq 0$.
---
##### Properties
> [!lemma] Theorem 1
> Let $T\in \mathcal{B}(\mathcal{H})$. Then, the following are equivalent:
> 1. $T$ is positive.
> 2. $T$ is [[Adjoint Linear Map|self-adjoint]] and $\text{Sp}(T)\subseteq[0,+\infty)$

> [!proof]+
> Let $T\geq 0$. Then,  $\braket{ x , Tx }=\overline{\braket{ Tx , x }}=\braket{ Tx , x }$ and $T=T^{*}$. Especially, $\text{Sp}(T)\subseteq \mathbb{R}$. Let $\lambda>0$. Then, $$\lambda \|x\|^{2}=\lambda \braket{ x , x } \leq\lambda \braket{ x , x } +\braket{ T ,  } $$