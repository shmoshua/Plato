#Definition #MeasureTheory 

> [!definition]
> The ***Lebesgue measure*** $\mathcal{L}^n$ of $\mathbb{R}^n$ is the [[Pre-measure|Carathéodory-Hahn extension]] of the [[volume function]] $\text{vol}$ defined on the algebra of elementary sets. In other words, 
> $$ \mathcal{L}^n(A)=\inf \left\{  \left. \sum_{j=1}^{\infty}\text{vol}(I_{j}) \right|   I_{j}\text{ is an elementary set} , A\subseteq \bigcup_{j=1}^{\infty}I_{j}\right\}$$

- **Remark**: It is not restrictive to assume that each $I_{j}$ is an interval (beyond being elementary sets)
---
##### Properties
> [!lemma] Theorem 1 (Regularity)
> For $A\subseteq \mathbb{R}^n$, we have that: $$\mathcal{L}^n(A)=\inf \{ \mathcal{L}^n(G):A\subseteq G, G\text{ is open} \}$$

> [!proof]-
> "$\leq$" side follows from the defintion, as $A \subseteq G$. Therefore, $\mathcal{L}^n(A)\leq \mathcal{L}^n(G)$.
> 
> For the "$\geq$" side, if $\mathcal{L}^n(A)=+\infty$, the equation holds trivially. Therefore, assume that $\mathcal{L}^n(A)<\infty$. From the definition of the infimum, for any $\epsilon>0$, we can find a sequence $\{ I_{k} \}$ s.t. $A\subseteq \bigcup_{k=1}^{\infty}I_{k}$ and $$\sum_{k=1}^{\infty}\text{vol}(I_{k})\leq \mathcal{L}^n(A)+\epsilon$$.
> It follows that $\sum_{k=1}^{\infty}\text{vol}(I_{k})<+\infty$ and therefore, $\text{vol}(I_{k})<+\infty$ for all $k \geq 1$.
> > [!lemma] Claim
> > For any $k \geq 1$ and $\epsilon >0$, there is an open interval $\tilde{ I_{k}}\supseteq I_{k}$ s.t. $$\text{vol}(\tilde{I}_{k})\leq \text{vol}(I_{k})+\frac{\epsilon}{2^k}$$
> 
> > [!proof]-
> > For any $k\geq 1$, as we have $\text{vol}(I_{k})<+\infty$, we can write $I_{k}=\prod_{\ell=1}^{n}J_{k,\ell}$.  Let $a_{k,\ell}:=\inf J_{k,\ell}\in \mathbb{R}$ and $b_{k,\ell}:=\sup J_{k,\ell}\in \mathbb{R}$. Then, for $\delta>0$, we define $$J_{k,\ell}^\delta:=(a_{k,\ell}-\delta,b_{k,\ell}+\delta)$$
> > and $J_{k}^\delta:=\prod_{\ell=1}^{n}J^\delta_{k,\ell}\supseteq I_{k}$, which is open. Then, $$\text{vol}(J^\delta_{k})=\prod_{\ell=1}^{n}(b_{k,\ell}-a_{k,\ell}+2\delta)$$ and $\lim_{ \delta \to 0 }\text{vol}(J^\delta_{k})=\text{vol}(I_{k})$.  This proves the statement.
> 
> Using the claim, we have $\{ \tilde{ I_{k}} \}$ of open intervals. Then, $G:=\bigcup_{k=1}^{\infty}\tilde{ I_{k}}$ is also open and: $$\mathcal{L}^n(G)\le \sum_{k=1}^{\infty}\text{vol}(\tilde{I}_{k})\leq\sum_{k=1}^{\infty}\text{vol}(I_{k})+\epsilon\leq \mathcal{L}^n(A)+2\epsilon$$
> As $\epsilon>0$ was arbitrary, this proves the statement.  
---
> [!lemma] Theorem 2
> The $\mathcal{L}^n$-measure is [[Borel Measure|Borel]], i.e. every $B\in \mathcal{B}(\mathbb{R}^n)$ is $\mathcal{L}^n$-measurable.

> [!proof]-
> This follows from [[Dyadic Cubes|Lemma 2]].

---

> [!lemma] Theorem 3
> For $A\subseteq \mathbb{R}^n$, the following conditions are equivalent: 
> 1. $A$ is $\mathcal{L}^n$-measurable.
> 2. For all $\epsilon>0$, there exists an open set $G \supseteq A$ s.t. $$\mathcal{L}^n(G\backslash A)\leq\epsilon$$

