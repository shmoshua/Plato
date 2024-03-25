#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[locally compact Hausdorff space]], $\mathcal{B}_{X}$ the [[Borel Sigma-Algebra|Borel $\sigma$-algebra]]  and $\mathcal{H}$ a [[Hilbert space]]. A map $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ is a ***resolution of identity*** if: 
> 1. $E(\varnothing)=0$, $E(X)=\text{id}_{\mathcal{H}}$.
> 2. $E(\omega)$ is a self-adjoint [[Hilbert Space Operator|projection]] for all $\omega\in \mathcal{B}_{X}$
> 3. $E(\omega_{1}\cap\omega_{2})=E(\omega_{1})E(\omega_{2})$ for all $\omega_{1},\omega_{2}\in \mathcal{B}_{X}$
> 4. $E(\omega_{1}\sqcup \omega_{2})=E(\omega_{1})+E(\omega_{2})$
> 5. for all $x,y\in \mathcal{H}$, the function: $$\begin{array}{cccc} {E_{x,y}:}&{\mathcal{B}_{X}}&\to&{\mathbb{C}}\\&{\omega} &\mapsto & {\braket{ E(\omega)x , y } } \end{array}{}$$is a regular [[complex measure]].

- **Remark**: In the applications, $X=$ [[Guelfand Spectrum|$\widehat{A}$]] where $A\subseteq \mathcal{B}(\mathcal{H})$ is an abelian sub-$C^{*}$-algebra.
- **Remark**: If $\omega_{1}\cap\omega_{2}=\varnothing$, then $\text{Im }E(\omega_{1}) {\ \bot\ }\text{Im } E(\omega_{2})$ (cf. [[Hilbert Space Operator|Proposition 3]])
- **Remark**: For any $x\in \mathcal{H}$, $E_{x,x}(\omega)=\braket{ E(\omega)x , x }=\left\| E(\omega)x \right\|^{2}$. Therefore, $0\leq E_{x,x}(\omega)\leq \|x\|^{2}$ and $E_{x,x}$ is a bounded positive measure.
- **Related definition**: We define:
	 1. $\mathcal{B}^\infty(X):=\{ f:X\to \mathbb{C} | f\text{ Borel-measurable}, \left\| f \right\| :=\sup_{x\in X}\left| f(x) \right|  \}$ and 
	 2. the ***essential image*** of a measurable function $f:X\to \mathbb{C}$ as: $\text{ess im}(f):=\mathbb{C} \backslash \bigcup_{E(f^{-1}(D_{n}))=0}^{}D_{n}$. 
	 3. a [[seminorm]] $\|f\|_{\infty}:=\sup\{ \left| \lambda \right|:\lambda\in \text{ess im}(f) \}$
	 4. $N:=\{ f\in \mathcal{B}^\infty(X),\|f\|_{\infty}=0 \}$ as a closed ideal in $\mathcal{B}^\infty(X)$.
	 5. The [[C*-Algebra|$C^{*}$-algebra]]: $L^\infty(E):= \mathcal{B}^\infty(X) / N$.
- **Remark**: For every $f\in \mathcal{B}^\infty(X)$, $\int_{X}^{} f\ dE_{x,y}$ is well-defined since $E_{x,y}$ is a regular Borel on $X$.
- **Remark**: If $\left\| f \right\|_{\infty}=0$, then, since $E(f^{-1}(\mathbb{C} \backslash \{ 0 \}))=0,$
	1. $\int_{X}^{} f \, dE_{x,x}=\int_{f^{-1}(\mathbb{C} \backslash \{ 0 \})}^{} f \, dE_{x,x}=0$ and
	2. $\int_{X}^{} f \, dE_{x,y}=0$ by the [[Inner Product Space|polarization identity]] ($E_{x+y,x+y},E_{x,x},E_{y,y},E_{x+iy,x+iy}$)

