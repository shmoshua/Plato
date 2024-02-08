#Definition #MeasureTheory 

> [!DEFINITION]
> For a bounded set $A \subseteq \mathbb{R}^n$, the ***inner Jordan measure*** of $A$ is defined as: $$\underline{\mu}(A):=\sup\{ \text{vol}(E): E\text{ is an elemental set}, E\subseteq A\}$$
> Similarly, the ***outer Jordan measure*** of $A$ is defined as:
> $$\overline{\mu}(A):=\inf\{ \text{vol}(E): E\text{ is an elemental set}, A\subseteq E\}$$
> If $\underline{\mu}(A)=\overline{\mu}(A)$, then $A$ is ***Jordan measurable*** with $\mu(A)$.
---
##### Properties
> [!lemma] Theorem 1
> For a bounded set $A$, we have: 
> 1. $\overline{\mu}(A)=\overline{\mu}(\overline{A})$
> 2. $\underline{\mu}(A)=\underline{\mu}(A^\circ)$
---
> [!lemma] Theorem 2
> For a bounded set $A\subseteq \mathbb{R}^n$, we have that:
> 1. $\underline{\mu}(A) \leq \mathcal{L}^n(A)\leq \overline{\mu}(A)$.
> 2. If $A$ is Jordan measurable, $A$ is $\mathcal{L}^n$-measurable with $\mathcal{L}^n(A)=\mu(A)$.

> [!proof]-
> Let's prove them!
> 1. We have: $$\begin{align}\mathcal{L}^n(A)&=\inf \left\{ \left.  \sum_{k=1}^{\infty}\text{vol}(I_{k})  \right|  I_{k}\text{ is elementary}, A \subseteq \bigcup_{k=1}^{\infty}I_{k}\right\}\\&\leq\inf \left\{ \left.  \sum_{k=1}^{m}\text{vol}(I_{k})  \right|  I_{k}\text{ is elementary}, A \subseteq \bigcup_{k=1}^{m}I_{k}\right\}\\&= \bar{\mu}(A)\end{align}$$The other direction of the equation follows from monotonicity. For an elementary set $E\subseteq A$, we have: $$\text{vol}(E)=\mathcal{L}^n(E)\leq \mathcal{L}^n(A)$$
> 	Therefore: $$\underline{\mu}(A)=\sup\left\{  \text{vol}(E) : E\text{ is elementary}, E\subseteq A\right\}\leq \mathcal{L}^n(A)$$
> 2. Now let's show that $A$ is $\mathcal{L}^n$-measurable when $\underline{\mu}(A)=\mathcal{L}^n(A)=\overline{\mu}(A)$. Since $A$ is Jordan measurable, for all $\varepsilon>0$, we have elementary sets $I_{\varepsilon}$ and $I^\varepsilon$ s.t. $I_{\varepsilon}\subseteq A\subseteq I^\varepsilon$ s.t. $$\text{vol}(I^\varepsilon)-\varepsilon\leq \mu(A)\leq \text{vol}(I_{\varepsilon})+\varepsilon$$We can wlog assume that $I^\varepsilon$ is open and: $$\mathcal{L}(I^\varepsilon \backslash I_{\varepsilon})=\text{vol}(I^\varepsilon \backslash I_{\varepsilon})=\text{vol}(I^\varepsilon)-\text{vol}(I_{\varepsilon})\leq 2 \varepsilon$$Therefore, from [[Lebesgue Measure|Corollary 4]], $A$ is $\mathcal{L}^n$-measurable.
---
> [!lemma] Lemma 3
> Let $A\subseteq \mathbb{R}^n$ bounded and Jordan measurable. Then, 
> 1. $A+x$ is Jordan measurable for all $x\in \mathbb{R}^n$ and $\mu(A+x)=\mu(A)$
> 2. $tA$ is Jordan measurable for all $0<t<+\infty$ with $\mu(tA)=t^n\mu(A)$.

> [!proof]-
> If $E\subseteq A$ is an elementary set, then $E+x\subseteq A+x$ is an elementary set and therefore, $$\underline{\mu}(A+x)=\underline{\mu}(A)$$Similarly, $\overline{\mu}(A+x)=\overline{\mu}(A)$. This proves the statement.
> 
> An analogous proof for 2. 
---
> [!lemma] Proposition 4
> Any open ball $B_{<r}(x)$ and closed ball $B_{\leq r}(x)$ are Jordan measurable. 
---
##### Examples
- The graph and the epigraph of a continuous function $f:[a,b]\to \mathbb{R}$ are Jordan measurable.
- Countable unions of Jordan measurable sets is not generally Jordan measurable.
- $B_{<r}(x)$ is Jordan measurable.
---
###### Examples of non-Jordan measurable sets
1. $Q \cap[0,1]=\{ q_{i} \}_{i=0}^\infty$ with $q_{0}=0$. For $\varepsilon>0$, we define: $$V_{\varepsilon}:=\bigcup_{n=0}^{\infty}\left( q_{n}- \frac{\varepsilon}{2^n},q_{n} +\frac{\varepsilon}{2^n} \right) $$Then, $V_{\varepsilon}$ is an open set that covers $Q\cap[0,1]$. Therefore, $$\underline{\mu}\left( Q \cap[0,1] \right) \leq \underline{\mu}(V_{\varepsilon})\leq \mathcal{L}^1(V_{\varepsilon})\leq \sum_{n=0}^{\infty}\left( q_{n}- \frac{\varepsilon}{2^n},q_{n} +\frac{\varepsilon}{2^n} \right)=\sum_{n=0}^{\infty}\frac{2\varepsilon}{2^n}=4\varepsilon$$Therefore, $\underline{\mu}(Q \cap[0,1])=0$. On the other hand, we have: $$\overline{\mu}(Q \cap [0,1])=\overline{\mu}(\overline{Q \cap [0,1]})=\overline{\mu}[0,1]=1$$
	Therefore, the set is not Jordan measurable.
---
##### Related Definitions
- [[Lebesgue Measure]]