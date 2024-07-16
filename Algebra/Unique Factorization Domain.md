#Definition #Algebra 

> [!definition]
> Let $R$ be an [[integral domain]]. $R$ is a ***unique factorization domain (UFD)***, if every $r\in R\backslash\{ 0 \}$ and $r\notin R^{\times}$ has the following properties:
> 1. $r$ can be written as a product of [[Integral Domain|irreducibles]]: $r=s_{1}\dots s_{n}$ where the decomposition is unique up to associates and renumbering.
- **Remark**: In a UFD $R$, $a,b\in R$ with $a=up_{1}^{e_{1}}\dots p_{n}^{e_{n}},b=vp_{1}^{f_{1}}\dots p_{n}^{f_{n}}$ with $e_{i},f_{i}\geq 0$ and $u,v\in R^{\times}$, $$\text{gcd}(a,b)=p_{1}^{\min\{ e_{1},f_{1} \}}\dots p_{n}^{\min\{ e_{n},f_{n} \}}$$However, $\text{gcd}(a,b)$ is not necessarily a linear combination of $a,b$ (compare it with [[Principal Ideal Domain|Theorem 2]])
- **Remark**: $\mathbb{Z}[2i]$ is an integral domain that is not a UFD.
- **Related definition**: Let $R$ be a UFD and $f\in R[X]$ with $\deg(f)\geq 1$. Then, for $f(x)=a_{0}+\dots+a_{n}x^n$, the ***content*** of $f$ is given by $\text{c}(f):=\gcd(a_{0},\dots,a_{n})$.
- **Related definition**: If $\text{c}(f)=1$, $f$ is ***primitive***.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a unique factorization domain and let $0\neq x\in R$. Then, TFAE:
> 1. $r$ is prime.
> 2. $r$ is irreducible.
> 3. $(r)$ is a prime ideal.

> [!proof]-
> We have that:
> 1. (1=>2): Every prime element is irreducible by [[Integral Domain|Lemma 2]]. 
> 2. (2=>1): Let $r$ be irreducible and $a,b\in R$ s.t. $r|ab$, i.e. $rc=ab$ for some $c\in R$.
> 	1. if $a\in R^\times$ or $b\in R^\times$, then wlog assume $a\in R^\times$ and  $rca^{-1}=b$ and $r|b$.
> 	2. if $a,b\notin R^\times$ and $c=0$, then $ab=0$ and as $R$ is an ID, either $a=0$ or $b=0$, therefore, either $r|a$ or $r|b$.
> 	3. if $a,b\notin R^\times$ and $c\in R^\times$, then by unique factorization, we have $a=p_{1}\dots p_{n}$ and $b=q_{1},\dots,q_{m}$. Therefore, $$r=c^{-1}p_{1}\dots p_{n}q_{1}\dots q_{m}$$As $r$ is irreducible, we have that $r\sim p_{i}$ or $r\sim q_{j}$ for some $i,j$. Therefore, $r|a$ or $r|b$. 
> 	4. if $a,b,c\notin R^\times$ and $c\neq 0$, then by unique factorization, $a=p_{1}\dots p_{n}$, $b=q_{1}\dots q_{m}$ and $c=\ell_{1}\dots \ell_{k}$. Then, $$r \ell_{1}\dots \ell_{k}=p_{1}\dots p_{n}q_{1}\dots q_{m}$$and by unique factorization, $r\sim p_{i}$ or $r\sim q_{j}$. Therefore, $r|a$ or $r|b$.
> 3. (1=>3): By [[Integral Domain|Lemma 2]]
> 4. (3=>1): By [[Integral Domain|Lemma 2]]

- **Remark**: Unlike in PIDs, not every non-zero prime ideals are maximal ideals in UFD, e.g. $(X)\subseteq \mathbb{Z}[X]$
	1. $(X)$ is prime: $\mathbb{Z}[X]  / (X)\cong \mathbb{Z}$ which is an integral domain.
	2. $(X)$ is not maximal: $(X)\subsetneq(2,X)\subsetneq \mathbb{Z}[X]$ or $\mathbb{Z}[X]  / (X)\cong \mathbb{Z}$ is not a field.
---
> [!lemma] Lemma 2 (Content-Primitive Decomposition)
> Let $R$ be a UFD. Every non-constant polynomial $f\in R[X]$ can be written as $f=cg$ where:
> 1. $c$ is unique up to units in $R$.
> 2. $g$ is [[Polynomial Ring|primitive]] and unique up to units.
> 3. $\deg f=\deg g$

