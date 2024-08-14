#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[locally compact Hausdorff space]], $\mathcal{B}_{X}$ the [[Borel Sigma-Algebra|Borel $\sigma$-algebra]]  and $\mathcal{H}$ a [[Hilbert space]]. A map $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ is a ***resolution of identity*** if: 
> 1. $E(\varnothing)=0$, $E(X)=\text{id}_{\mathcal{H}}$.
> 2. $E(\omega)$ is a self-adjoint [[Hilbert Space Operator|projection]] for all $\omega\in \mathcal{B}_{X}$
> 3. $E(\omega_{1}\cap\omega_{2})=E(\omega_{1})E(\omega_{2})$ for all $\omega_{1},\omega_{2}\in \mathcal{B}_{X}$
> 4. $E(\omega_{1}\sqcup \omega_{2})=E(\omega_{1})+E(\omega_{2})$
> 5. for all $x,y\in \mathcal{H}$, the function: $$\begin{array}{cccc} {E_{x,y}:}&{\mathcal{B}_{X}}&\to&{\mathbb{C}}\\&{\omega} &\mapsto & {\braket{ E(\omega)x , y } } \end{array}{}$$is a regular [[complex measure]].

- **Remark**: In the applications, $X=$ [[Guelfand Spectrum|$\widehat{A}$]] where $A\subseteq \mathcal{B}(\mathcal{H})$ is an abelian sub-$C^{*}$-algebra.
- **Remark**: If $\omega_{1}\cap\omega_{2}=\varnothing$, then $\text{Im }E(\omega_{1}) {\ \bot\ }\text{Im } E(\omega_{2})$ (cf. [[Hilbert Space Operator|Proposition 4]])
- **Remark**: For any $x\in \mathcal{H}$, $E_{x,x}(\omega)=\braket{ E(\omega)x , x }=\left\| E(\omega)x \right\|^{2}$. Therefore, $0\leq E_{x,x}(\omega)\leq \|x\|^{2}$ and $E_{x,x}$ is a bounded positive measure.
- **Related definition**: We define:
	 1. $\mathcal{B}^\infty(X):=\{ f:X\to \mathbb{C} | f\text{ Borel-measurable}, \left\| f \right\| :=\sup_{x\in X}\left| f(x) \right| <+\infty \}$ and 
	 2. the ***essential image*** of a measurable map $f:X\to \mathbb{C}$: $\text{ess im}(f):=\mathbb{C} \backslash \bigcup_{E(f^{-1}(D_{n}))=0}^{}D_{n}$. 
	 3. a [[seminorm]] $\|f\|_{\infty}:=\sup\{ \left| \lambda \right|:\lambda\in \text{ess im}(f) \}$
	 4. $N:=\{ f\in \mathcal{B}^\infty(X):\|f\|_{\infty}=0 \}$ as a closed ideal in $\mathcal{B}^\infty(X)$.
	 5. The [[C*-Algebra|$C^{*}$-algebra]]: $L^\infty(E):= \mathcal{B}^\infty(X) / N$.
- **Remark**: For every $f\in \mathcal{B}^\infty(X)$, $\int_{X}^{} f\ dE_{x,y}$ is well-defined since $E_{x,y}$ is a regular Borel on $X$.
- **Remark**: If $\left\| f \right\|_{\infty}=0$, then, since $E(f^{-1}(\mathbb{C} \backslash \{ 0 \}))=0,$
	1. $\int_{X}^{} f \, dE_{x,x}=\int_{f^{-1}(\mathbb{C} \backslash \{ 0 \})}^{} f \, dE_{x,x}=0$ and
	2. $\int_{X}^{} f \, dE_{x,y}=0$ by the [[Inner Product Space|polarization identity]] ($E_{x+y,x+y},E_{x,x},E_{y,y},E_{x+iy,x+iy}$)
- **Related definition**: $f\in \mathcal{B}^\infty(X)$ is ***simple*** if $f(X)$ is finite. $\mathcal{S}(X)\subseteq \mathcal{B}^\infty(X)$ denotes the space of simple functions.

