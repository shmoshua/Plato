#Definition #MeasureTheory 

> [!definition] Definition (Carathéodory criterion)
> For a [[Measure|measure]] $\mu:\mathcal{P}(X)\to[0,+\infty]$, a set $A \subseteq X$ is called ***$\mu$-measurable*** if for all $B\subseteq X$, we have: $$\mu(B)=\mu(B\cap A)+\mu(B \backslash A)$$
> As a measure $\mu$ is $\sigma$-subadditive, this condition is equivalent to: $$\mu(B)\geq\mu(B\cap A)+\mu(B \backslash A)$$
---
##### Properties
> [!lemma] Theorem 1
> For a subset $A\subseteq X$, if $\mu(A)=0$, then $A$ is $\mu$-measurable.

>[!proof]-
>We have that: $$\mu(B\cap A)+\mu(B \backslash A)\leq \mu (A)+\mu(B)=\mu(B)$$
---
> [!lemma] Theorem 2
> For a measure $\mu: \mathcal{ P}(X)\to[0,+\infty]$, the set: $$\Sigma:=\{ A \subseteq X:A\text{ is }\mu \text{-measurable} \}$$is a [[Sigma Algebra|$\sigma$-algebra]].

>[!proof]-
>We have:
>1. For all $B \subseteq X$, we have: $$\mu(B \cap X)+\mu(B \backslash X)=\mu(B)+\mu(\varnothing)=\mu(B)$$
>2. For $A\in \Sigma$ and all $B \subseteq X$, we have: $$\mu(B \cap A^c)+\mu(B \backslash A^c)=\mu(B \backslash A)+\mu(B \cap A)=\mu(B)$$
>3. For $A_{1},\dots,A_{m}\in \Sigma$, we will show that the finite union $\bigcup_{i=1}^{m}A_{i}\in \Sigma$ using induction. If $m=1$, it holds trivially. Let $A:=\bigcup_{i=1}^{m-1}A_{i}\in \Sigma$. Then, for any subset $B \subseteq X$: $$\mu(B \backslash A)=\mu((B \backslash A)\cap A_{m})+\mu((B \backslash A)\backslash A_{m})=\mu((B \backslash A)\cap A_{m})+\mu(B \backslash (A \cup A_{m}))$$
>   Therefore, we have: $$ \begin{align}\mu(B)&=\mu(B\cap A)+\mu(B \backslash A)\\&=\mu(B\cap A)+\mu((B \backslash A)\cap A_{m})+\mu(B \backslash (A \cup A_{m}))\\&\geq \mu(B \cap (A\cup A_{m}))+\mu(B \backslash(A\cup A_{m}))\end{align}$$where in the last step we use $\sigma$-subadditivity.
>4. Let $(A_{n})_{n}\subseteq \Sigma$. We will show that $\bigcup_{n=1}^{\infty}A_{n}\in \Sigma$. Wlog we can assume that $A_{n}$ are disjoint. For any subset $B \subseteq X$, notice that $$\begin{align}\mu \left( B\cap \bigcup_{n=1}^{m}A_{n} \right)&=\mu \left( \left( B \cap \bigcup_{n=1}^{m}A_{n} \right) \cap A_{m}\right)  +\mu \left( \left( B \cap \bigcup_{n=1}^{m}A_{n} \right) \backslash A_{m}\right) \\&=\mu(B \cap A_{m})+ \mu \left( B\cap \bigcup_{n=1}^{m-1}A_{n} \right)= \cdots  =\sum_{n=1}^{m}\mu(B\cap A_{n})\end{align}$$
>Therefore, for any $m$:$$\begin{align}\mu(B)&=\mu \left( B\cap \bigcup_{n=1}^{m}A_{n} \right)+ \mu \left( B\backslash \bigcup_{n=1}^{m}A_{n} \right)\geq \sum_{n=1}^{m}\mu(B\cap A_{n})+\mu \left( B \backslash \bigcup_{n=1}^{\infty} A_{n} \right)\end{align}$$
> Then, $$\mu(B)\geq \sum_{n=1}^{\infty}\mu(B\cap A_{n})+\mu \left( B \backslash \bigcup_{n=1}^{\infty} A_{n} \right)\geq\mu \left( B \cap \bigcup_{n=1}^{\infty} A_{n} \right)+\mu \left( B \backslash \bigcup_{n=1}^{\infty} A_{n} \right)$$
>This proves that $\bigcup_{n=1}^{\infty}A_{n}\in \Sigma$.

---

