#Definition #Algebra

> [!definition]
> For a nontrivial commutative [[Ring|ring]] $R$, the ***polynomial ring*** $R[X]$ s.t. $X\notin R$,  is defined through the commutative ring $$\mathcal{F}_{R}:=\{ f:\mathbb{N}\to R\ |\ \exists n_{f}\in \mathbb{N}.\forall k\geq n_{f}.(f(k)=0_{R}) \}$$s.t. we have: $$R[X]:=\left\{  \sum_{i=0}^{\infty}f(i)X^i:f\in \mathcal{F}_{R}  \right\}$$
- **Related definition**: For $p\in R[X]$ with $p=a_{0}+\dots+a_{n}x^n$ with $a_{n}\neq 0$, 
	 1. $\text{deg}(p):=n$ is the ***degree*** of $p$ with $\deg(0)=-\infty$,
	2. $a_{n}$ is the ***leading coefficient*** of $p$ with ***monic*** if $a_{n}=1$.
- **Related definition**: For a [[Unique Factorization Domain|UFD]] $R$ and a polynomial $f\in R[X]$, the ***content*** $c(f)$ of $f$ is the [[Integral Domain|greatest common divisor]] of the coefficients of the polynomial. 
- **Related definition**: a polynomial $f$ is ***primitive*** if $c(f)=1$.
---
##### Properties
> [!lemma] Fact 1
> The natural inclusion: $$\begin{array}{cccc} {\iota:}&{R}&\hookrightarrow&{R[X]}\\&{a} &\mapsto & {a+0X+0X^{2}+\dots} \end{array}{}$$is a [[ring homomorphism]]. Further, $R$ is a [[Subring|subring]] of $R[X]$.

> [!proof]-
> We have that: 
> 1. Addition: $$\iota(a+b)=(a+b)+0X+0X^{2}+\dots=\underbrace{ (a+0X+0X^{2}+\dots) }_{ \iota(a) }+\underbrace{ (b+0X+0X^{2}+\dots) }_{ \iota(b) }$$
> 2. Multiplication holds analogously to 1.
> 3. Identity: $$\iota(1_{R})=1_{R}+0X+0X^{2}+\dots=1_{R[X]}$$
---
> [!lemma] Theorem 2 (Universal Property)
> Let $R,S$ be commutative rings, $\varphi:R\to S$ a ring homomorphism and $s_{0}\in S$.  Then, there exists a uniquely determined ring homomorphism $\varphi_{s_{0}}:R[X]\to S$ s.t.
> 1. $\varphi_{s_{0}}|_{R}=\varphi$
> 2. $\varphi_{s_{0}}(X)=s_{0}$
> 
> In other words, 
> ```tikz
> \usepackage{tikz-cd}
> \begin{document}
> \begin{tikzcd}
> R\arrow[r,"\varphi"]\arrow[d,"\iota"]&S\\
> R[X]\arrow[ru,swap,"\varphi_{s_0}"]
> \end{tikzcd}
> \end{document}
> ```
> commutes.

> [!proof]-
> We define: $$\begin{array}{cccc} {\varphi_{s_{0}}:}&{R[X]}&\to&{S}\\&{a_{0}+a_{1}X+\dots+a_{n}X^n} &\mapsto & {\varphi(a_{0})+\varphi(a_{1})s_{0}+\dots+\varphi(a_{n})s_{0}^n} \end{array}{}$$
> Then, $\varphi_{s_{0}}$ is a ring homomorphism as: 
> 1. additivity and multiplicativity is obvious.
> 2. $\varphi_{s_{0}}(1_{R[X]})=\varphi_{s_{0}}(1_{R})=\varphi(1_{R})=1_{S}$.
> 3. $\varphi_{s_{0}}|_{R}=\varphi$ and
> 4. $\varphi_{s_{0}}(X)=\varphi_{s_{0}}(1_{R}X)=1_{S}\cdot s_{0}=s_{0}$.
---
> [!lemma] Corollary 3
> Let $S$ be a commutative ring with a subring $R\subseteq S$ and $s_{0}\in S$. Then, there exists an ideal $\mathfrak{a}_{s_{0}}\subseteq R[X]$ s.t. $\mathfrak{a}_{s_{0}}\cap R=\{ 0 \}$ and $$R[X] / \mathfrak{a}_{s_{0}}\cong R[s_{0}]$$

> [!proof]-
> Let $\varphi=\iota:R \hookrightarrow S$ and $\varphi_{s_{0}}$ defined in Theorem 2. Then, $$\varphi_{s_{0}}[R[X]]=R[s_{0}]$$and $R[X] / \text{ker }\varphi_{s_{0}}\cong R[s_{0}]$. If we let $\mathfrak{a}_{s_{0}}:=\text{ker }\varphi_{s_{0}}$, then: $$\mathfrak{a}_{s_{0}}\cap R=\{ a\in R:\varphi_{s_{0}}(a)=0 \}=\{ a\in R:\varphi(a)=0 \}=\{ 0 \}$$
---
> [!lemma] Fact 4
> For $p,q\in R[X]$, it holds that: 
> 1. $\text{deg}(p+q)\leq \max\{ \text{deg}(p),\text{deg}(q) \}$
> 2. $\text{deg}(pq)\leq \text{deg}(p)+\text{deg}(q)$ with equality for [[Integral Domain|integral domains]].
> 3. Let $a$ and $b$ be the leading coefficients of $p$ and $q$ respectively. If $ab\neq 0$, then $\text{deg}(pq)= \text{deg}(p)+\text{deg}(q)$
---
> [!lemma] Theorem 5 (Euclidean Algorithm)
> Let $f,g\in R[X]$, where $g\neq 0$ with leading coefficient $b_{m}$. Then, 
> 1. there exists $q,r\in R[X]$ with $\text{deg}(r)<\text{deg}(g)$ and $k\in \mathbb{N}$ s.t. $$b_{m}^k\cdot f=q\cdot g+r$$
> 2. if $R$ is a field, there exists $q,r\in R[X]$ with $\deg(r)<\deg(g)$ with $f=q\cdot g+r$.

