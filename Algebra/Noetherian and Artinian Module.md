#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module.
> 1. $M$ is called ***Noetherian*** if every ascending chain of submodules of $M$: $$M_{0}\subseteq M_{1}\subseteq M_{2}\subseteq\dots$$becomes stationary, i.e. for every chain, there exists $n\in \mathbb{N}$ s.t. $M_{k}=M_{n}$ for all $k\geq n$. 
> 2. $M$ is called ***Artinian*** if every descending chain of submodules of $M$: $$M_{0}\supseteq M_{1} \supseteq M_{2} \supseteq\dots$$becomes stationary.

^11ada3

---
##### Properties
> [!lemma] Proposition 1 (Equivalent Conditions of Noetherian/Artinian Modules)
> Let $M$ be a $R$-module.
> 1. $M$ is Noetherian if and only if every non-empty family of submodules of $M$ has a maximal element.
> 2. $M$ is Artinian if and only if every non-empty family of submodules of $M$ has a minimal element.
> 3. $M$ is Noetherian if and only if every submodule of $M$ is finitely generated.

^7b589f

> [!proof]-
> We have:
> 1. We will show that:
> 	1. (1=>2): Let $A$ be a non-empty family of submodules of $M$. If there is no maximal element, then we can recursively choose a chain $M_{0}\subsetneq M_{1}\subsetneq\dots$ from $A$. This is a contradiction.
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq M_{2}\subseteq\dots$ be a chain of submodules. Then, this has a maximal element $M_{n}$. Hence, the chain is stationary and $M$ is Noetherian.
> 2. Analogous to 1. 
> 3. We show that:
> 	1. (1=>2): Assume there exists a submodule $N\leq M$ that is not finitely generated. Then, we can recursively pick $m_{0}\in N$ and $m_{n+1}\in N \backslash \braket{ m_{0} , \dots,m_{n} }$ and obtain a chain: $$M_{0}\subsetneq M_{1}\subsetneq \dots$$which is a contradiction. 
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq\dots$ be a chain. Then, $N:=\bigcup_{n}^{}M_{n}\leq M$ and $N=\braket{ m_{1} , \dots,m_{r} }$. Then, by definition we have $n_{i}\in \mathbb{N}$ s.t. $m_{i}\in M_{n_{i}}$ for all $i$. Hence, by choosing $n:= \max n_{i}$, $M$ is Noetherian. 

^0f47ce

---
> [!lemma] Lemma 2
> Let $M$ be a $R$-module and $N\leq M$.
> 1. $M$ is Noetherian if and only if $N$ and $M / N$ are Noetherian.
> 2. $M$ is Artinian if and only if $N$ and $M / N$ are Artinian.

^ad1eee

> [!proof]-
> We have:
> 1. We show that:
> 	1. (1=>2): Let $M$ be Noetherian. As any chain of submodules of $N$ is also that of $M$, $N$ is Noetherian. 
> 	   
> 	   Similarly, let $P_{0}\subseteq P_{1}\subseteq\dots$ be a chain of submodules of $M /N$. Let $M_{i}:= q^{-1}(P_{i})$ where $q:M\to M / N$ be the quotient map. Then, $M_{0}\subseteq M_{1}\subseteq \dots$ is a chain of submodules of $M$ and becomes stationary. As $q$ is surjective, this means that the $P$-chain also becomes stationary. Hence, $M / N$ is Noetherian.
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq \dots$ be an ascending chain of submodules. If we set $N_{i}:= M_{i}\cap N$, and $P_{i}:=(M_{i}+N) / N$, then: $$N_{0}\subseteq N_{1}\subseteq\dots,\quad P_{0}\subseteq P_{1}\subseteq\dots$$are ascending chain of submodules of $N$ and $M / N$ respectively. As they both become stationary, there exists $n\in \mathbb{N}$ s.t. $N_{k}=N_{n}$ and $P_{k}=P_{n}$ for all $k\geq n$. Then, we get a commutative diagram: $$\begin{CD}0 @>>> N_{n}@>>> M_{n} @>>> P_{n}@>>> 0\\&@VVV @VVV@VVV\\0 @>>> N_{k}@>>> M_{k} @>>> P_{k}@>>> 0\end{CD}$$where the rows are exact. Then, by [[Exact Sequence|5-lemma]], the inclusion $M_{n}\to M_{k}$ is an isomorphism, i.e. $M_{n}=M_{k}$ for all $k\geq n$. 
> 2. Analogous to 1.