> [!proof]-
> We have: 
> 1. (1 -> 2): First case, assume that $\mathcal{L}^n(A)<+\infty$. Then, for any $\epsilon>0$, by Theorem 1 there exists an open set $G$ with $A\subseteq G$ s.t. $\mathcal{L}^n(G) \leq \mathcal{L}^n(A)+\epsilon$. As $A$ is $\mathcal{L}^n$-measurable, $$\mathcal{L}^n(G\backslash A)=\mathcal{L}^n(G)-\mathcal{L}^n(G\cap A)=\mathcal{L}^n(G)-\mathcal{L}^n( A)\leq \epsilon$$ In the second case where $\mathcal{L}^n(A)=+\infty$, we can define $A_{k}:=A \cap [-k,k]^n$ for all $k\geq 1$. Then, $\mathcal{L}^n(A_{k})<+\infty$ is bounded and $A=\bigcup_{k=1}^{\infty}A_{k}$. Using the same claim, we show that there exists an open set $G_{k}$ s.t. $A_{k}\subseteq G_{k}$ and $\mathcal{L}^n(G_{k}\backslash A_{k})\leq \frac{\epsilon}{2^k}$. Let $G:=\bigcup_{k=1}^{\infty}G_{k}.$ Then,
> $$\mathcal{L}^n(G\backslash A)\leq \sum_{k=1}^{\infty}\mathcal{L}^n(G_{k}\backslash A)\leq \sum_{k=1}^{\infty}\mathcal{L}^n(G_{k}\backslash A_{k})\leq \epsilon$$
> 2. (2 -> 1) Now for any $B\subseteq \mathbb{R}^n$, we have:
> $$\mathcal{L}^n(B\cap A)+\mathcal{L}^n(B\backslash A)\leq \mathcal{L}^n(B\cap G)+\mathcal{L}^n(B\backslash G)+\mathcal{L}^n(G\backslash A)\leq \mathcal{L}^n(B)+\epsilon$$
---

> [!lemma] Corollary 4
> For $A\subseteq \mathbb{R}^n$, $A$ is $\mathcal{L}^n$-measurable if and only if for all $\epsilon>0$ there exists a closed set $F$ and a open set $G$ s.t. $F\subseteq A\subseteq G$ and $$\mathcal{L}^n(G \backslash F)\leq\mathcal{L}^n(G\backslash A)+\mathcal{L}^n(A\backslash F)\leq\epsilon$$

> [!proof]-
> If this condition holds, then: for all $\varepsilon>0$ there exists an open set $G$ s.t. $A\subseteq G$ and $$\mathcal{L}^n(G \backslash A)\leq \mathcal{L}^n(G \backslash A)+\mathcal{L}^n(A \backslash F)\leq\varepsilon$$Therefore, $A$ is $\mathcal{L}^n$-measurable.
> 
> Conversely if $A$ is $\mathcal{L}^n$-measurable, for $\varepsilon>0$ find an open set $G \supseteq A^c$ s.t. $\mathcal{L}^n(G \backslash A^c)\leq\varepsilon$. If we set $F:=G^c$, then $F$ is closed and: $$\mathcal{L}^n(A \backslash F)=\mathcal{L}^n(A \cap G)=\mathcal{L}^n(G \backslash A^c)\leq \varepsilon$$This proves the statement.
---
> [!lemma] Theorem 5
> Lebesgue measure is invariant under isometries, i.e. for $$\begin{array}{cccc} {\Phi:}&{\mathbb{R}^n}&\to&{\mathbb{R}^n}\\&{x} &\mapsto & {Rx+x_{0}} \end{array}{}$$s.t. $R^\top R=I$, it holds that $\mathcal{L}^n(A)=\mathcal{L}^n(\Phi(A))$.

> [!proof]-
> Let $A \subseteq \mathbb{R}^n$. Then, we want to show that: $$\mathcal{L}^n(A)=\mathcal{L}^n(\Phi(A))$$
> If $A$ is an interval, by the invariance of the Jordan measure, we have that $\Phi(A)$ is Jordan-measurable and: $$\mathcal{L}^n(\Phi(A))=\mu(\Phi(A))=\mu (A)=\mathcal{L}^n(A)$$
> If $A$ is an open set, then $A=\bigcup_{k=1}^{\infty}I_{k}$ for disjoint intervals $\{ I_{k} \}_{k\geq 1}$. As $\Phi^{-1}$ is also an affine map between $\mathbb{R}^n$ and therefore continuous, we know that $\Phi(A)$ is an open set (therefore, $\mathcal{L}^n$-measurable). Therefore, $\Phi(A)=\bigcup_{k=1}^{\infty}\Phi(I_{k})$ where $\{\Phi(I_{k})\}_{k\geq 1}$ are disjoint. It follows that: $$\mathcal{L}^n(\Phi(A))=\sum_{k=1}^{\infty}\mathcal{L}^n(\Phi(I_{k}))=\sum_{k=1}^{\infty}\mathcal{L}^n(I_{k})=\mathcal{L}^n(A)$$Finally, for any $A$, we have that: $$\mathcal{L}^n(\Phi(A))=\inf_{\Phi(A)\subseteq \Phi(G), \Phi(G)\text{ open}}\mathcal{L}^n(\Phi(G))=\inf_{{A\subseteq G,G\text{ open}}}\mathcal{L}^n(G)=\mathcal{L}^n(A)$$
> This proves the statement.
---

