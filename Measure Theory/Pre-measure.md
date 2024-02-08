#Definition #MeasureTheory 

> [!definition]
> For an algebra $\mathcal{A}\subseteq \mathcal{P}(X)$, a function $\lambda:\mathcal{A} \to[0,+\infty]$ is a **pre-measure**, if it is [[Additive Functions|$\sigma$-additive]].
---
##### Properties
> [!lemma] Theorem 1
> Let $\mathcal A\subseteq \mathcal P(X)$ be an algebra and $\lambda:\mathcal{A}\to[0,+\infty]$ a pre-measure. Then, for a function $\mu:\mathcal{P}(X)\to[0,+\infty]$ defined as: $$\mu(A)=\text{inf}\left\{  \left.\sum_{i=1}^{\infty}\lambda(A_{i})  \right| A_{i}\in \mathcal A,A\subseteq \bigcup_{i=1}^{\infty}A_{ i}\right\}$$the followings hold:
> 1. $\mu$ is a [[measure]].
> 2. $\left. \mu \right|_{\mathcal{A}}=\lambda$.
> 4. For all $A\in\mathcal A$, $A$ is [[Measurable Set|$\mu$-measurable]], i.e. $\mathcal{A}\subseteq\Sigma_{\mu}$
>    
> $\mu$ is called the ***Carathéodory-Hahn (CH) extension*** of $\lambda$.

> [!proof]-
 > We have that: 
> 1. The first statement holds from [[Set Covering|Theorem 1]].
> 2. For any $A\in\mathcal A$, $\mu(A)\leq\lambda(A)$ holds trivially. Now, let us choose any covering of $A\subseteq \bigcup_{i=1}^{\infty}A_{i}$. We may assume wlog that $A_{i}\cap A_{j}=\varnothing$ for $i\neq j$. However, $\tilde{A_{i}}:=A_{i}\cap A\in\mathcal A$ for all $i$ and $A=\bigcup_{i=1}^{\infty}\tilde{A_{i}}$. As $\lambda$ is $\sigma$-additive, $$\lambda(A)=\sum_{i=1}^{\infty}\lambda(A_{i}\cap A)\underset{ \text{monotonicty} }{ \leq }\sum_{i=1}^{\infty}\lambda(A_{i})$$
> 	As this holds for any covering, this proves that $\lambda(A)\leq \mu(A)$.
> 3. For any $A\in\mathcal A$, we take any $B\subseteq X$. We choose the covering $(B_{i})_{i}\subseteq\mathcal A$ with $B\subseteq \bigcup_{i=1}^{\infty}B_{i}$ s.t. $$\sum_{i=1}^{\infty}\lambda(B_{i})\leq \mu(B)+\epsilon$$Observe that $A,B_{i}\in \mathcal A$ we have $$\lambda(B_{i})=\lambda(B_{i}\cap A)+\lambda(B_{i}\backslash A)$$ and we have: $B\cap A\subseteq \bigcup_{i=1}^{\infty}(B_{i}\cap A)$ and $B\backslash A\subseteq \bigcup_{i=1}^{\infty}(B_{i}\backslash A)$
> 	Therefore, $$\mu(B\cap A)+\mu(B\backslash A)\leq \sum_{i=1}^{\infty}\lambda(B_{i}\cap A)+\sum_{i=1}^{\infty}\lambda(B_{i}\backslash A)=\sum_{i=1}^{\infty}\lambda(B_{i})\leq \mu(B)+\epsilon$$
> 	As $\epsilon$ was arbitrary, we have that $\mu(B\cap A)+\mu(B\backslash A)\leq \mu(B)$.

---

> [!lemma] Theorem 2 (Uniqueness of the Carathéodory-Hahn Extension)
> 	Let $\lambda:\mathcal{A} \to [0,+\infty]$ be a $\sigma$-finite pre-measure. Let $\mu$ be the CH-extension of $\lambda$ and $\Sigma$ the $\sigma$-algebra of all $\mu$-measurable sets. If $\tilde{\mu}:\mathcal{P}(X)\to[0,+\infty]$ is another measure s.t. $\left. \tilde{\mu} \right|_{\mathcal{A}}=\lambda$, then we have that: $$\left. \tilde{\mu} \right|_{\Sigma}=\mu$$

