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
	 3. a [[Seminorm]] $\|f\|_{\infty}:=\sup\{ \left| \lambda \right|:\lambda\in \text{ess im}(f) \}$
	 4. $N:=\{ f\in \mathcal{B}^\infty(X),\|f\|_{\infty}=0 \}$ as a closed ideal in $\mathcal{B}^\infty(X)$.
	 5. The [[C*-Algebra|$C^{*}$-algebra]]: $L^\infty(E):= \mathcal{B}^\infty(X) / N$.
- **Remark**: For every $f\in \mathcal{B}^\infty(X)$, $\int_{X}^{} f\ dE_{x,y}$ is well-defined since $E_{x,y}$ is a regular Borel on $X$.
- **Remark**: If $\left\| f \right\|_{\infty}=0$, then, since $E(f^{-1}(\mathbb{C} \backslash \{ 0 \}))=0,$
	1. $\int_{X}^{} f \, dE_{x,x}=\int_{f^{-1}(\mathbb{C} \backslash \{ 0 \})}^{} f \, dE_{x,x}=0$ and
	2. $\int_{X}^{} f \, dE_{x,y}=0$ by the [[Inner Product Space|polarization identity]] ($E_{x+y,x+y},E_{x,x},E_{y,y},E_{x+iy,x+iy}$)
- **Related definition**: $f\in \mathcal{B}^\infty(X)$ is ***simple*** if $f(X)$ is finite. $\mathcal{S}(X)\subseteq \mathcal{B}^\infty(X)$ denotes the space of simple functions.

---
##### Properties
> [!lemma] Proposition 1
> For every $x\in \mathcal{H}$, the map $\mathcal{B}_{X}\to \mathcal{H},\omega\mapsto E(\omega)x$ is $\sigma$-additive, i.e. if $\omega=\bigsqcup_{n=1}^{\infty}\omega_{n}$ for $\omega_{n}\in \mathcal{B}_{X}$, then: $$E(\omega)x=\sum_{n=1}^{\infty}E(\omega_{n})x$$

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
> We have:
> 1. let $\omega=\bigcup_{n= 1}^{\infty}\omega_{n}$ with $\omega_{n}\in \mathcal{B}_{X}$ s.t. $E(\omega_{n})=0$. Then, $E(\omega)=0$.
> 2. let $(\omega_{n})_{n}\subseteq \mathcal{B}_{X}$ be increasing, then for all $x\in \mathcal{H}$, $$E\left( \bigcup_{n\geq 1}^{}\omega_{n} \right)x=\lim_{ n \to \infty } E(\omega_{n})x$$
> 3. let $(\omega_{n})_{n}\subseteq \mathcal{B}_{X}$ be decreasing, then for all $x\in \mathcal{H}$, $$E\left( \bigcap_{n\geq 1}^{}\omega_{n} \right)x=\lim_{ n \to \infty } E(\omega_{n})x$$


> [!proof]-
> We have that 
> 1. $E_{x,x}$ is a $\sigma$-additive measure. Therefore, for any $x\in \mathcal{H}$, $$\braket{ E(\omega)x , x } =E_{x,x}(\omega)\leq \sum_{n=1}^{\infty}E_{x,x}(\omega_{n})=0$$It follows that $E(\omega)=0$.
> 2. Consider $(\tilde{\omega}_{n})_{n}$ where $\tilde{\omega}_{n}:=\omega_{n}\backslash \omega_{n-1}$. Then, $(\tilde{ \omega}_{n})_{n}$ is disjoint and $$E\left( \bigcup_{n}^{} \omega_{n}\right)x=E\left( \bigcup_{n}^{}\tilde{\omega}_{n} \right)x=\sum_{n=1}^{\infty}E(\tilde{\omega}_{n})x=\lim_{ m\to \infty } \sum_{n=1}^{m}E(\tilde{\omega}_{n})x=\lim_{ m \to \infty } E(\omega_{m})x$$
> 3. Consider $(\tilde{\omega}_{n})_{n}$ where $\tilde{\omega}_{n}:=\omega_{1}\backslash \omega_{n}$. Then, $(\tilde{ \omega}_{n})_{n}$ is increasing and $$\begin{align}E\left( \bigcap_{n=1}^{\infty}\omega_{n} \right)x=E(\omega_{1})x- \end{align}$$
---
> [!lemma] Proposition 4
> We have that: 
> 1. $\mathcal{B}^\infty(X)$ is a commutative $C^{*}$-algebra with complex conjugate.
> 2. $\mathcal{B}^\infty(X)$ is a Banach space.
> 3. $\text{ess im}(f)$ is closed.

---
> [!lemma] Theorem 5
> Given a resolution of identity $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$, 
> 1. there exists a $C^{*}$-algebra isomorphism: $$\begin{array}{cccc} {\psi:}&{L^\infty(E)}&\to&{B\subseteq \mathcal{B}(\mathcal{H})}\end{array}{}$$s.t. $\braket{ \psi(f)x , y }=\int_{X}^{} f \, dE_{x,y}$ for all $f\in L^\infty(E)$.
> 2. $\|\psi(f)x\|^{2}=\int_{X}^{}  \left| f \right|^{2}\, dE_{x,x}$
> 3. $Q\in \mathcal{B}(\mathcal{H})$ commutes with $E(\omega)$ for all $\omega\in \mathcal{B}$ if and only if $Q$ commutes with $\psi(L^\infty(E)):=B$

