#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. Then, the ***Guelfand transform*** of $x\in A$ is the function: $$\begin{array}{cccc} {\hat{x}:}&{\hat{A}}&\to&{\mathbb{C}}\\&{\chi} &\mapsto & {\chi(x)} \end{array}{}$$
---
##### Properties
> [!lemma] Theorem 1
> For any $x\in A$, 
> 1. $\hat{x}\in$ [[Continuous function Vanishing at Infinity|$C_{0}(\hat{A})$]].
> 2. $A\to C_{0}(\hat{A}),x\mapsto \hat{x}$ is an algebra homomorphism.
> 3. if $A$ is unital, $\text{Sp}_{A}(x)=\hat{x}(\hat{A})$.
> 4. if $A$ is non-unital, $\text{Sp}_{A}(x)=\hat{x}(\hat{A})\cup \{ 0 \}$.
> 5. $\|\hat{x}\|_{\infty}=\|x\|_{\text{sp}}$

> [!proof]+
> 
- **Corollary**: For $x,y\in A$, $\|xy\|_{\text{sp}}=\left\| \widehat{xy} \right\|_{\infty}\leq\|\hat{x}\|_{\infty}\|\hat{y}\|_{\infty}=\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.
- **Remark**: For every non-commutative Banach algebra $A$ and $x,y\in A$, s.t. $xy=yx$, $\|xy\|_{\text{sp}}\leq\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.