> [!proof]+
> Let $f(x)=a_{0}+a_{1}x+a_{2}x^{2}+\dots+a_{n}x^n$ and let $c:=\text{c}(f)$ the content. Then, $a_{i}=cb_{i}$ for some $b_{i}\in R$ and: $$f(x)=c\cdot (b_{0}+b_{1}x+b_{2}x^{2}+\dots+b_{n}x^n)$$
> $g(x)$ is primitive, as if there is any irreducible $r$ that divides all $b_{i}$s, then $c|cr$, which is the contradiction to the maximality of $c$.
> 
> For uniqueness, suppose $f(x)=dh(x)$ where $h(x)\in R[X]$ is primitive. Any irreducible factor of $c$ must divide $h(x)$ and vice versa. Therefore, $c=du$ for some $u\in R^{*}$ and $ug(x)=h(x)$ as claimed.
---
> [!lemma] Lemma 5 (Gauss' Lemma)
> Let $R$ be a unique factorization domain. Then, the product of two primitive polynomials in $R[X]$ is primitive.

> [!proof]-
> Let $f(X)=a_{0}+a_{1}X+\dots +a_{n}X^n$ and $g(X)=b_{0}+b_{1}X+\dots+b_{m}X^m$ for $a_{n},b_{m}\neq 0$ be two primitives. Let $$h(X):=f(X)g(X)=c_{0}+c_{1}X+\dots+c_{m+n}X^{m+n}$$Let $p\in R$ be an irreducible. Then, $p$ doesn't divide all $a_{i}$s and it doesn't divide all $b_{j}$s. Let $a_{r}$ be the first coefficient not divisible by $p$. Similarly, let $b_{s}$ be the first coefficient not divisible by $p$. Then, $$c_{r+s}=(a_{0}b_{r+s}+\dots+a_{r-1}b_{s+1})+a_{r}b_{s}+(a_{r+1}b_{s-1}+\dots+a_{r+s}b_{0})$$and $p$ does not divide $a_{r}b_{s}$. Therefore, $p$ does not divide $c_{r+s}$.
---
> [!lemma] Proposition 6
> Let $R$ be a unique factorization domain and $F:=\text{Quot}(R)$ the [[quotient field]] of $R$. Let $f(x)\in R[X]$ with $\deg f>0$. If $f$ is irreducible in $R[X]$, then $f$ is irreducible in $F[X]$. 
> 
> Moreover, if $f$ is primitive in $R[X]$ and irreducible in $F[X]$, then $f$ is irreducible in $R[X]$.

> [!proof]-
> We will prove the contrapositive. Suppose $f(x)\in R[X]\subseteq F[X]$ is a product of lower degree polynomials in $F[X]$, i.e. $f(x)=r(x)s(x)$ for $r(x),s(x)\in F[X]$ and $\deg r<\deg f$ and $\deg s<\deg f$. 
> 
> Then, from quotient field, there exists $d\in R$ and $r_{1},s_{1}\in R[X]$ s.t. $$f(x)=\frac{r_{1}(x)s_{1}(x)}{d}$$with $\deg r_{1}=\deg r$ and $\deg s_{1}=\deg s$. By Lemma 4, we have $r_{2},s_{2},g\in R[X]$ primitives and $c,c_{1},c_{2}\in R$ s.t. $$df(x)=dcg(x)=c_{1}c_{2}r_{2}(x)s_{2}(x)$$where by Gauss' lemma $r_{2}s_{2}$ is primitive as well. Looking at the contents on both sides, $c_{1}c_{2}=dcu$ for some unit $u\in R$. Therefore, $$f(x)=cg(x)=cur_{2}(x)s_{2}(x)$$ This shows that $f$ is reducible. 
> 
> If $f$ is primitive and was reducible, then $f(x)=r(x)s(x)\subseteq R[X]\subseteq F[X]$ which is a contradiction.
- For non-primitive $f\in R[X]$, $f(x)$ can be reducible in $R[X]$ and irreducible in $F[X]$, e.g. $5x\in \mathbb{Z}[X]$ and $\mathbb{Q}[X]$.
---

> [!lemma] Lemma 7
> Let $R$ be an integral domain. Then, $R$ is a unique factorization domain if and only if $R[X]$ is a unique factorization domain.

> [!proof]-
> We have: 
> 1. Since $R[X]$ is a UFD, the constant polynomials have to be factored uniquely. However, due to degree concerns, the factorization in $R[X]$ is a factorization in $R$.
> 2. Let $R$ be a UFD and let $f\in R[X]$, $f\neq 0$ and non-unit. If $\deg f=0$, we are done. Suppose $\deg f>0$. Then, $f(x)\in F[X]$. As $F$ is a field $F[X]$ is a PID, hence UFD and there exists $p_{1},\dots,p_{r}\in F[X]$ irreducibles s.t. $$f(x)=p_{1}(x)\dots p_{r}(x)$$Therefore, there exists $d\in R$ and $q_{1},\dots,q_{r}\in R[X]$ s.t. $$df(x)=q_{1}(x)\dots q_{r}(x)$$As $d$ is a unit in $F[X]$, $q_{1},\dots,q_{r}$ are irreducible in $F[X]$.  Therefore, by Lemma 4, there exists $c,c_{i}\in R$ and primitive $g,q'_{i}\in R[X]$ s.t. $$df(x)=dcg(x)=c_{1}\dots c_{r}q'_{1}(x)\dots q'_{r}(x)$$Using Gauss' lemma, there exists a unit $u\in R$ s.t. $udc=c_{1}\dots c_{r}$. Therefore, $$f(x)=cuq'_{1}(x)\dots q'_{r}(x)$$As $cu\in R$ and $R$ is a UFD, $f(x)$ can be factorized into irreducibles. 
>    
>    For uniqueness, we may assume wlog that $f$ is primitive. Otherwise $f=cg$ where $c$ has a unique factorization and $g$ is primitive. Let $f=g_{1}\dots g_{r}=h_{1}\dots h_{s}$ with each irreducible in $R[X]$. As $c(f)=1$, $c(g_{i})=c(h_{j})=1$. By Proposition 6, they are also irreducible in $F[X]$. 
>    
>    Since $F[X]$ is a UFD, $r=s$ and the factorizations are unique modulo unit multiplication and reordering. Therefore, $g_{i}=c_{i}h_{i}$ where $c_{i}=a_{i} / b_{i}$ for $a_{i},b_{i}\in R$. As $b_{i}g_{i}=a_{i}h_{i}$ and by uniqueness in Lemma 4, $ub_{i}=a_{i}$ for some $u\in R^{*}$ and $g_{i}=uh_{i}$, i.e. $g_{i}\sim h_{i}$ in $R[X]$.
---
> [!lemma] Theorem 8 (Eisenstein Criteria)
> Let $R$ be a unique factorization domain with $F:=\text{Quot}(R)$ and let: $$f(x)=a_{n}x^n+\dots+a_{1}x+a_{0}\in R[X]$$If $p$ is [[Integral Domain|prime]] in $R$ s.t. 
> 1. $p|a_{i}$ for all $0\leq i<n$
> 2. $p\nmid a_{n}$
> 3. $p^{2}\nmid a_{0}$
>    
>  Then, $f$ is irreducible over $F[X]$. 

> [!proof]-
> If we define $f$ with its content, then $f=cf'$ and the assertion is valid for $f'$ as well, as $p\nmid a_{n}$ and therefore $p \nmid c$. Therefore, wlog we may assume that $f$ is primitive.
> 
> Assume $f$ is reducible, i.e. $f=gh$ with $g(x)=b_{0}+b_{1}x+\dots+b_{r}x^r$ and $h(x)=c_{0}+c_{1}x+\dots+c_{s}x^s$. If $r=0$ or $s=0$, then as $f$ is primitive, $b_{0}$ or $c_{0}$ is a unit. Therefore, we can assume that $r,s\geq 1$. 
> 
> From $p|a_{0}=b_{0}c_{0}$ and $p^{2}\nmid a_{0}=b_{0}c_{0}$, we have that $p$ divides either $b_{0}$ or $c_{0}$ but not both. Assume $p|b_{0}$ and $p\nmid c_{0}$. Further, as $p\nmid a_{n}=b_{r}c_{s}$, $p\nmid b_{r}$. 
> 
> Now, let $i$ be the smallest index s.t. $p\nmid b_{i}$ where $1\leq i\leq r<n$. Then, consider: $$a_{i}=b_{0}c_{i}+b_{1}c_{i-1}+\dots+b_{i-1}c_{1}+b_{i}c_{0}$$Then, as $p|a_{i}$ and $p|b_{j}c_{i-j}$ for all $j<i$, $p|b_{i}c_{0}$ and $p|c_{0}$ which is a contradiction.
---
##### Examples
> [!h] Example 1
> For a primitive $f\in \mathbb{Z}[X]$ and $a\in \mathbb{Z}$, $f$ is irreducible in $\mathbb{Z}[X]$ if and only if $f(x+a)$ is irreducible in $\mathbb{Z}[X].$
---
> [!h] Example 2
> The $p$-th cyclotomic polynomial is defined as: $$\Phi_{p}(x):=\frac{x^p-1}{x-1}=x^{p-1}+x^{p-2}+\dots+x+1$$Then, $\Phi_{p}(x)$ is irreducible in $\mathbb{Z}[X]$. 

> [!proof]-
> Using Eisenstein on $\Phi_{p}(x+1)$, we get: $$\Phi_{p}(x+1)=\frac{(x+1)^p-1}{x}=x^{p-1}+px^{p-2}+\dots{p\choose i}x^{i-1}+\dots+p$$and by using Eisenstein with $p$. 