> [!lemma] Theorem 7
> The $\mathcal{L}^n$-measure is [[Borel Measure|Borel regular]].

> [!proof]-
> For $A \subseteq \mathbb{R}^n$, if $\mathcal{L}^n(A)=+\infty$, then take $B=\mathbb{R}^n$.  If $\mathcal{L}^n(A)<+\infty$, then using the regularity of Lebesgue measures, for any $k\geq 1$, we can find an open set $G_{k}$ s.t. $A \subseteq G_{k}$ and $$\mathcal{L}^n(G_{k})\leq \mathcal{L}^n(A)+ \frac{1}{k}$$Further, we can assume that $(G_{k})_{k\geq 1}$ is decreasing. If not, we can define $\{ \tilde{G}_{k} \}_{k\geq 1}$ where $\tilde{ G}_{k}=G_{k} \cap \tilde{G}_{k-1}$. Now, if we define $B:=\bigcap_{k=1}^{\infty}G_{k}$, then: $$\mathcal{L}^n(A)\leq \mathcal{L}^n(B)=\lim_{ k \to \infty } \mathcal{L}^n(G_{k})\leq \mathcal{L}^n(A)$$Therefore, $\mathcal{L}^n$ is Borel-regular.

---
> [!lemma] Proposition 8
> Let $f:[a,b]\to \mathbb{R}$ be a bounded Riemann-integrable function. Then, it is [[Integrable Function|$\mathcal{L}^1$-integrable]] and: $$\mathcal{R}\int_{a}^{b} f(x) \, dx =\int_{[a,b]}f  \, d\mathcal{L}^1 $$

> [!proof]-
> We have: $$\mathcal{R}\underline{\int_{a}^b}f(x) \, dx=\underline{\int_{[a,b]}}f \, d\mathcal{L}^1=\overline{\int_{[a,b]}}f \, d\mathcal{L}^1=\mathcal{R}\overline{\int_{a}^{b}}f(x)  \, dx    $$
---
> [!lemma] Proposition 9
> Let $f:[a,+\infty)\to \overline{\mathbb{R}}$ be a locally bounded and locally Riemann-integrable function. Then, it is [[Summable Function|$\mathcal{L}^1$-summable]] if and only if $f$ is absolutely Riemann integrable, i.e. $$\int_{a}^{\infty} \left| f(x) \right|  \, dx=\lim_{ b \to \infty } \int_{a}^{b} \left| f(x) \right|  \, dx <+\infty $$Then, it holds that: $$\int_{a}^{\infty} f(x) \, dx =\int_{[a,\infty)}f  \, d\mathcal{L}^1 $$

> [!proof]-
> Let $g_{b}:=\left| f \right|\cdot \chi_{[a,b]}$. Then, $g_{b}$ is $\mathcal{L}^1$-summable as they are Riemann-integrable, by Proposition 8. Moreover, $g_{b}$ is an increasing sequence which converges to $\left| f \right|$ pointwise. 
> 
> Therefore, by the [[Integrable Function|Monotone Convergence Theorem]], $f$ is $\mathcal{L}^1$-summable if and only if $$\infty>\lim_{ b \to \infty }\int_{[a,+\infty)}g_{b}  \, d\mathcal{L}^1=\lim_{ b \to \infty } \int_{a}^{b}\left| f(x) \right|   \, dx   $$
---
> [!lemma] Theorem 10 (Change of Variable)
> Let $\Omega,O\subseteq \mathbb{R}^n$ be two open sets, $\Phi:\Omega\to O$ be a [[Diffeomorphism|$C^1$-diffeomorphism]]. Then, for $f:O\to \overline{\mathbb{R}}$:
> 1. $f$ is $\mathcal{L}^n$-measurable in $O$ $\Longleftrightarrow$ $x\mapsto (f\circ\Phi)(x)\left| \det(D\Phi(x)) \right|$ is $\mathcal{L}^n$-measurable in $\Omega$.
> 2. $f$ is $\mathcal{L}^n$-integrable in $O$ $\Longleftrightarrow$ $x\mapsto (f\circ\Phi)(x)\left| \det(D\Phi(x)) \right|$ is $\mathcal{L}^n$-integrable in $\Omega$. Then, $$\int_{O}f  \, d\mathcal{L}^n=\int_{\Omega}^{} f(\Phi(x))\left| \det(D\Phi(x)) \right|  \, d\mathcal{L}^n(x)  $$
---
> [!lemma] Corollary 11
> Let $A\subseteq\Omega$ be a $\mathcal{L}^n$-measurable set and $\Phi:\Omega\to O$ be a $C^1$-diffeomorphism. Then, $\Phi[A]\subseteq O$ is $\mathcal{L}^n$-measurable as well and: $$\mathcal{L}^n(\Phi[A])=\int_{A}^{} \left| \det(D\Phi(x)) \right|  \, d\mathcal{L}^n(x) $$

