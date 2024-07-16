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
> Let $R$ be a UFD. Every non-constant polynomial $f\in R[X]$ can be written as $f(x)=cg(x)$ for $c\in R$ where:
> 1. $c$ is unique up to units in $R$.
> 2. $g$ is [[Polynomial Ring|primitive]] and unique up to units.
> 3. $\deg f=\deg g$

> [!proof]-
> Let $f(x)=a_{0}+a_{1}x+a_{2}x^{2}+\dots+a_{n}x^n$ and let $c:=\text{c}(f)$ the content. Then, $a_{i}=cb_{i}$ for some $b_{i}\in R$ and: $$f(x)=c\cdot \underbrace{ (b_{0}+b_{1}x+b_{2}x^{2}+\dots+b_{n}x^n) }_{ =:g(x) }$$
> $g(x)$ is primitive, as if there is any irreducible $r$ that divides all $b_{i}$s, then $c|cr$, which is the contradiction to the maximality of $c$.
> 
> For uniqueness, suppose $f(x)=dh(x)$ where $h(x)\in R[X]$ is primitive. Any irreducible factor of $c$ must divide $h(x)$ and vice versa. Therefore, $c=du$ for some $u\in R^{\times}$ and $ug(x)=h(x)$ as claimed.
---
> [!lemma] Lemma 3 (Gauss Lemma)
> Let $R$ be a unique factorization domain. Then, 
> 1. if $f,g\in R[X]$ are primitive, $fg$ is primitive.
> 2. for $f,g\in R[X]$, $\text{c}(fg)=\text{c}(f)\cdot \text{c}(g)$.

> [!proof]-
> We have:
> 1. Let $f(x)=a_{0}+a_{1}x+\dots+a_{n}x^n$ and $g(x)=b_{0}+b_{1}x+\dots+b_{m}x^m$ with $a_{n},b_{m}\neq 0$. Then, $$h(x):=f(x)g(x)=c_{0}+c_{1}x+\dots+c_{m+n}x^{m+n}$$For an irreducible $p\in R$, $p$ doesn't divide all $a_{i}$ and all $b_{j}$. Therefore, let $a_{r}$ and $b_{s}$ be the first coefficient not divisible by $p$ respectfully. Then, $$c_{r+s}=(a_{0}b_{r+s}+\dots+a_{r-1}b_{s+1})+a_{r}b_{s}+(a_{r+1}b_{s-1}+\dots+a_{r+s}b_{0})$$and $p$ does not divide $a_{r}b_{s}$, as $p$ is prime. Therefore, $p$ does not divide $c_{r+s}$. 
> 2. From the decomposition, we have that $f=cf'$ and $g=dg'$ for $c,d\in R$. Then, $$fg=cf'dg'=(cd)f'g'$$where $f'g'$ is primitive by 1. Hence $\text{c}(fg)=cd=\text{c}(f)\text{c}(g)$.
---
> [!lemma] Proposition 4 (Polynomials in R[X] and Quot(R)[X])
> Let $R$ be a UFD and $f\in R[X]$ a non-constant polynomial. 
> 1. if $f$ is irreducible in $R[X]$, $f$ is irreducible in $\text{Quot}(R)[X]$. 
> 2. if $f$ is primitive in $R[X]$ then $f$ is irreducible in $\text{Quot}(R)[X]$, then $f$ is irreducible in $R[X]$.

> [!proof]-
> Let $F:=\text{Quot}(R)$. 
> 1. We will show that if $f$ is reducible in $F[X]$, then it is reducible in $R[X]$. If $f$ is reducible in $F[X]$, there exists $g,h\in F[X]$ with $f=gh$ and $\deg(g),\deg(h)<\deg(f)$.
>    
>    Then, from quotient field, there exists $d\in R$ and $g',h'\in R[X]$ s.t. $$f(x)=\frac{g'(x)h'(x)}{d}$$with $\deg g'=\deg g$ and $\deg h'=\deg h$. By Content-Primitive decomposition, there exist $g_{2},h_{2},f_{1}$ primitive and $c,c_{1},c_{2}\in R$ s.t.$$dcf_{1}(x)=df(x)=g'(x)h'(x)=c_{1}c_{2}g_{1}(x)h_{1}(x)$$ where by Gauss lemma, $g_{1}h_{1}$ is primitive as well. Looking at the contents on both sides, we get that $c_{1}c_{2}\sim dc$, i.e. $c_{1}c_{2}=dcu$ and therefore, $$dcf_{1}(x)=df(x)=dcug_{1}(x)h_{1}(x)$$From integral domain, $f(x)=cug_{1}(x)h_{1}(x)$ and $f$ is reducible.
> 2. If $f$ is primitive in $R[X]$ and $f$ is irreducible in $\text{Quot}(R)[X]$ but $f$ is reducible in $R[X]$, Then, $f(x)=g(x)h(x)\subseteq R[X]\subseteq F[X]$ where $\deg(g),\deg(h)<\deg(f)$ as $f$ is primitive. This is a contradiction to the irreducibility in $F[X]$.

---
> [!lemma] Theorem 5 (R and R[X] for R UFD)
> Let $R$ be an integral domain. Then, TFAE:
> 1. $R$ is a UFD 
> 2. $R[X]$ is a UFD.