---
##### Properties
> [!lemma] Proposition 1
> For every $x\in \mathcal{H}$, 
> 1. the map $\mathcal{B}_{X}\to \mathcal{H},\omega\mapsto E(\omega)x$ is $\sigma$-additive, i.e. if $\omega=\bigsqcup_{n=1}^{\infty}\omega_{n}$ for $\omega_{n}\in \mathcal{B}_{X}$, then: $$E(\omega)x=\sum_{n=1}^{\infty}E(\omega_{n})x$$

> [!proof]-
> Since $\omega\mapsto \braket{ E(\omega)x , y }$ is a complex measure, we have: $$E_{x,y}(\omega)=\braket{ E(\omega)x , y } =\sum_{n=1}^{\infty}\braket{ E(\omega_{n})x , y } $$However, as $\omega_{i}\cap\omega_{j}=\varnothing$, $E(\omega_{i})x \ {\bot}\ E(\omega_{j})x$ for all $i,j\geq 1$. Therefore, by [[Hilbert Space Operator|Lemma 2]], we have that $\sum_{n=1}^{\infty}E(\omega_{n})x$ converges in $\mathcal{H}$. Hence, $$\braket{ E(\omega)x , y } =E_{x,y}(\omega)=\sum_{n=1}^{\infty}\braket{ E(\omega_{n})x , y }=\left\langle \sum_{n=1}^{\infty}E(\omega_{n})x , y \right\rangle  $$Since this holds for every $y\in \mathcal{H}$, $E(\omega)x=\sum_{n=1}^{\infty}E(\omega_{n})x$.
- **Remark**: Note that $\omega\mapsto E(\omega)$ is not $\sigma$-additive. The sum does not converge in $\mathcal{B}(\mathcal{H})$ in general!
---

> [!lemma] Lemma 2
> We have:
> 1. let $\omega=\bigcup_{n= 1}^{\infty}\omega_{n}$ with $\omega_{n}\in \mathcal{B}_{X}$ s.t. $E(\omega_{n})=0$. Then, $E(\omega)=0$.
> 2. let $(\omega_{n})_{n}\subseteq \mathcal{B}_{X}$ be increasing, then for all $x\in \mathcal{H}$, $$E\left( \bigcup_{n\geq 1}^{}\omega_{n} \right)x=\lim_{ n \to \infty } E(\omega_{n})x$$
> 3. let $(\omega_{n})_{n}\subseteq \mathcal{B}_{X}$ be decreasing, then for all $x\in \mathcal{H}$, $$E\left( \bigcap_{n\geq 1}^{}\omega_{n} \right)x=\lim_{ n \to \infty } E(\omega_{n})x$$


> [!proof]+
> We have that 
> 1. $E_{x,x}$ is a $\sigma$-additive measure. Therefore, for any $x\in \mathcal{H}$, $$\braket{ E(\omega)x , x } =E_{x,x}(\omega)\leq \sum_{n=1}^{\infty}E_{x,x}(\omega_{n})=0$$It follows that $E(\omega)=0$.
> 2. Consider $(\tilde{\omega}_{n})_{n}$ where $\tilde{\omega}_{n}:=\omega_{n}\backslash \omega_{n-1}$. Then, $(\tilde{ \omega}_{n})_{n}$ is disjoint and $$E\left( \bigcup_{n}^{} \omega_{n}\right)x=E\left( \bigcup_{n}^{}\tilde{\omega}_{n} \right)x=\sum_{n=1}^{\infty}E(\tilde{\omega}_{n})x=\lim_{ m\to \infty } \sum_{n=1}^{m}E(\tilde{\omega}_{n})x=\lim_{ m \to \infty } E(\omega_{m})x$$
> 3. Consider $(\tilde{\omega}_{n})_{n}$ where $\tilde{\omega}_{n}:=\omega_{1}\backslash \omega_{n}$. Then, $(\tilde{ \omega}_{n})_{n}$ is increasing and $$\begin{align}E\left( \bigcap_{n=1}^{\infty}\omega_{n} \right)x=E(\omega_{1})x- \end{align}$$
---
> [!lemma] Lemma 3 (Essential Image Lemma)
> For a compact Hausdorff $X$ and a measurable function $f:X\to \mathbb{C}$, 
> 1. $\text{ess im}(f)$ is closed.
> 2. for any $z\in \text{ess im}(f)$ and open $U\ni z$, $E(f^{-1}(U))\neq 0$.
> 3. for any $U\subseteq \mathbb{C}$ open, if $E(f^{-1}(U))=0$, then $U\subseteq \mathbb{C} \backslash \text{ess im}(f)$.
> 4. $\|f\|_{\infty}=\inf\{ t\geq 0:E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0))) =0\}$