> [!proof]-
> As $A$ is measurable, $\chi_{A}$ is also $\mathcal{L}^n$-measurable in $\Omega$. $$\mathcal{L}^n(\Phi[A])=\int_{O}\chi_{\Phi[A]} \, d\mathcal{L}^n=\int_{\Omega}^{} \left| \det(D\Phi(x)) \right| \chi_{A}(x) \, d\mathcal{L}^n(x)=\int_{A}^{} \left| \det(D\Phi(x)) \right|  \, d\mathcal{L}^n(x)   $$
---
> [!lemma] Lemma 12 (Lipschitz maps measurable to measurable)
> Let $f:\mathbb{R}^n\to \mathbb{R}^n$ be [[Lipschitz Function|Lipschitz]] with Lipschitz constant $k$ and let $A\subseteq \mathbb{R}^n$ be $\mathcal{L}^n$-measurable. Then, $f[A]$ is $\mathcal{L}^n$-measurable.

> [!proof]-
> Let $\mathcal{L}^n(A)=0$. For $\varepsilon>0$, choose $G\supseteq A$ s.t. $\mu(G)<\varepsilon$ and denote $G=\bigcup_{j=1}^{\infty}Q_{j}$ where $Q_{j}$ are disjoint [[Dyadic Cubes]] with length $\ell_{j}$. Then, it holds that: $$f[A]\subseteq f[G]\subseteq \bigcup_{j=1}^{\infty}f[Q_{j}]$$ From Lipschitz continuity, the diameter of $f[Q_{j}]$ is: $$L_{j}:=\text{diam }f[Q_{j}]\leq L\cdot \omega_{n}\cdot \ell_{j}$$Therefore, $$\mu(f[A])\leq \sum_{j=1}^{\infty}\mu(f[Q_{j}])\leq \omega^n_{n}L^n\sum_{j=1}^{\infty}\mu(Q_{j})=\omega^n_{n}L^n\mu(G)<\omega^n_{n}L^n\varepsilon$$It follows that $f[A]$ is $\mathcal{L}^n$-measurable. 
> 
> Now let $\mathcal{L}^n(A)>0$. 
---
> [!lemma] Proposition 13 (Graph of Continuous Graphs is Lebesgue-Null)
> Let $f:[a,b]\to \mathbb{R}$ be continuous. Then, $\mathcal{L}^2(\text{Graph}(f))=0$

> [!proof]-
> Let $\varepsilon>0$. Then, there exists $\delta>0$ s.t. for any $x,y\in [a,b]$ with $\left| x-y \right|<\delta$, it holds that $\left| f(x)-f(y) \right|<\varepsilon$. 
> 
> Now, choose $a=x_{1}<x_{2}<\dots<x_{n}=b$ s.t. $x_{i+1}-x_{i}<\delta$ for all $i$. Then, we define: $$R_{i}:=[x_{i},x_{i+1}]\times[f(x_{i})-\varepsilon,f(x_{i})+\varepsilon]$$It follows that for any $x\in [a,b]$, there exists $R_{i}$ s.t. $(x,f(x))\in R_{i}$. Therefore, $$\mathcal{L}^2(\text{Graph}(f))\leq \mathcal{L}^2\left( \bigcup_{i=1}^{n-1}R_{i} \right) <2\varepsilon\sum_{i=1}^{n-1}(x_{i+1}-x_{i})=2\varepsilon(b-a)$$By $\varepsilon\to{0}$, we get that $\mathcal{L}^2(\text{Graph}(f))=0$.
---
##### Examples
###### Examples of non-$\mathcal{L}^n$ measurable sets
- [[Vitali Set]]
###### Examples of uncountable $\mathcal{L}^n$-null sets
- [[Cantor Set]]
---