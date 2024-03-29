#Series #Algebra 

> [!definition] Problem 1
> Let $R$ be a principal ideal domain. 
> 1. Show that every ascending chain of ideals, $I_{1}\subseteq I_{2}\subseteq\dots$ , eventually become stationary. In other words, there is a positive index $n$ such that $I_{k}=I_{n}$ for all $k\geq n$. 
> 2. Show that every irreducible element is a prime element.

We have:
1. Let $\{ I_{k} \}_{k}$ be an ascending chain of ideals. We claim that $I:=\bigcup_{k=1}^{\infty}I_{k}$ is an ideal. For $x,y\in I$, there exists $a,b\geq 1$ s.t. $x\in I_{a}$ and $y\in I_{b}$. Then, $x-y\in I_{\max\{ a,b \}}\subseteq I$. Similarly, for $r\in R$, $rx\in I_a\subseteq I$. 
   
   This means, $I=(x)$ for some $x\in R$ as $R$ is a PID. Therefore, there exists $n\geq 1$ s.t. $x\in I_{n}$. Hence, for any $k\geq n$, $x\in I_{k}$ and therefore, $I=(x)\subseteq I_{k}\subseteq I$. This shows that $I_{k}=I_{n}=I$ for all $k\geq n$.
3. Let $r\in R$ be irreducible. Then, $(r)$ is maximal and therefore prime. As $r\neq 0$, this means that $r$ is prime.
---
> [!def] Problem 2
> Show that every principal ideal domain is a unique factorization domain.

Let $R$ be a PID and we define a poset with respect to inclusion:
$$\mathcal{I}:=\{ (r)\subseteq R:r\neq 0,r\notin R^{*},r \text{ has a factorization} \}$$
Then, we will use Zorn's lemma to show that there is a maximal element in $\mathcal{I}$. Let $\{ (r_{n}) \}_{n}\subseteq \mathcal{I}$ be an ascending chain. From 1, we know that there is $n\geq 1$ s.t. $(r_{k})=(r_{n})$ for all $k\geq n$. Therefore, $(r_{n})$ is the upper bound. Indeed, now we can use the Zorn's lemma to find a maximal element $(m)\in \mathcal{I}$. 

As $m$ is not irreducible by definition, $(m)$ is not maximal and there exists $q\in R$ s.t. $(m)\subsetneq (q)\subsetneq R$. Then, $q|m$ and  by assumption, $(q)\notin \mathcal{I}$. This means there exists an irreducible $a\in R$ s.t. $a|q$ and therefore, $$m=ab$$for some $b\in R$. If $(b)\notin \mathcal{I}$, then we have the following possibilities.
1. $b\in R^{*}$ and $m\sim a$ and $(m)=(a)\in \mathcal{I}$ which is a contradiction as $a$ is irreducible.
2. $b$ has a factorization, which is a contradiction as $m$ doesn't have a factorization.

Therefore, $(b)\in \mathcal{I}$. However, this is also a contradiction to the maximality of $(m)$ as $m\in (b)$ and $(m)\subsetneq(b)$ as $a\notin R^{*}$. 

To prove that the factorization is unique, assume that for any $r\neq 0$, $r\notin R^{*}$:$$r=p_{1}\dots p_{n}=q_{1}\dots q_{m}$$where $p_{i},q_{j}$ are irreducibles and thereby primes. Indeed, $p_{1}|q_{1}\dots q_{m}$ and modulo reordering, $p_{1}|q_{1}$ and $(q_{1})\subseteq(p_{1})$. However, from the maximality of $(q_{1})$, $p_{1}\sim q_{1}$, i.e. $p_{1}=sq_{1}$ where $s\in R^{*}$. As $R$ is an integral domain and $q_{1}\neq 0$, $sp_{2}\dots p_{n}=q_{2}\dots q_{m}$. This proves the uniqueness.