^0f0168

- **Corollary**: Let $R$ be a Noetherian ring and $I\unlhd R$. Then, $R / I$ is a Noetherian ring.  ^bf8e86

---
> [!lemma] Corollary 3
> Let $M,N$ be $R$-modules.
> 1. $M\oplus N$ is Noetherian/Artinian if and only if $M,N$ are.
> 2. if $R$ is Noetherian/Artinian and $M$ is finitely generated, then $M$ is also Noetherian/Artinian.

^f57f95

> [!proof]-
> We have that:
> 1. From the exact sequence $0\to M \to M\oplus N \to N \to 0$ and Lemma 2 by treating $M$ as a submodule of $M\oplus N$ and $N\cong M\oplus N / M$.
> 2. Let $M:=\braket{ m_{1} , \dots,m_{k} }$ for some $m_{1},\dots,m_{k}\in M$. Then, the module homomorphism: $$\varphi:R^k\to M,\quad (a_{1},..,a_{k})\mapsto a_{1}m_{1}+\dots+a_{k}m_{k}$$ is surjective and we have an exact sequence, $0 \to \text{ker }\varphi \to R^k \to M \to 0$. As $R$ is Noetherian /Artinian, so is $R^k$ by 1 and subsequently $M$ by Lemma 2.

^201b37

---
> [!lemma] Lemma 4 (Noetherian, Artinian and Length)
> Let $M$ be a $R$-module.
> 1. $M$ is of finite [[Composition Series|length]] if and only if it is both Noetherian and Artinian.

^851c01

> [!proof]-
> We have:
> 1. If $M$ is of finite length, then all strict chains of submodules of $M$ are finite by [[Composition Series|Proposition 1]]. Hence, $M$ is both Noetherian and Artinian.
> 	
> 	Conversely, assume $M$ is both Noetherian and Artinian. Starting from $M_{0}=0$, we construct a chain as follows: Let $M_{n+1}$ be the minimal submodule of $M$ that strictly contains $M_{n}$. As long as $M_{n}\neq M$, this works by Proposition 1.2 since $M$ is Artinian. However, as $M$ is Noetherian, this chain cannot grow indefinitely and we will have $M_{n}=M$ for some $n\in \mathbb{N}$. 
> 	
> 	This gives us a composition series by construction and $M$ is of finite length. 
> 	

^79018c

---
> [!lemma] Proposition 5
> Let $M$ be a $R$-module and $\varphi:M\to M$ a $R$-module homomorphism.
> 1. If $M$ is Noetherian and $\varphi$ is surjective, $\varphi$ is isomorphic. 
> 2. If $M$ is Artinian and $\varphi$ is injective, $\varphi$ is isomorphic. 

^8f7e90

> [!proof]-
> We have:
> 1. If $M$ is Noetherian, then it is finitely generated and the rest follows from [[Module|Corollary 8]].
> 2. If $M$ is Artinian, then let $M_{n}:= \text{im }\varphi^n$. Then, $M_{n+1}\subseteq M_{n}$ for all $n$ and: $$M_{1}\supseteq M_{2}\supseteq \dots$$is a descending chain of submodules. Hence, there exists $n\in \mathbb{N}$ s.t. $\text{im }\varphi^k=\text{im }\varphi^n$ for all $k\geq n$. Let $b\in M$. Then, we have that: $$\varphi^n(b)=\varphi^{n+1}(a)$$for some $a\in M$. Hence, by injectivity, $b=\varphi(a)$ and $\varphi$ is isomorphic. 

^c49c05

---
> [!lemma] Proposition 6
> Let $M$ be a $R$-module.
> 1. if $M$ is Noetherian, so is $R / \text{Ann}(M)$.
> 2. if $M$ is finitely generated and Artinian, then $M$ is also Noetherian.

^53ccea