> [!proof]-
> We have:
> 1. Proof with induction over $\text{deg}(f)=:n$.
> 	1. If $\deg(f)<\deg(g)$, then, $b^0_{m}\cdot f=f=0\cdot q+f$.
> 	3. If $\text{deg}(f)\geq \text{deg}(g)=:m$, then let:$$\begin{align}f_{1}&:=b_{m}\cdot f-a_{n}x^{n-m}g\\&=b_{m}\cdot a_{0}+b_{m}a_{1}X+\dots+\cancel{ b_{m}a_{n}X^n }-a_{n}b_{0}X^{n-m}-a_{n}b_{1}X^{n-m+1}-\dots-\cancel{ a_{n}b_{m}X^{n} }\end{align}$$Therefore, $\text{deg}(f_{1})<\text{deg}(f)$. Therefore, from induction hypothesis, there exists $q_{1},r_{1}\in R[X]$ with $\text{deg}(r_{1})<\text{deg}(g)$ and $k_{1}\in \mathbb{N}$ s.t. $$b_{m}^{k_{1}}\cdot f_{1}=q_{1}\cdot g+r_{1}$$Indeed,
> 	$$q_{1}\cdot g+r_{1}=b_{m}^{k_{1}}\cdot f_{1}=b_{m}^{k_{1}+1}\cdot f-b_{m}^{k_{1}}a_{m}x^{n-m}g$$Therefore, by $k:=k_{1}+1$, $$b_{m}^k\cdot f=\underbrace{ \left( b^{k_{1}}_{m}a_{m}x^{n-m}+q_{1} \right) }_{ =:q } g+r_{1}=q\cdot g+r$$with $r_{1}=r$. 
> 2. If $R$ is a field, as $b_{m}\neq 0$, we have $c:=b_{m}^{-1}\in R$ and: $$f=(c^k\cdot q)g+(c^k\cdot r)$$with $\deg(c^k\cdot r)=\deg(c^k)+\deg(r)=\deg(r)<\deg(g)$. It is also unique as if $q',r'$ also satisfy it, then: $$(q'-q)g+(r'-r)=0$$and as $\deg((q'-q)g)=\deg(q'-q)+\deg(g)$ and $\deg(g)>\deg(r)>\deg(r'-r)$, we have that $(q'-q)=0$. Consequently, we have that $r'=r$.
---
> [!lemma] Corollary 6
> For $f\in R[X]$ and $a\in R$,
> 1. there exists a uniquely determined $q\in R[X]$ s.t. $f(x)=q(x)(x-a)+f(a)$.
> 2. $(x-a)|f \iff f(a)=0$.

> [!proof]-
> We show that:
> 1. **Existence of $q$**: Let $g(x):=x-a$. Then, $\text{deg}(g)=1$ and the leading coefficient is $b_{1}=1$. Therefore, from the Euclidean algorithm, there exists $s,r\in R[X]$ s.t. $$f(x)=s(x) (x-a)+r(x)$$where $\text{deg}(r)<1$ ($r=0$ or $\text{deg}(r)=0$).
> 
> 	By plugging in, we have: $$f(a)=s(a)(a-a)+r(a)=r(a)$$
> 	However, as $r\in R$, we have that $f(x)=q(x)(x-a)+f(a)$.
> 2. **Uniqueness of $q$**: Let $q'\in R[X]$ s.t. $f(x)=q'(x)(x-a)+f(a)$. Then, $$(x-a)(q'-q)=0$$Therefore, $q'=q$.
> 3. Follows from 1 and 2.
---
> [!lemma] Lemma 7
> A polynomial of degree 2 or 3 over a field $F$ is reducible if and only if it has a root in $F$.

> [!proof]-
> A polynomial of degree 2 or 3 over a field $F$ is reducible if and only if the polynomial has at least one linear factor. This is equivalent to the polynomial having a root.
---
##### Examples
> [!h] Example 1
> Let $p$ be a prime and $f=\sum_{i=0}^{n}a_{i}x^i\in \mathbb{Z}[X]$ be a primitive polynomial. Assume $p\nmid a_{n}$. Then, define: $$\overline{f}:=\sum_{i=0}^{n}\overline{a_{i}}x^i\in (\mathbb{Z} / p\mathbb{Z})[X]$$
> If $\overline{f}$ is irreducible in $(\mathbb{Z} / p\mathbb{Z})[X]$, it is irreducible in $\mathbb{Z}[X]$ (and thereby in $\mathbb{Q}[X]$).

> [!proof]-
> Suppose $f\in\mathbb{Z}[X]$ is irreducible. Then, $f=gh$ where $\deg g,\deg h<n$. Then, $\overline{f}=\overline{g}\overline{h}$ with $\deg \overline{f}=n$ and $\deg \overline{g},\deg \overline{h}\geq 1$. Therefore, $\overline{f}$ is reducible in $(\mathbb{Z} / p\mathbb{Z})[X]$.
---
> [!h] Example 2
> Let $f(x)=\sum_{i=0}^{n}a_{i}x^i\in \mathbb{Z}[X]$. If $r /s \in \mathbb{Q}$ with $(r,s)=1$ is a root of $f(x)$  then $r|a_{0}$ and $s|a_{n}$. In particular, if $f(x)$ is monic and if for all $d|a_{0}$, $f(d)\neq 0$ then $f$ has no zeros in $\mathbb{Q}$.

> [!proof]+
> 