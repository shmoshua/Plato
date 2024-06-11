#MeasureTheory #Definition 

> [!definition]
> The ***Cantor set*** $C$ is defined as the set of values $x\in[0,1]$ s.t when written in base-3, i.e. $$x=\sum_{i=1}^{\infty}d_{i}(x)3^{-i}$$the digits $\{ d_{i}(x) \}_{i\geq 1}$ does not contain $1$. In other words,
> $$C:=\{ x\in[0,1]:d_{i}(x)\in \{ 0,2 \},\forall i\geq 1 \}$$

- **Remark**: Alternatively, it is defined as $C:=\bigcap_{n=1}^{\infty}C_{n}$ where: $$C_{n}:=\{ x\in[0,1]:d_{i}(x)\in \{ 0,2 \}\  \forall i\leq n\}$$Then, $C_{n}$ is a disjoint union of $2^n$ closed intervals of length $1/3^n$. 
- **Remark**: $C$ is closed as a union of closed sets.
---
##### Properties
> [!lemma] Lemma 1
> $\mathcal{L}^1(C)=0$, but $C$ is not countable.

>[!proof]-
>As $\mathcal{L}^1(C_{1})<\infty$ and using [[Measure Space|continuity from below]]:$$\mathcal{L}^1(C)=\mathcal{L}^1\left( \bigcap_{n=1}^{\infty}C_{n} \right) =\lim_{ n \to \infty } \mathcal{L}^1(C_{n})=\lim_{ n \to \infty } \left( \frac{2}{3} \right) ^n=0$$For the uncountability, we know that: $$\begin{array}{cccc} {f:}&{C}&\to&{[0,1]}\\&{x} &\mapsto & {\sum_{i=1}^{\infty}\left( \frac{d_{i}(x)}{2} \right)2^{-i} } \end{array}{}$$is a surjective function. (but not injective)
---