---
##### Properties
> [!lemma] Proposition 
> For every $x\in \mathcal{H}$, the map $\mathcal{B}_{X}\to \mathcal{H}:\omega\mapsto E(\omega)x$ is $\sigma$-additive, i.e. if $\omega=\bigsqcup_{n=1}^{\infty}\omega_{n}$ for $\omega_{n}\in \mathcal{B}_{X}$, then: $$E(\omega)x=\sum_{n=1}^{\infty}E(\omega_{n})x$$

> [!proof]- Proof (Incomplete)
> Since $\omega\mapsto \braket{ E(\omega)x , y }$ is a complex measure, we have: $$\braket{ E(\omega)x , y } =\sum_{n=1}^{\infty}\braket{ E(\omega_{n})x , y } $$However, as $\omega_{i}\cap\omega_{j}=\varnothing$, $E(\omega_{i})x \ {\bot}\ E(\omega_{j})x$ for all $i,j\geq 1$. Therefore, by Lemma 2, we prove the statement.
- **Remark**: Note that $\omega\mapsto E(\omega)$ is not $\sigma$-additive. The sum does not converge in $\mathcal{B}(\mathcal{H})$ in general!
---
> [!lemma] Lemma 2
> Assume $\{ x_{n}: n\geq 1 \}$ is pairwise orthogonal. Then, the following are equivalent:
> 1. $\sum_{n=1}^{\infty}x_{n}$ converges.
> 2. $\sum_{n=1}^{\infty}\left\| x_{n} \right\|^{2}$ converges.
> 3. $\sum_{n=1}^{\infty}\braket{ x_{n} , y }$ converges for all $y\in \mathcal{H}$.

> [!proof]-
> 1 is equivalent to 2 by [[Hilbert Space|Pythagoras]]. (the partial sum is Cauchy in one iff it is in another).
> 1. (1=>3): We have; $$\left| \sum_{n=k}^{\ell}\braket{ x_{n} , y }  \right| =\left| \left\langle \sum_{n=k}^{\ell} x_{n},y  \right\rangle \right|\leq \left\| \sum_{n=k}^{\ell}x_{n} \right\| \left\| y \right\|  $$Therefore, 3 is Cauchy if 1 is Cauchy.
> 2. (3=>1): Define $\Lambda_{n}(y):=\sum_{k=1}^{n}\braket{ y ,x_{k}  }$ . Then, $\Lambda_{n}\in \mathcal{H}^{*}$. Then, for all $y\in \mathcal{H}$, $\lim_{ n \to \infty }\Lambda_{n}(y)$ exists and $$\sup_{n\geq 1}\left| \Lambda_{n}(y) \right| <+\infty,\quad \forall y\in \mathcal{H}$$Then, by [[Bounded Linear Map|Banach-Steinhaus]], $\sup_{n\geq 1}\left\| \Lambda_{n} \right\|<+\infty$. Then, $$\left\| \Lambda_{n} \right\| ^{2}=\sup_{\left\| y \right\| \leq 1}\left| \left\langle\sum_{k=1}^{n}x_{k},y\right\rangle \right| ^{2}\leq \left\| \sum_{k=1}^{n}x_{k} \right\| ^{2}=\sum_{k=1}^{n}\left\| x_{k} \right\| ^{2}$$Therefore, we get 1. 
---

> [!lemma] Lemma 3
> Let $\omega=\bigcup_{n= 1}^{\infty}\omega_{n}$ with $\omega_{n}\in \mathcal{B}_{X}$ s.t. $E(\omega_{n})=0$. Then, $E(\omega)=0$.

> [!proof]-
> We have that $E_{x,x}$ is a $\sigma$-additive measure. Therefore, for any $x\in \mathcal{H}$, $$\braket{ E(\omega)x , x } =E_{x,x}(\omega)\leq \sum_{n=1}^{\infty}E_{x,x}(\omega_{n})=0$$It follows that $E(\omega)=0$.
---
> [!lemma] Proposition 4
> We have that: 
> 1. $\mathcal{B}^\infty(X)$ is a commutative $C^{*}$-algebra with complex conjugate.
> 2. $\mathcal{B}^\infty(X)$ is a Banach space.
> 3. $\text{ess im}(f)$ is closed.

---