> [!proof]- Proof (Exercise)
> We introduce the following notation: $\int_{X}^{} f \, dE:=\psi(f)$. We show: 
> 1. **Showing that $\mathcal{S}(X)$ is dense in $\mathcal{B}^\infty(X)$**: 
>    Let $\varepsilon>0$ and $f\in \mathcal{B}^\infty(X)$. Then, $f(X)\subseteq \mathbb{C}$ is bounded and we get a finite family of partition $$f(X)\subseteq \bigsqcup_{i,j}^{}D_{i,j}$$ s.t. $D_{i,j}$ is a square of side-length $\varepsilon$. Then, by selecting $z_{i,j}\in D_{i,j}$ for all $i,j$ and $$s_{\varepsilon}:=\sum_{i,j}^{}z_{i,j}\chi_{D_{i,j}}$$Then, $\|f-s_{\varepsilon}\|\leq \varepsilon$. 
> 2. **Showing that $\psi$ exists for $\mathcal{S}(X)$**:
>    Let $s\in \mathcal{S}(X)$ be simple. Then, there is a partition $\bigsqcup_{i=1}^{n}\omega_{i}=X$ with $s=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$. Then, we define:$$\psi(s):=\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})$$which has the property: 
>    - $\psi$ is linear: (Exercise)
>    $$\psi(s)^{*}=\left( \sum_{i=1}^{n}\alpha_{i} E(\omega_{i})\right)^{*}=\sum_{i=1}^{n}\overline{\alpha_{i}}E(\omega_{i})=\psi(\overline{s})$$
>    - Let $s=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$ and $t=\sum_{j=1}^{m}\beta_{j}\chi_{\omega'_{j}}$. Then, $st=\sum_{i=1}^{m}\sum_{j=1}^{m}\alpha_{i}\beta_{j}\chi_{\omega_{i}\cap\omega_{j}'}$ and: $$\psi(st)=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}E(\omega_{i}\cap\omega'_{j})=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}E(\omega_{i})E(\omega'_{j})=\psi(s)\psi(t)$$
>      
>    Then, $$\braket{ \psi(s)x , y } =\left\langle\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})x,y\right\rangle =\sum_{i=1}^{n}\alpha_{i}E_{x,y}(\omega_{i})=\int_{X}^{} \sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}} \, dE_{x,y}=\int_{X}^{} s \, dE_{x,y}  $$
>    and $$\left\| \psi(s)x \right\| ^{2}=\braket{ \psi(s)x , \psi(s)x } =\braket{ \psi(s)^{*}\psi(s)x , x } =\braket{ \psi(\overline{s}s)x , x } =\braket{ \psi (\left| s \right|^{2} )x , x } =\int_{X}^{} \left| s \right| ^{2} \, dE_{x,x} $$therefore, $\left\| \psi(s)x \right\|^{2}\leq \|s\|_{\infty}^{2} E_{x,x}(X)\leq\|s\|^{2}_{\infty}\|x\|^{2}$ and $\|\psi(s)\|\leq\|s\|_{\infty}$. Furthermore, we have that $\|s\|_{\infty}=\max\{ \left| \alpha_{i} \right|:E(\omega_{i})\neq 0 \}=\left| \alpha_{j_{0}} \right|$ for some $j_{0}$. 
>     
>     
>    Then, for $x\in \text{Im }E(\omega_{j_{0}})$ and $\|x\|=1$, we get: $$\psi(s)x=\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})x=\alpha_{j_{0}} E(\omega_{j_{0}})x=\alpha_{j_{0}} x$$where for all $i\neq j_{0}$, $E(\omega_{i})x=E(\omega_{i})E(\omega_{j_{0}})x=E(\omega_{i}\cap\omega_{j_{0}})x=0$. Therefore, $$\left\| \psi(s)x \right\| =\left| \alpha_{j_{0}} \right| \|x\|=\left| \alpha_{j_{0}} \right| =\|s\|_{\infty}$$This shows that $\|\psi(s)\|=\|s\|_{\infty}$. Therefore, by the [[Bounded Linear Map|BLT Theorem]], $\psi$ extends to $\psi:L^\infty(E)\to \mathcal{B}(\mathcal{H})$ s.t. $\|\psi(f)\|=\|f\|_{\infty}$. 
>  3. We have: $$\braket{ \psi(f)x , y } =\lim_{ k \to \infty }\braket{ \psi(s_{k})x , y } =\lim_{ k \to \infty } \int_{X}^{} s_{k} \, dE_{x,y}  $$where the limit converges for all diagonal coefficients $$\left| \int_{X}^{} f \, dE_{x,x} -\int_{X}^{} s_{k} \, dE_{x,x}  \right|=\left| \int_{X}^{} (f-s_{k}) \, dE_{x,x}  \right|\leq \left\| f-s_{k} \right\| E_{x,x}(X)=\left\| f-s_{k} \right\| \|x\|^{2}\to 0  $$and thereby for every $x,y\in \mathcal{H}$.

 ---
 