> [!proof]-
> We have that:
> 1. By definition.
> 2. If $z\in \text{ess im}(f)$. Then, for any $D_{n}$ with $E(f^{-1}(D_{n}))=0$, $z\notin D_{n}$. Now, assume that $E(f^{-1}(U))=0$. By basis, there exists $z\in D_{n}\subseteq U$ and as $$f^{-1}(U)=f^{-1}(D_{n})\sqcup f^{-1}(U\backslash D_{n})$$we have that $$0=E(f^{-1}(U))=E(f^{-1}(D_{n}))+E(f^{-1}(U \backslash D_{n}))$$Now, for any $x\in \mathcal{H}$, $$\braket{ E(f^{-1}(D_{n}))x , x } =\braket{ E(f^{-1}(D_{n}))x , E(f^{-1}(D_{n}))x }=\braket{ E(f^{-1}(D_{n}))x , -E(f^{-1}(U \backslash D_{n}))x }=0  $$and $E(f^{-1}(D_{n}))=0$, which is a contradiction.
> 3. From 2.
> 4. Let $z\in \text{ess im}(f)$. Then, by 2 $E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0)))=0$ means that $\left| z \right|\leq t$. Otherwise $z\in \mathbb{C} \backslash B_{\leq t}(0)$ which is open and $E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0)))\neq 0$. Hence, we have that: $$\left\| f \right\| _{\infty}=\inf \{ t\geq 0 : E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0)))=0\}$$Now consider $t>\left\| f \right\|_{\infty}$. Then, $\text{ess im}(f)\subseteq B_{\leq t}(0)$ and there exists a countable open cover $\mathbb{C} \backslash B_{\leq t}(0)\subseteq \bigcup_{n}^{}D_{n}$ where $E(f^{-1}(D_{n}))=0$. Therefore, by Lemma 2.1, we get that: $$E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0)))=0$$ and this proves that $\|f\|_{\infty}\geq\inf\{ t\geq 0:E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0))) =0\}$.

---
> [!lemma] Lemma 4 (Essential Norm Lemmas)
> We have for $f,g\in \mathcal{B}^\infty(X)$,
> 1. $\left\| f \right\|_{\infty}\leq \left\| f \right\|_{b}$.
> 2. $\left\| f+g \right\|_{\infty}\leq \left\| f \right\|_{\infty}+\left\| g \right\|_{\infty}$.
> 3. $\left\| fg \right\|_{\infty}\leq \left\| f \right\|_{\infty}\left\| g \right\|_{\infty}$
> 4. for $g\in N:=\{ f\in \mathcal{B}^\infty(X):\left\| f \right\|_{\infty}=0 \}$, $\left\| f+g \right\|_{\infty}=\left\| f \right\|_{\infty}$ 

