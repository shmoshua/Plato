#Example #FunctionalAnalysis 

> [!definition]
> Let $\mathcal{H}$ be a [[Separable Space|separable]] [[Hilbert Space|Hilbert space]] with an [[orthonormal basis|orthonormal basis]] $\{ e_{i} \}_{i=1}^\infty$. Then, a ***diagonal operator*** is defined as: $$\begin{array}{cccc} {T:}&{\underset{ i\geq 1 }{ \oplus } \mathbb{C}e_{i}}&\to&{\underset{ i\geq 1 }{ \oplus } \mathbb{C}e_{i}}\\&{\sum_{i\geq 1}^{}a_{i}e_{i} } &\mapsto & {\sum_{i\geq 1}^{}\lambda_{i}a_{i}e_{i} } \end{array}{}$$for $\lambda_{i}\in \mathbb{C}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $T$ be a diagonal operator. 
> 1. $T$ is bounded if and only if $\sup_{i\geq 1}\left| \lambda_{i} \right|<+\infty$, in which case $\left\| T \right\|=\sup_{i\geq 1}\left| \lambda_{i} \right|$.
> 2. $T$ is compact if and only if $\lim_{ i \to \infty }\lambda_{i}=0$.

> [!proof]-
> We have that: 
> 1. Suppose $T\in \mathcal{B}(\mathcal{H})$ with $T(e_{i})=\lambda_{i}e_{i}$. Then, $$\left| \lambda_{i} \right| =\left\| \lambda_{i}e_{i} \right\| =\left\| Te_{i} \right\| \leq \left\| T \right\| $$
> Conversely, suppose $\sup_{i}\left| \lambda_{i} \right|<+\infty$. Then, define: $$T\left( \sum_{i}^{}a_{i}e_{i} \right) :=\sum_{i}^{}\lambda_{i}a_{i}e_{i}$$This is well-defined and is bounded as: $$\left\| T(v) \right\| ^{2}=\left\| T\left( \sum_{i}^{}a_{i}e_{i} \right)  \right\| ^{2}=\left\|\sum_{i}^{} \lambda_{i}a_{i}e_{i} \right\|^{2}=\sum_{i}^{}|\lambda_{i}|^{2}|a_{i}|^{2}\leq(\sup_{i}\left| \lambda_{i} \right| )^{2}\|v\|^2  $$for all $v\in \mathcal{H}$.
> 2. (=>): Assume that $T$ is compact. If $\lim_{ i \to \infty }\lambda_{i}\neq 0$, then there exists a subsequence $(\lambda_{i_{k}})_{k}$ and $\varepsilon>0$ s.t. $$\left| \lambda_{i_{k}} \right| >\varepsilon$$for all $k$. Then, there cannot be a Cauchy subsequence of $(T(e_{i_{k}}))_{k}:=(\lambda_{i_{k}}e_{i_{k}})_{k}$, as $$\left\| \lambda_{i}e_{i}-\lambda_{j}e_{j} \right\|^{2} =\left| \lambda_{i} \right| ^{2}+\left| \lambda_{j} \right| ^{2}$$for $i\neq j$. This is a contradiction to $T$ being compact as $\{ e_{i} \}\subseteq B_{\leq 1}(0)$.
> - (<=): For $n\geq 1$, we define: $$T_{n}(e_{i})=\begin{cases}\lambda_{i}e_{i}&1\leq i\leq n\\0&n<i\end{cases}$$Then, $$\left\| T-T_{n} \right\| =\sup_{i\geq n+1}\left| \lambda_{i} \right| \to 0$$Then $T_{n}\to T$ and as each $T_{n}$ is finite-rank, from the [[Compact Operator|Proposition 1]], $T$ is compact.
- **Remark**: Bounded operators correspond to bounded sequences and compact operators to sequences vanishing at infinity.
---
> [!lemma] Proposition 2
> A diagonal operator $T$ is [[Hilbert-Schmidt Operator|Hilbert-Schmidt]] if and only if $$\sum_{i=1}^{\infty}\left| \lambda_{i} \right|^{2}<+\infty $$

> [!proof]-
> $$\sum_{i,j=1}^{\infty}\left| \braket{ Te_{j} , e_{i} }  \right|^{2}=\sum_{i,j=1}^{\infty}\left| \overline{\lambda}_{i}\braket{ e_{j} , e_{i} }  \right|^{2}=\sum_{i=1}^{\infty}\left| \lambda_{i} \right| ^{2} $$
---