> [!proof]-
> We have:
> 1. If $M$ is Noetherian, $M$ is finitely generated, i.e. $M=\braket{ m_{1} , \dots,m_{k} }$. Therefore, $M^k$ is also Noetherian and consider a map: $$\varphi:R\to M^k,\quad 1\mapsto (m_{1},\dots,m_{k})$$Then, $\text{ker }\varphi=\text{Ann}(M)$. Hence, $R / \text{Ann}(M)\cong \text{im }\varphi$, which is Noetherian. 
> 2. If $M$ is finitely generated, we can do the same proof as 1 to get that $R / \text{Ann}(M)$ is a Artinian ring. Hence, by Hopkins, $R / \text{Ann}(M)$ is Noetherian. 
>    
>    Now, $M$ can be viewed as a $R  / \text{Ann}(M)$ module and by Corollary 3.2, $M$ is Noetherian.

^52e94b


---
##### Noetherian Rings
> [!lemma] Theorem 1 (Hilbert's Basis Theorem)
> Let $R$ be a Noetherian ring. 
> 1. $R[x]$ is also Noetherian.
> 2. A finitely generated $R$-algebra $A$ is a Noetherian ring.

^0b0197

> [!proof]-
> We have:
> 1. Assume $R[x]$ is not Noetherian. Then, by Proposition 1, there exists an ideal $I\unlhd R[x]$ that is not finitely generated. Hence, we can find $(f_{i})_{i}\subseteq I$ as follows: 
>	1. $f_{0}\in I$ is a non-zero polynomial of minimal degree.
>	2. $f_{k+1}$ is a non-zero polynomial of minimal degree in $I \backslash \braket{ f_{0} , \dots,f_{k} }$.
>   
> 	Now, for all $k$, let $d_{k}$ denote the degree of $f_{k}$ and $a_{k}\in R$ the leading coefficient of $f_{k}$. Then, $d_{k}\leq d_{k+1}$ by construction. Now, since $R$ is Noetherian, $(a_{0})\subseteq (a_{0},a_{1})\subseteq(a_{0},a_{1},a_{2})\subseteq \dots$ becomes stationary and we have: $$a_{n+1}=c_{0}a_{0}+\dots+c_{n}a_{n}$$for some $n\in \mathbb{N}$ and $c_{i}\in R$. 
> 
> 	If we now define: $$f'_{n+1}:= f_{n+1}-\sum_{k=0}^{n}c_{k}(x^{d_{n+1}-d_{k}})f_{k}$$Then, $x^{d_{n+1}}$ coefficient is $0$ and $\deg f'_{n+1}\leq \deg f_{n+1}$. However, as $f_{n+1}\notin \braket{ f_{0} , \dots,f_{n} }$, so is $f'_{n+1}$. This contradicts the minimality of $f_{n+1}$ and $R[x]$ is Noetherian. 
> 2. By [[Algebra|Lemma 2]], $A\cong R[x_{1},\dots,x_{n}] / I$ for some $I\unlhd R[x_{1},\dots,x_{n}]$. Now, from Hilbert's Basis theorem, we have that $R[x_{1},\dots,x_{n}]$ is Noetherian. Hence, by Lemma 2, $A$ is Noetherian as well.

^1f586a

---
> [!lemma] Proposition 2
> Let $R$ be a Noetherian ring. 
> 1. if $R$ is an integral domain, every non-zero non-unit $a\in R$ can be written as a product of irreducible elements in $R$. 
> 2. for any ideal $I\unlhd R$, there is an $n\in \mathbb{N}$ s.t. $(\sqrt{ I })^n\subseteq I$.

^2f8b5f

> [!proof]-
> We have:
> 1. Let $X$ be the set of non-zero non-units in $R$ that cannot be written in irreducible elements. If $X\neq \varnothing$, then pick $x_0\in X$. As $x_{0}$ is not irreducible, hence, we can find $x_{1}\in X$ s.t. $x_{0}=yx_{1}$. Continuing this, we have a sequence, $$(x_{0})\subseteq(x_{1})\subseteq\dots$$As $R$ is Noetherian, we have $x_{n}$ s.t. $(x_{n})=(x_{n+1})$. Then, by construction $x_{n}=ax_{n+1}$ for some non-unit $a\in R$. However, as $x_{n+1}\in (x_{n})$, there exists some $z\in R$ s.t. $x_{n+1}=zax_{n+1}$. As $R$ is an integral domain, we have that $1=za$ which proves that $a$ is a unit. This is a contradiction and $X=\varnothing$.
> 2. As $R$ is Noetherian, $\sqrt{ I }$ is finitely generated, i.e. $\sqrt{ I }=(a_{1},\dots,a_{k})$. Then, we have $n_{i}$ s.t. $a_{i}^{n_{i}}\in I$ and by taking $n:= n_{1}+\dots+n_{k}$, we have that $(\sqrt{ I })^n$ is generated by $a_{1}^{\mu_{1}}\dots a_{k}^{\mu_{k}}$ where $\mu_{1}+\dots+\mu_{k}=n_{1}+\dots+n_{k}$. Now, we have that at least one $i\in[k]$, $\mu_{k}\geq n_{i}$ and hence, $a_{1}^{\mu_{1}}\dots a_{k}^{\mu_{k}}\in I$. This shows that $(\sqrt{ I })^n\subseteq I$.

^734d2a

---
> [!lemma] Proposition 3
 > Let $R$ be an Noetherian integral domain. 
 > 1. $R$ is UFD if and only if every minimal prime ideal over a principal ideal is principal.
 > 2. if $R$ is a UFD then every minimal non-zero prime ideal is principal.

> [!proof]- Proof (Incomplete)
---
##### Artinian Rings
> [!lemma] Proposition 1
> Let $R$ be an Artinian ring. 
> 1. there are maximal ideals $P_{1},\dots,P_{n}\unlhd R$ s.t. $P_{1}\cdots P_{n}=0$.
> 2. $R$ has only finitely many prime ideals all of which are maximal. They all occur among $P_{1},\dots,P_{n}$ in $1$.

^5a3218

> [!proof]-
> We have:
> 1. Let $I=P_{1}\dots P_{n}$ be a product of maximal ideals $P_{1},\dots,P_{n}$ s.t. $I$ is minimal among all ideals, which exists by Proposition 1.2. We need to show that $I=0$. 
> 	1. $I^{2}$ is also the product of maximal ideals and from $I^2\subseteq I$, $I=I^{2}$. 
> 	2. if $P\unlhd R$ is any maximal ideal, $PI\subseteq I$ and by minimality $I=PI\subseteq P$. Hence, $$I\subseteq \text{Rad}(R)$$ where $\text{Rad}(R)$ is the [[Jacobson radical]].
>    
> 	Now, assume that $I\neq 0$. Then, as $R$ is Artinian, there exists a minimal ideal $J\unlhd R$ with $IJ\neq 0$. Then, 
> 	1. $J$ is principal. Indeed, there must be an element $b\in J$ with $I\cdot(b)\neq 0$. Hence, by minimality of $J$, $(b)=J$. 
> 	2. $IJ=J$ as we have $IJ\subseteq J$ and $I\cdot IJ= I^{2}J=IJ\neq 0$.
>    
> 	Hence, $J$ is finitely generated and by [[Module|Nakayama]], there is an element $a\in I$ with $(1-a)m=0$ for all $m\in J$. As $J\neq 0$, $(1-a)$ is not a unit in $R$. Then, $(1-a)\neq R$, hence $1-a$ is contained in some maximal ideal $P\unlhd R$. However, so is $a\in I\subseteq P$, hence $$1=(1-a)+a\in P$$which is a contradiction. Hence, $I=0$.
> 2. Let $P\unlhd R$ be a prime ideal. Then, $P_{i}\subseteq P$ for some $i=1,\dots,n$. Otherwise, there exists $a_i\in  P_{i} \backslash P$ for all $i$ and $a_{1}\dots a_{n}\in P_{1}\dots P_{n}=0\subseteq P$. But this contradicts that $P$ is prime. Hence, $P_{i}\subseteq P$ for some $i$ and as $P_{i}$ is maximal, $P=P_{i}$. 

^d98383

---
> [!lemma] Theorem 2 (Hopkins)
> Let $R$ be a ring. TFAE:
> 1. $R$ is Artinian.
> 2. $R$ is Noetherian and every prime ideal is maximal.
> 3. $R$ is Noetherian and $\text{dim}R=0$.

^930aa1

> [!proof]-
> We have:
> 1. (1=>2): Let $R$ be Artinian. Then, every prime ideal is maximal by Proposition 1. Furthermore, we have a chain: $$0=Q_{0}\subseteq Q_{1}\subseteq\dots \subseteq Q_{n}=R$$where $Q_{i}:= P_{i+1}\cdots P_{n}$. Now, for all $i$, the quotient $Q_{i} / Q_{i-1}=Q_{i} / P_{i}Q_{i-1}$ is an Artinian $R$-module by Lemma 2. Hence, it is a Artinian $R / P_{i}$-vector space by Example 1.7. Hence, by Example 1.2, it is a Noetherian $R / P_{i}$-vector space and Noetherian $R$-module. 
>    
>    Hence, by induction on $i$, it follows that $Q_{i}$ is Noetherian and in particular $R= Q_{n}$ is Noetherian.
>    
>    The rest follows from Proposition 1.
>  2. (2=> 1): Assume that $R$ is Noetherian but not Artinian. We will find a prime ideal $P\unlhd R$ that is not maximal. 
>     
>     Consider the family of all ideals $I\unlhd R$ s.t. $R / I$ is not Artinian. Then it is non-empty as it contains the zero ideal. As $R$ is Noetherian, by Proposition 1.1, it has a maximal element $P$. However, $P$ is not maximal in $R$, as if it is then $R/P$ is a field, hence Artinian. 
>     
>     We are left to show that $P$ is prime, i.e. $S:=R / P$ is an integral domain. For any $a\in R$, consider the exact sequence: $$0 \to S / \text{Ann}(\overline{a})\xrightarrow{\cdot \overline{a}} S \to S / (\overline{a}) \to 0$$As $S$ is not Artinian, either $S / \text{Ann}(\overline{a})$ or $S / (\overline{a})$ is not Artinian. However, as $P$ is chosen to be maximal over all such rings, taking a further quotient of $S$ by a non-zero ideal must give an Artinian ring. This shows that either $\text{Ann}(\overline{a})=0$ or $\overline{a}=0$. Hence, every non-zero element of $R / P$ is a non-zero divisor. This shows that $R / P$ is an integral domain.
>  3. (2<=>3) is given by [[Krull Dimension|Example 1]].

^1ee703

---
> [!lemma] Theorem 3 (Structure Theorem for Artinian Rings)
> Every Artinian ring $R$ is a finite product of local Artinian rings. 
> 1. if $P_{1},\dots,P_{n}$ are the distinct maximal ideals, then $R_{P_{i}}$ are also Artinian and $R$ is isomorphic to $R_{P_{1}}\times\dots \times R_{P_{n}}$. 

^a4a5fe

> [!proof]-
> By Proposition 1, we can find $k\in \mathbb{N}$ s.t. $P_{1}^k\cdot\dots \cdot P^k_{n}=0$. Then, $P^k_{1},\dots,P^k_{n}$ are pairwise coprime by [[Maximal Ideal|Proposition 3]]. Hence, by [[Coprime Ideal|Theorem 2]]: $$P^k_{1}\cap\dots \cap P^k_{n}=P^k_{1}\cdot \dots \cdot P^k_{n}=0$$ Hence, by [[Ideal (Ring)|Chinese remainder theorem]], $$R\cong R / P^k_{1}\times\dots \times R / P^k_{n}$$and $R / P^k_{i}$ are Artinian for all $i$. Therefore, it suffices to show that $R / P^k_{i} \cong R_{P_{i}}$. We have:
> 1. Consider $\varphi_{i}:R\to R_{P_{i}}, a\mapsto \frac{a}{1}$. Then $P^k_{i}\subseteq \text{ker }\varphi_{i}$. Indeed, for $a\in P^k_{i}$, we can choose $a_{j}\in P_{j} \backslash P_{i}$. Then, $u:=a_{1}^k\dots a_{i-1}^k a^k_{i}\dots a^k_{n}\notin P_{i}$ since $P_{i}$ is prime. It follows that $ua\in P^k_{1}\dots P^k_{n}=0$. Hence, $\frac{a}{1}=0$ in $R_{P_{i}}$. Hence, we have a map $$\tilde{\varphi}_{i}:R / P_{i}^k \to R_{P_{i}},\quad \overline{a}\mapsto \frac{a}{1}$$
> 2. Consider $\psi:R \to R / P^k_{i}, a\mapsto \overline{a}$. For any $a\in R / P_{i}$, if $(\overline{a})$ is proper, then it is contained in some maximal ideal which must be of the form $P / P^k_{i}$ for a maximal ideal $P\supseteq P^k_{i}$ of $R$. As $P$ is prime, this means that $P\supseteq P_{i}$ and $P=P_{i}$ since $P_{i}$ is maximal. However, $\overline{a}\in P_{i} / P_{i}^k$ implies that $a\in P_{i}$, which is a contradiction. 
>    
>    Therefore, by [[Localization|universal property]] we have a map $\tilde{\psi}:R_{P_{i}} \to R / P^k_{i}$ with $\frac{a}{1}\mapsto \overline{a}$. 

^7b30ca

---
##### Examples

> [!h] Example 1
> We have that:
> 1. Any field $K$ is both Noetherian and Artinian as it only has trivial ideals. 
> 2. For a $K$-vector space $V$, TFAE:
> 	1. $V$ is Noetherian.
> 	2. $V$ is Artinian.
> 	3. $V$ is finite dimensional.
> 3. $\mathbb{Z}$ is Noetherian but not Artinian.
> 4. $R:=\bigcup_{n}^{}\mathbb{R}[x_{0},x_{1},\dots,x_{n}]$ is neither Noetherian nor Artinian.
> 5. Every [[Principal Ideal Domain|PID]] $R$ is Noetherian by Proposition 1.3. 
> 6. $\mathbb{R}[x]$ is a Noetherian ring but a non-Noetherian $R$-module by 2.
> 7. $M / IM$ is Noetherian/Artinian as an $R / I$ module if and only if it is as a $R$-module.
> 8. $R/I$ is Noetherian/Artinian as a ring if and only if it is as a $R$-module.

^5e1255

> [!proof]-
> We have:
> 1. Obvious.
> 2. If $V$ is finite dimensional, there can only be finite strictly increasing ascending or descending chain of vector subspaces. As the dimension has to be strictly increasing. 
> 	
> 	If $V$ is infinite dimensional, we can form an ascending chain that doesn't become stationary. Set $M_{0}:=0$ and for $i$, let $M_{i+1}:= M_{i}+\braket{ v_{i+1} }$ where $v_{i+1}\notin M_{i}$. Similarly, for a descending chain, we choose $M_{0}:=M$ and let $M_{i+1}:=M_{i}\cap \text{ker }\varphi_{i+1}$ where $\varphi_{i+1}:V\to K$ s.t. $\varphi_{i+1}|_{M_{i}}\neq 0$. Then, $$M/M_{n}\cong (M / M_{n+1}) / (M_{n} / M_{n+1})$$Hence, from $\text{dim}(M_{n} / M_{n+1})=1$, we have that it forms a descending chain. 
> 3. Assume we have a ascending chain $I_{0}\subsetneq I_{1}\subsetneq \dots$. As $\mathbb{Z}$ is a PID, we have that $I_{1}=(a)$ for some $a\neq 0$. However, by [[Ring Homomorphism|Proposition 5]], the ideals in $\mathbb{Z}$ that contain $(a)$ forms a bijection to the ideals in $\mathbb{Z} / (a)$, which is finite. Hence, the chain cannot be infinitely long. 
>    
>    $\mathbb{Z}$ is not Artinian as we have: $$\mathbb{Z} \supsetneq  2\mathbb{Z} \supsetneq 4\mathbb{Z} \supsetneq 8\mathbb{Z} \supsetneq \dots$$
>  4. We have: $$(x_{0})\subsetneq (x_{0},x_{1})\subsetneq(x_{0},x_{1},x_{2})\subsetneq \dots, \quad (x_{0})\supsetneq (x_{0}^{2})\supsetneq (x_{0}^3)\supsetneq \dots$$

^159f21

---
> [!h] Example 2
> Let $p\in \mathbb{N}$ be a prime number and consider $M:= \mathbb{Z}_{p} / \mathbb{Z}$ as a $\mathbb{Z}$-module, where $\mathbb{Z}_{p}\subseteq \mathbb{Q}$ denotes the [[localization]] of $\mathbb{Z}$ at $p$. Then,
> 1. every proper submodule of $M$ is of the form $\braket{ \overline{\frac{1}{p^n}}  }$.
> 2. $M$ is Artinian but not Noetherian.

^dac35e

> [!proof]-
> We have: 
> 1. $$\mathbb{Z}_{p}:=\left\{  \frac{a}{p^n}:a\in \mathbb{Z},n\in \mathbb{N}  \right\}$$Then, let $N$ be a proper submodule of $M$. If $N=0$, then $N=\braket{ \overline{\frac{1}{p^0}}  }$. Assume $N\neq 0$. Let $0\neq\overline{\frac{a}{p^n}}\in N$. Wlog we may assume that $1\leq a< p^n$. Then, $\gcd(a,p^n)=d$. Then, $a=da'$ where $\gcd(a',p^n)=1$. Hence, by [[Principal Ideal Domain|Theorem 2]], there exists $x,y\in \mathbb{Z}$ s.t. $$1=a'x+p^ny$$Multiplying it by $\frac{d}{p^n}$, we get $\frac{d}{p^n}=\frac{a}{p^n}x+dy$ and $\overline{\frac{d}{p^n}}=x\overline{\frac{a}{p^n}}\in N$. As $d$ is a divisor of $a$, we can repeat this argument to get that $\overline{\frac{1}{p^n}}\in N$. Therefore, $N\geq \braket{  \overline{\frac{1}{p^n}} }$. To show the opposite inclusion, Let $\overline{\frac{1}{p^n}},\overline{\frac{1}{p^m}}\in N$ with $n<m$. Then, $\overline{\frac{1}{p^n}}=\overline{\frac{p^{m-n}}{p^m}}$ and $\overline{\frac{1}{p^n}}\in \braket{ \overline{\frac{1}{p^m}}  }$. This proves the statement.
> 2. We showed that $\braket{ \overline{\frac{1}{p^n }}}\subsetneq\braket{ \overline{\frac{1}{p^m }}}$ for all $n<m$. Hence, $M$ is not Noetherian. Conversely, let $$N_{0}\supsetneq N_{1} \supsetneq \dots $$be a descending chain. Then, $N_1=\braket{ \overline{\frac{1}{p^n}}  }$ for some $n$ and there can be only finitely many submodules strictly smaller. 

^06e384

---
> [!h] Example 3 (Ideals in PID)
> Let $R$ be a PID.
> 1. for $0\neq I\unlhd R$, $I=(a)$ where $a=p_{1}^{a_{1}}\cdots p_{n}^{a_{n}}$ for $a_{1},\dots,a_{n}\in \mathbb{N}_{>0}$ and $p_{1},\dots ,p_{n}$ are distinct prime. 
> 2. the ideals of $R / I$ correspond to the ideals of $R$ that contain $I$, i.e. ideals $(b)$ with $b=p_{1}^{b_{1}}\dots p_{n}^{b_{n}}$ where $b_{i}\leq a_{i}$. 
> 3. $R / I$ is Noetherian and Artinian as it only has finitely many ideals. 
> 4. Every non-zero prime ideal in $R / I$ is maximal. 
> 5. Let $k:= \max a_{i}$. Then, $$(R / I) / (\overline{p}_{i}^k)\cong R / (a,p_{i}^k)=R / (p_{i}^{a_{i}})$$from [[Principal Ideal Domain|Proposition 6]]. Hence, $$R /I\cong R / (p_{1}^{a_{1}})\times\dots \times R / (p_{n}^{a_{n}})$$

^677f46

---