> [!proof]+
> We want to show that for any $A\in \Sigma$, $\tilde{\mu}(A)=\mu(A)$. 
> 1. **Showing $\tilde{\mu}(A)\leq \mu (A)$ for $A\in \Sigma$:**
> 	Let $A\subseteq \bigcup_{k=1}^{\infty}A_{k}$ with $A_{k}\subseteq \mathcal{A}$. Then, from the $\sigma$-subadditivity of $\tilde{\mu}$, $$\tilde{\mu}(A)\leq \sum_{k=1}^{\infty}\tilde{\mu}(A_{k})=\sum_{k=1}^{\infty}\lambda(A_{k})$$By taking the infimum, we get $\tilde{\mu}(A)\leq \mu(A)$.
> 2. **Showing $\mu(A)\leq \tilde{\mu}(A)$ if $A\subseteq S\in \mathcal{A}$ finite:**
>    First, assume that there exists $S\in \mathcal{A}$ s.t. $A\subseteq S$ and $\lambda(S)<+\infty$. Then, we get: $$\tilde{\mu}(S \backslash A)\leq \mu(S \backslash A)\leq \mu(S)=\lambda(S)<+\infty$$Therefore, by the $\sigma$-subadditivity of $\tilde{\mu}$: $$\tilde{\mu}(A)+\tilde{\mu}(S \backslash A)\leq \mu(A)+\mu(S \backslash A)=\mu(S)=\lambda(S)=\tilde{\mu}(S)\leq \tilde{\mu}(A)+\tilde{\mu}(S \backslash A)$$It follows that $\mu(A)\leq \tilde{\mu}(A)$ and $\mu(A)=\tilde{\mu}(A)$.
>  3. **Showing for arbitrary $A\in \Sigma$:**
>    Now suppose that $X=\bigcup_{k=1}^{\infty}S_{k}$ where $(S_{k})_{k}$ are mutually disjoint and $\lambda(S_{k})<+\infty$ (which exists as $\lambda$ is $\sigma$-finite).  Then, consider $A=\bigcup_{k=1}^{\infty}A_{k}$ where $A_{k}:=A \cap S_{k}$. Then, $$\tilde{\mu}\left( \bigcup_{k=1}^{m}A_{k} \right)=\mu\left( \bigcup_{k=1}^{m}A_{k} \right)$$Therefore, $$\tilde{\mu}(A)\geq \lim_{ m \to \infty } \tilde{\mu}\left( \bigcup_{k=1}^{m}A_{k} \right)=\lim_{ m \to \infty } \mu\left( \bigcup_{k=1}^{m}A_{k} \right)=\mu(A)$$
>
- **Remark**: $\Sigma$ may contain non-$\tilde{\mu}$-measurable sets.
- **Remark**: This theorem cannot be improved: Let $X=[0,1]$ and $\mathcal{A}=\{ \varnothing,X \}$. We also have the pre-measure $\lambda:\mathcal{A}\to[0,+\infty]$ s.t. $\lambda(\varnothing)=0$ and $\lambda(X)=1$. Then, from the CH-extension, we have:
	$$\mu(A)=\begin{cases}1&A\neq \varnothing\\0&A=\varnothing\end{cases}$$
	and we have $\Sigma=\{ \varnothing,X \}$. On the contrary, we have the [[Lebesgue Measure]] on $[0,1]$, $\mathcal{L}^1$ with $\mathcal{L}^1(\varnothing)=0$ and $\mathcal{L}^1(X)=1$. However, $\mathcal{L}^1\left( \left[ 0, \frac{1}{2} \right] \right)=\frac{1}{2}\neq 1=\mu\left[ 0, \frac{1}{2} \right]$

---