---
> [!def] Problem 3
> Consider the ring $R:=\mathbb{Z}[i]\subseteq\mathbb{C}$ with the so called field norm:$$\begin{array}{cccc} {N:}&{R}&\to&{\mathbb{Z}_{\geq0}}\\&{a+bi} &\mapsto & {a^{2}+b ^{2}} \end{array}{}$$
> 1. Prove that $R$ is a Euclidean domain with respect to $N$.
> 2. Determine $\gcd(3-i,3+i)$ and $\gcd(2-i,2+i)$ in $R$.
> 3. Write $3+i$ as a product of prime elements from $R$.
> 4. Prove that each prime element of $R$ divides exactly one prime number $p\in \mathbb{Z}$.
> 5. Prove that each prime number $p\equiv 3\mod 4$ is a prime element of $R$.

We have: 
1. Let $a=a_{1}+a_{2}i,b=b_{1}+b_{2}i\in R \backslash \{ 0 \}$. Indeed $bi=-b_{2}+b_{1}i$ and $b$ and $bi$ are orthogonal in $\mathbb{C}$. Therefore, $B:=\{ qb:q\in \mathbb{Z}[i] \}$ is a square grid of side length $N(b)$, rotated by $b$. Now consider $B_{<N(b)}(a)$ in $\mathbb{C}$. Then, there exists $x\in B \cap B_{<N(b)}(a)$ and $q\in\mathbb{Z}[i]$ s.t. $qb=x$. Let $r=a-bq$. Then, surely $a=bq+r$ and: $$N(r)=N(a-bq)=N(a-x)<N(b)$$Therefore, $R$ is a euclidean domain.
2. We have: $$\begin{align}3-i&=(3+i)-2i\\3+i&=i(-2i)+(1+i)\\-2i&=(-1-i)(1+i)\end{align}$$Therefore, $\gcd(3-i,3+i)=1+i$. Similarly, $$\begin{align}2-i&=(2+i)-2i\\2+i&=i(-2i)+i\\-2i&=(-2)i\end{align}$$Therefore, $\gcd(2-i,2+i)=i$.
3. We have that: $3+i=(1+2i)(1-i)$. Then, notice that $N$ is multiplicative. Therefore, $(1+2i)$ is irreducible, as $N(1+2i)=5$ and if $1+2i=ab$, either $N(a)=1$ or $N(b)=1$. However, any $x\in R$ with $N(x)=1$ is a unit. Analogously we can show that $1-i$ is irreducible. As $R$ is euclidean and therefore a PID, this means that $1+2i$ and $1-i$ are primes.
4. Firstly, we show that $R^{*}=\{ z\in R:N(z)=1 \}=\{ 1,-1,i,-1 \}$. Let $z\in R^{*}$. Then, $N(z)N(z^{-1})=1$, which implies that $N(z)=1$. On the other hand, one can easily check that $\{ 1,-1,i,-1 \}$ are all units. 

   Now, let $x\in R$ be prime. Then, $N(x)>2$ and there exists a prime factorization of $N(x)=p_{1}\dots p_{n}$ over the integers, as $\mathbb{Z}$ is a UFD, where $p_{1},\dots,p_{n}$ are primes. Indeed, $N(x)=x \overline{x}$ and as $x$ is prime, there exists $i\in [n]$ s.t. $x|p_{i}$. This shows the existence.
   
   For uniqueness, assume $x|p$ and $x|q$ where $p\neq q$ are primes. Then, $N(x)|p^{2}$ and $N(x)|q^{2}$. But at $\gcd(p^{2},q^{2})=1$, $N(x)=1$ which is a contradiction as $x$ is non-unit.