> [!proof]-
> We have:
> 1. Let $t:=\left\| f \right\|_{b}$. Then, $f^{-1}(\mathbb{C} \backslash B_{\leq t}(0))=\varnothing$ and $E(f^{-1}(\mathbb{C} \backslash B_{\leq t}(0)))=0$. Hence, $\left\| f \right\|_{b}\geq \left\| f \right\|_{\infty}$ by Lemma 3.3
> 2. Let $s>\left\| f \right\|_{\infty}$ and $t>\left\| g \right\|_{\infty}$. Then, $$(f+g)^{-1}(\mathbb{C} \backslash B_{\leq s+t}(0))\subseteq f^{-1}(\mathbb{C} \backslash B_{\leq s}(0))\cup g^{-1}(\mathbb{C} \backslash B_{\leq t}(0))$$Therefore, $E((f+g)^{-1}(\mathbb{C} \backslash B_{\leq s+t}(0)))=0$ and $\|f+g\|_{\infty}\leq\|f\|_{\infty}+\|g\|_{\infty}$.
> 3. Analogous to 2. 
> 4. $\left\| f+g \right\|_{\infty}\leq \left\| f \right\|_{\infty}+\left\| g \right\|_{\infty}=\left\| f \right\|_{\infty}$. But $$\left\| f \right\| _{\infty}=\left\| f+g-g \right\| _{\infty}\leq \left\| f+g \right\| _{\infty}+\left\| g \right\| _{\infty}=\left\| f+g \right\| _{\infty}$$
---
> [!lemma] Proposition 5 (Bounded Borel Functions form a C*-algebra)
> We have that: 
> 1. $\mathcal{B}^\infty(X)$ is a commutative $C^{*}$-algebra with complex conjugate.
> 2. $L^\infty(E):=\mathcal{B}^\infty(X) / N$ quotient norm is given by $\left\| f+N \right\|=\left\| f \right\|_{\infty}$.
> 3. $L^\infty(E):=\mathcal{B}^\infty(X) / N$ is a $C^{*}$-algebra. 
> 4. $\text{Sp}_{L^\infty(N)}(f+N)=\text{ess im}(f)$ for $f\in \mathcal{B}^\infty(X)$.

> [!proof]-
> We have that:
> 1. For $\mathcal{B}^\infty(X)$:
> 	1. $\mathcal{B}^\infty(X)$ is a unital $\mathbb{C}$-algebra with unit $1$.
> 	2. **$\mathcal{B}^\infty(X)$ is a Banach space**: Let $(f_{n})\in \mathcal{B}^\infty(X)$ be a Cauchy sequence. Then, $f:=\lim_{ n \to \infty }f_{n}$ exists and is bounded. Further, it is measurable by [[Measurable Function|Theorem 1.4]]. Hence, $f\in \mathcal{B}^\infty(X)$.
> 	3. $\left\| fg \right\|=\sup_{x\in X}\left| f(x)g(x) \right|\leq\sup_{x\in X}\left| f(x) \right|\sup_{x\in X}\left| g(x) \right|=\left\| f \right\|\left\| g \right\|$.
> 	4. $\mathcal{B}^\infty(X)$ is an involutive Banach algebra. 
> 	5. Lastly, $$\left\| ff^{*} \right\| =\sup_{x\in X}\left| f(x) \right| ^{2}=(\sup_{x\in X}\left| f(x) \right| )^{2}=\left\| f \right\| ^{2}$$
> 2. We have that: $$\left\| f+N \right\| =\inf_{g\in N}\left\| f+g \right\|_{b} \geq\inf_{g\in N}\left\| f+g \right\| _{\infty}=\left\| f \right\| _{\infty}$$We then define $g\in \mathcal{B}^\infty(X)$: $$g(x)=\begin{cases}-f(x)&f(x)\notin \text{ess im}(f)\\0&\text{otherwise}\end{cases}$$Then, $\left\| f+N \right\|\leq \left\| f+g \right\|_{b}=\left\| f \right\|_{\infty}$.
> 3. By [[Banach Algebra|Proposition 3]], $L^\infty(N)$ is a Banach algebra. Then, we have that: $\left\| f^{*}\right\| _{\infty}=\left\| f \right\|_{\infty}$. 
>    
>    Let $a:\mathbb{C}\to \mathbb{R},z\mapsto \left| z \right|^{2}$. Then, $ff^{*}=a\circ f$. We want to argue that: $$\text{ess im}(ff^{*})=a(\text{ess im}(f))$$For $D_{n}\subseteq \mathbb{C}$ open, as $a$ is continuous, $a^{-1}(D_{n})$ is open and:$$\begin{align}D_{n}\subseteq \mathbb{C} \backslash \text{ess im}(ff^{*})&\iff E((ff^{*})^{-1}(D_{n}))=0\\&\iff E((a\circ f)^{-1}(D_{n}))=0\\&\iff E(f^{-1}(a^{-1}(D_{n})))=0\\&\iff a^{-1}(D_{n})\subseteq \mathbb{C} \backslash \text{ess im}(f)\end{align}$$This proves the statement and: $$\left\| ff^{*} \right\| _{\infty}=\sup_{\lambda\in \text{ess im}(ff^{*})}\left| \lambda \right| =\sup_{\lambda\in \text{ess im}(f)}\left| \lambda \right|^{2} =(\sup_{\lambda\in \text{ess im}(f)}\left| \lambda \right|)^{2} =\left\| f \right\| _{\infty}^{2}$$
> 4. We have that $\lambda\in \text{Sp}_{L^\infty(N)}(f+N)$ if and only if $0\in \text{Sp}_{L^\infty(N)}(f-\lambda+N)$. Further, $0\in \text{ess im}(f-\lambda)$ if and only if $\lambda\in \text{ess im}(f)$. Therefore, it suffices to show that $0\in \text{Sp}_{L^\infty(N)}(f+N)$ if and only if $0\in \text{ess im}(f)$. 

