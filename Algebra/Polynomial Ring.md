#Definition #Algebra

> [!definition]
> For a nontrivial commutative [[Ring|ring]] $R$, the ***polynomial ring*** $R[X]$ s.t. $X\notin R$,  is defined through the commutative ring $$\mathcal{F}_{R}:=\{ f:\mathbb{N}\to R\ |\ \exists n_{f}\in \mathbb{N}.\forall k\geq n_{f}.(f(k)=0_{R}) \}$$s.t. for $f\in \mathcal{F}_{R}$, we represent: $$f = \sum_{i=0}^{\infty}f(i)\cdot X^i\in R[X]$$
> For $p\in R[X]$, $p=a_{0}+\dots+a_{n}X^n$ with $a_{n}\neq 0$, we have: 
> 1. $\text{deg}(p):=n$ is the ***degree*** of $p$,
> 2. $a_{n}$ is the ***leading coefficient*** of $p$,
> 
> If $a_{n}=1$, then $p$ is ***normalized***. If $p=0$, then $\text{deg}(p)=-\infty$.
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
> Let $p,q\in R[X]$, where $q\neq 0$ with leading coefficient $b_{m}$. Then, there exists $s,r\in R[X]$ with $\text{deg}(r)<\text{deg}(q)$ and $k\in \mathbb{N}$ s.t. $$b_{m}^k\cdot p=s\cdot q+r$$

> [!proof]-
> Proof with induction over $\text{deg}(p)=:n$.
> 1. If $\text{deg}(p)<\text{deg}(q)$, then: $$b_{m}^0\cdot p=p=0\cdot q+p$$
> 2. If $\text{deg}(p)\geq \text{deg}(q)=:m$, then:$$\begin{align}p_{1}&:=b_{m}\cdot p-a_{n}X^{n-m}q\\&=b_{m}\cdot a_{0}+b_{m}a_{1}X+\dots+\cancel{ b_{m}a_{n}X^n }-a_{n}b_{0}X^{n-m}-a_{n}b_{1}X^{n-m+1}-\dots-\cancel{ a_{n}b_{m}X^{n} }\end{align}$$Therefore, $\text{deg}(p_{1})<\text{deg}(p)$. Therefore, from induction hypothesis, there exists $s_{1},r_{1}\in R[X]$ with $\text{deg}(r_{1})<\text{deg}(q)$ and $k_{1}\in \mathbb{N}$ s.t. $$b_{m}^{k_{1}}\cdot p_{1}=s_{1}\cdot q+r_{1}$$Indeed,
> 	$$s_{1}\cdot q+r_{1}=b_{m}^{k_{1}}\cdot p_{1}=b_{m}^{k_{1}+1}\cdot p-b_{m}^{k_{1}}a_{m}X^{n-m}q$$Therefore, by $k:=k_{1}+1$, $$b_{m}^k\cdot p=\underbrace{ \left( b^{k_{1}}_{m}a_{m}X^{n-m}+s_{1} \right) }_{ =:s } q+r_{1}=s\cdot q+r$$with $r_{1}=r$. 
---
> [!lemma] Corollary 6
> For $p\in R[X]$ and $a\in R$,
> 1. there exists a uniquely determined $s\in R[X]$ s.t. $$p=s(X-a)+p(a)$$
> 2. $(X-a)|p \iff p(a)=0$

> [!proof]-
> We show that:
> 1. Existence of $s$: Let $q=X-a$. Then, $\text{deg}(q)=1$ and the leading coefficient is $b_{1}=1$. Therefore, from the Euclidean algorithm, there exists $s,r\in R[X]$ s.t. $$p=s\cdot (X-a)+r$$where $\text{deg}(r)<1$ ($r=0$ or $\text{deg}(r)=0$).
> 
> 	By plugging in, we have: $$p(a)=s(a)(a-a)+r(a)=r(a)$$
> 	However, as $r\in R$, we have that $p=s(X-a)+p(a)$.
> 2. Uniqueness of $s$: Let $\tilde{s}\in R[X]$ s.t. $p=\tilde{s}(X-a)+p(a)$. Then, $$(X-a)(\tilde{s}-s)=0$$Therefore, $s=\tilde{s}$.
> 3. Follows from 1 and 2.
---