> [!proof]-
> We have:
> 1. (1=>2): Let $R$ be a UFD and let $f\in R[X]$ s.t. $f\neq 0$ and non-unit. If $\deg(f)=0$, then $f\in R$ and we are done. Suppose $\deg(f)>0$. Then $f(x)\in \text{Quot}(R)[X]$. Let $F:=\text{Quot}(R)$ and as $F$ is a field, $F[X]$ is a PID and hence UFD. Therefore, there exists $p_{1},\dots,p_{r}\in F[X]$ irreducible polynomials s.t. $$f(x)=p_{1}(x)\dots p_{r}(x)$$Hence, there exists $d\in R$ and $q_{1},\dots,q_{r}\in R[X]$ s.t. $$df(x)=q_{1}(x)\dots q_{r}(x)$$
>    As $d\in R\backslash\{ 0 \}\subseteq F \backslash\{ 0 \}$, $d$ is a unit in $F[X]$ and $q_{1},\dots,q_{r}$ are irreducible in $F[X]$. From content-primitive factorization, we have $f',q_{1}',\dots,q_{r}'\in R[X]$ primitives and $c,c_{1},\dots,c_{r}\in R$ s.t. $$dcf'(x)=c_{1}\dots c_{r}q_{1}'(x)\dots q_{r}'(x)$$where by Gauss $q'_{1}\dots q_{r}'$ is primitive as well. Hence, $dcu=c_{1}\dots c_{r}$ for some unit $u\in R$ and $f(x)=cuq'_{1}(x)\dots q_{r}'(x)$. 
>    
>    Then, we notice that $q'_{i}$ is irreducible in $F[X]$. Otherwise, $q'_{i}(x)=a(x)\cdot b(x)$ and $q_{i}(x)=c_{i}a(x)\cdot b(x)$ is reducible. Hence, by Proposition 4.2, $q'_{1},\dots,q_{r}'$ are irreducible in $R[X]$. Further, as $cu\in R$ and $R$ is a UFD, $f(x)$ can be written be factorized into irreducibles in $R[X]$.
>    
>    For uniqueness, we may assume wlog that $f$ is primitive. Otherwise $f=cg$ where $c$ has a unique factorization and $g$ is primitive. Let $f=g_{1}\dots g_{r}=h_{1}\dots h_{s}$ with each irreducible in $R[X]$. As $c(f)=1$, $c(g_{i})=c(h_{j})=1$ by Gauss. By Proposition 4.1, they are also irreducible in $F[X]$. 
>    
>    Since $F[X]$ is a UFD, $r=s$ and the factorizations are unique modulo unit multiplication and reordering. Therefore, $g_{i}=c_{i}h_{i}$ where $c_{i}=a_{i} / b_{i}$ for $a_{i},b_{i}\in R$. As $b_{i}g_{i}=a_{i}h_{i}$ and by uniqueness in Lemma 4, $ub_{i}=a_{i}$ for some $u\in R^{\times}$ and $g_{i}=uh_{i}$, i.e. $g_{i}\sim h_{i}$ in $R[X]$.
>  2. (2=>1): Since $R[X]$ is a UFD, the constant polynomials have to be factored uniquely. However, due to degree concerns, the factorization in $R[X]$ is a factorization in $R$.

---
> [!lemma] Theorem 6 (Eisenstein Criteria)
> Let $R$ be a UFD and let: $f(x)=a_{n}x^n+\dots+a_{1}x+a_{0}\in R[X]$. If $p$ is [[Integral Domain|prime]] in $R$ s.t. 
> 1. $p|a_{i}$ for all $0\leq i<n$
> 2. $p\nmid a_{n}$
> 3. $p^{2}\nmid a_{0}$
>    
>  Then, $f$ is irreducible over $\text{Quot}(R)[X]$. 

> [!proof]-
> Let $F:=\text{Quot}(R)$. If $f$ is not primitive. Then, $f(x)=cf'(x)=c(b_{0}+b_{1}x+\dots+b_{n}x^n)$ by the decomposition and we have that from $p\nmid a_{n}$, $p\nmid c$. Therefore, $p|b_{i}$ for all $0\leq i<n$, $p\nmid b_{n}$ and $p^2\nmid b_{0}$. Moreover, if $f'$ is irreducible in $F[X]$, then $f$ is irreducible in $F[X]$ as well. 
> 
> Hence, wlog we may assume that $f$ is primitive. Assume $f$ is reducible in $F[X]$, i.e. $f=gh$ with $g(x)=b_{0}+b_{1}x+\dots+b_{r}x^r$ and $h(x)=c_{0}+c_{1}x+\dots +c_{s}x^s$ and $0<r,s<n$. 
> 
> From $p|a_{0}=b_{0}c_{0}$ and $p^{2}\nmid a_{0}=b_{0}c_{0}$, we have that $p$ divides $b_{0}$ or $c_{0}$ but not both. Assume $p|b_{0}$ and not $c_{0}$. Further, as $p\nmid a_{n}=b_{r}c_{s}$, $p\nmid b_{r}$. 
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