---
> [!lemma] Theorem 6
> For a compact Hausdorff $X$ and a resolution of identity $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$, 
> 1. there exists a $C^{*}$-algebra isomorphism: $\psi:L^\infty(E)\to B\subseteq \mathcal{B}(\mathcal{H})$ onto a sub-$C^{*}$-algebra $B$s.t. $$\braket{ \psi(f)x , y } =\int_{X}^{} f \, dE_{x,y},\quad \forall x,y\in \mathcal{H},f\in L^\infty(E) $$
> 2. $\|\psi(f)x\|^{2}=\int_{X}^{}  \left| f \right|^{2}\, dE_{x,x}$ for all $x\in \mathcal{H}$, $f\in L^\infty(E)$.
> 3. an operator $Q\in \mathcal{B}(\mathcal{H})$ commutes with every $E(\omega)$  if and only if $Q$ commutes with $B$.

> [!proof]-
> We introduce the following notation: $\int_{X}^{} f \, dE:=\psi(f)$. We show:
> 1. We will construct $\psi$ on a dense subset of $\mathcal{B}^\infty(X)$ and extend  
> 	1. **Showing that $\mathcal{S}(X)$ is dense in $\mathcal{B}^\infty(X)$**: 
>    Let $\mathcal{S}(X)\subseteq \mathcal{B}^\infty(X)$ be the set of simple functions, i.e. functions that take finitely many values. Let $\varepsilon>0$ and $f\in \mathcal{B}^\infty(X)$. Then, $f(X)\subseteq \mathbb{C}$ is bounded and we get a finite family of partition $$f(X)\subseteq \bigsqcup_{i,j}^{}D_{i,j}$$ s.t. $D_{i,j}$ is a square of side-length $\varepsilon$. Then, by selecting $z_{i,j}\in D_{i,j}$ for all $i,j$ and $$s_{\varepsilon}:=\sum_{i,j}^{}z_{i,j}\chi_{f^{-1}(D_{i,j})}$$Then, $\|f-s_{\varepsilon}\|_{b}\leq \varepsilon$. 
> 	1. **Showing that $\psi$ exists for $\mathcal{S}(X)$**:
>    Let $s\in \mathcal{S}(X)$ be simple. Then, there is a partition $\bigsqcup_{i=1}^{n}\omega_{i}=X$ with $s=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$. Then, we define:$$\psi(s):=\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})$$which has the property: 
> 	   1. **$\psi$ is linear**: For $s_{1}:=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$ and $s_{2}:=\sum_{j=1}^{m}\beta_{j}\chi_{\xi_{j}}$, let $\eta_{i,j}:=\omega_{i}\cap \xi_{j}$. Then, 
> 	      $$\braket{ \psi(s_{1}+s_{2})x , x } =\sum_{i,j}^{}(\alpha_{i}+\beta_{j})E_{x,x}(\omega_{i}\cap \xi_{j})=\sum_{i}^{}\alpha_{i}E_{x,x}(\omega_{i})+\sum_{j}^{}\beta_{j}E_{x,x}(\xi_{j})$$ which shows the linearity.
> 	   2. **$\psi$ respects the $C^{*}$-algebra structure** as: $$\psi(s)^{*}=\left( \sum_{i=1}^{n}\alpha_{i}E(\omega_{i}) \right) ^{*}=\sum_{i=1}^{n}\overline{\alpha_{i}}E(\omega_{i})=\psi(\overline{s})$$
> 	   3. **$\psi$ is multiplicative**:  Let $s=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$ and $t=\sum_{j=1}^{m}\beta_{j}\chi_{\omega'_{j}}$. Then, $st=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}\chi_{\omega_{i}\cap\omega_{j}'}$ and: $$\psi(st)=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}E(\omega_{i}\cap\omega'_{j})=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}E(\omega_{i})E(\omega'_{j})=\psi(s)\psi(t)$$
> 	  2. **Properties of $\psi$**:
> 	     We have: $$\braket{ \psi(s)x , y } =\left\langle \sum_{i=1}^{n}\alpha_{i}E(\omega_{i})x , y \right\rangle= \sum_{i=1}^{n}\alpha_{i}E_{x,y}(\omega_{i})=\int_{X}^{} \sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}} \, dE_{x,y}=\int_{X}^{}s  \, dE_{x,y}  $$
> 	     Further, $$\left\| \psi(s)x \right\| ^{2}=\braket{ \psi(s)x , \psi(s)x } =\braket{ \psi(s)^{*}\psi(s)x , x }=\braket{ \psi(\left| s \right|^{2} )x ,  x}=\int_{X}^{} \left| s \right| ^{2} \, dE_{x,x}   $$Hence, $\left\| \psi(s)x \right\|^{2}\leq \|s\|_{\infty}^{2}E_{x,x}(X)=\|s\|_{\infty}^{2}\braket{ x , x }=\|s\|^2_{\infty}\|x\|^2$ and $\left\| \psi(s) \right\|\leq \|s\|$.
> 	     
> 	     Furthermore, we have that $\|s\|_{\infty}=\max\{ \left| \alpha_{i} \right|:E(\omega_{i})\neq 0 \}=\left| \alpha_{j_{0}} \right|$ for some $j_{0}$. 
>     
>     
> 		   Then, for $x\in \text{im }E(\omega_{j_{0}})$ and $\|x\|=1$, we get: $$\psi(s)x=\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})x=\alpha_{j_{0}} E(\omega_{j_{0}})x=\alpha_{j_{0}} x$$where for all $i\neq j_{0}$, $E(\omega_{i})x=E(\omega_{i})E(\omega_{j_{0}})x=E(\omega_{i}\cap\omega_{j_{0}})x=0$. Therefore, $$\left\| \psi(s)x \right\| =\left| \alpha_{j_{0}} \right| \|x\|=\left| \alpha_{j_{0}} \right| =\|s\|_{\infty}$$This shows that $\|\psi(s)\|=\|s\|_{\infty}$. 
> 		   
> 	4. **Extending $\psi$:** 
> 	   By the [[Bounded Linear Map|BLT Theorem]], $\psi$ extends to $\psi:\mathcal{B}^\infty(X)\to \mathcal{B}(\mathcal{H})$ s.t. $\|\psi(f)\|=\|f\|_{b}$. 
>  1. We have: $$\braket{ \psi(f)x , y } =\lim_{ k \to \infty }\braket{ \psi(s_{k})x , y } =\lim_{ k \to \infty } \int_{X}^{} s_{k} \, dE_{x,y}  $$where the limit converges for all diagonal coefficients $$\left| \int_{X}^{} f \, dE_{x,x} -\int_{X}^{} s_{k} \, dE_{x,x}  \right|=\left| \int_{X}^{} (f-s_{k}) \, dE_{x,x}  \right|\leq \left\| f-s_{k} \right\| E_{x,x}(X)=\left\| f-s_{k} \right\| \|x\|^{2}\to 0  $$and thereby for every $x,y\in \mathcal{H}$.

- **Notation**: $\int_{X}^{} f \, dE:=\psi(f)\in \mathcal{B}(\mathcal{H})$. 
---
 