5. Firstly, we notice that there is no $a,b\in \mathbb{Z}$ s.t. $a^{2}+b ^{2}=3\mod 4$. By taking modulo 4 on both sides, we would have $a^{2}+b ^{2}=3$ for $a,b\in \mathbb{Z} / 4\mathbb{Z}$. However, as $z^{2}\in \{ 0,1 \}$ in $\mathbb{Z} / 4\mathbb{Z}$, this is not possible, i.e. there is no $x\in R$ s.t. $N(x)=3\mod{4}$.
   
   Now, for any prime $p\equiv 3 \mod 4$, assume $p$ is not a prime/irreducible in $R$. Then, there are $r,s\notin R^{*}$ s.t. $p=rs$ and $p^{2}=N(p)=N(r)N(s)$. Then, as $N(r),N(s)\neq 1$, $N(r)=N(s)=p$, which is a contradiction.
---
> [!def] Problem 4
> Solve:
> 1. Let $R$ be a ring with unique factorization. Prove: if $a,b,c\in R$ are nonzero, $ab=c^n$  and $\gcd(a,b)=1$, then there are units $u,v\in R$ as well as elements $a',b'\in R$, s.t. $a=ua'^n$ and $b= vb'^n$.
> 2. There are counterexamples to the conclusion of (a) if we drop the the hypothesis that $R$ has unique factorization. Use $R=\mathbb{Z}[\sqrt{ -26 }]$ to give such a counterexample.

Assuming a ring with unique factorization means a UFD: 
1. As $a,b,c$ are non-zero, we can write them as:
	1. $a=up_{1}\dots p_{\alpha}$ where $u\in R^{*}$ and $p_{1},\dots,p_{\alpha}$ are irreducibles.
	2. $b=vq_{1}\dots q_{\beta}$ where $v\in R^{*}$ and $q_{1},\dots,q_{\beta}$ are irreducibles.
	3. $c=wr_{1}\dots r_{\gamma}$ where $w\in R^{*}$ and $r_{1},\dots,r_{\gamma}$ are irreducibles.
	
	Then, as $\gcd(a,b)=1$, $p_{i}\not\sim q_{j}$ for all $i,j$. Further, 
	$$ab=uvp_{1}\dots p_{\alpha}q_{1}\dots q_{\beta}=w^nr_{1}^n\dots r_{\gamma}^n=c^n$$First notice that $w^n\in R^{*}$. By the uniqueness of the factorization, $\alpha+\beta=\gamma n$ and for all $i,j$, $p_{i}\sim r_{k}$ for some $k$ and $q_{j}\sim r_{\ell}$ for some $\ell$. Indeed, it is also not possible that $p_{i}\sim r_{k}\sim q_{j}$ for some $i,j,k$ as associates are transitive and $a,b$ are coprime. In other words, the $n$ copies of $r_{k}$ get paired up with exactly one of $a$ or $b$. This shows that, modulo renumbering: 
	- $a\sim r_{1}^n\dots r_{\alpha /n}^n$
	- $b\sim r_{\alpha / n+1}^n\dots r_{\gamma}^n$
	
	which proves the statement.
	
1. Counterexample. Consider $(1+\sqrt{ -26 })$ and $(1-\sqrt{ -26 })$. Then, $$(1+\sqrt{ -26 })(1-\sqrt{ -26 })=3^3$$Further, $1\pm \sqrt{ -26 }$ is irreducible as if there exists $a,b,c,d\in \mathbb{Z}$: $$\begin{align}1+\sqrt{ -26 }&=(a+b \sqrt{ -26 })(c+d \sqrt{ -26 })\\27&=(a^{2}+26b ^{2})(c^{2}+26 d^{2})\end{align}$$which is only possible if $a+b \sqrt{ -26 }=1$ or $c+d \sqrt{ -26 }=1$. Hence, $\gcd(1+\sqrt{ -26 },1-\sqrt{ -26 })=1$. However, if there exists $u\in R^{*},x\in R$ s.t. $1+\sqrt{ -26 }=ux^3$, as we have seen above, either $ux=1$ or $x^{2}=1$. This means $x\in R^{*}$ and $1+\sqrt{ -26 }\in R^{*}$, which is a contradiction.
---