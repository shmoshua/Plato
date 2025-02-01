#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module.
> 1. $M$ is called ***Noetherian*** if every ascending chain of submodules of $M$: $$M_{0}\subseteq M_{1}\subseteq M_{2}\subseteq\dots$$becomes stationary, i.e. for every chain, there exists $n\in \mathbb{N}$ s.t. $M_{k}=M_{n}$ for all $k\geq n$. 
> 2. $M$ is called ***Artinian*** if every descending chain of submodules of $M$: $$M_{0}\supseteq M_{1} \supseteq M_{2} \supseteq\dots$$becomes stationary.

---
##### Properties
> [!lemma] Proposition 1 (Equivalent Conditions of Noetherian/Artinian Modules)
> Let $M$ be a $R$-module.
> 1. $M$ is Noetherian if and only if every non-empty family of submodules of $M$ has a maximal element.
> 2. $M$ is Artinian if and only if every non-empty family of submodules of $M$ has a minimal element.
> 3. $M$ is Noetherian if and only if every submodule of $M$ is finitely generated.

> [!proof]-
> We have:
> 1. We will show that:
> 	1. (1=>2): Let $A$ be a non-empty family of submodules of $M$. If there is no maximal element, then we can recursively choose a chain $M_{0}\subsetneq M_{1}\subsetneq\dots$ from $A$. This is a contradiction.
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq M_{2}\subseteq\dots$ be a chain of submodules. Then, this has a maximal element $M_{n}$. Hence, the chain is stationary and $M$ is Noetherian.
> 2. Analogous to 1. 
> 3. We show that:
> 	1. (1=>2): Assume there exists a submodule $N\leq M$ that is not finitely generated. Then, we can recursively pick $m_{0}\in N$ and $m_{n+1}\in N \backslash \braket{ m_{0} , \dots,m_{n} }$ and obtain a chain: $$M_{0}\subsetneq M_{1}\subsetneq \dots$$which is a contradiction. 
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq\dots$ be a chain. Then, $N:=\bigcup_{n}^{}M_{n}\leq M$ and $N=\braket{ m_{1} , \dots,m_{r} }$. Then, by definition we have $n_{i}\in \mathbb{N}$ s.t. $m_{i}\in M_{n_{i}}$ for all $i$. Hence, by choosing $n:= \max n_{i}$, $M$ is Noetherian. 

---
> [!lemma] Lemma 2
> Let $M$ be a $R$-module and $N\leq M$.
> 1. $M$ is Noetherian if and only if $N$ and $M / N$ are Noetherian.
> 2. $M$ is Artinian if and only if $N$ and $M / N$ are Artinian.

> [!proof]-
> We have:
> 1. We show that:
> 	1. (1=>2): Let $M$ be Noetherian. As any chain of submodules of $N$ is also that of $M$, $N$ is Noetherian. 
> 	   
> 	   Similarly, let $P_{0}\subseteq P_{1}\subseteq\dots$ be a chain of submodules of $M /N$. Let $M_{i}:= q^{-1}(P_{i})$ where $q:M\to M / N$ be the quotient map. Then, $M_{0}\subseteq M_{1}\subseteq \dots$ is a chain of submodules of $M$ and becomes stationary. As $q$ is surjective, this means that the $P$-chain also becomes stationary. Hence, $M / N$ is Noetherian.
> 	2. (2=>1): Let $M_{0}\subseteq M_{1}\subseteq \dots$ be an ascending chain of submodules. If we set $N_{i}:= M_{i}\cap N$, and $P_{i}:=(M_{i}+N) / N$, then: $$N_{0}\subseteq N_{1}\subseteq\dots,\quad P_{0}\subseteq P_{1}\subseteq\dots$$are ascending chain of submodules of $N$ and $M / N$ respectively. As they both become stationary, there exists $n\in \mathbb{N}$ s.t. $N_{k}=N_{n}$ and $P_{k}=P_{n}$ for all $k\geq n$. Then, we get a commutative diagram: $$\begin{CD}0 @>>> N_{n}@>>> M_{n} @>>> P_{n}@>>> 0\\&@VVV @VVV@VVV\\0 @>>> N_{k}@>>> M_{k} @>>> P_{k}@>>> 0\end{CD}$$where the rows are exact. Then, by [[Exact Sequence|5-lemma]], the inclusion $M_{n}\to M_{k}$ is an isomorphism, i.e. $M_{n}=M_{k}$ for all $k\geq n$. 
> 2. Analogous to 1.
- **Corollary**: Let $R$ be a Noetherian ring and $I\unlhd R$. Then, $R / I$ is a Noetherian ring. 

---
> [!lemma] Corollary 3
> Let $M,N$ be $R$-modules.
> 1. $M\oplus N$ is Noetherian/Artinian if and only if $M,N$ are.
> 2. if $R$ is Noetherian/Artinian and $M$ is finitely generated, then $M$ is also Noetherian/Artinian.

> [!proof]-
> We have that:
> 1. From the exact sequence $0\to M \to M\oplus N \to N \to 0$ and Lemma 2 by treating $M$ as a submodule of $M\oplus N$ and $N\cong M\oplus N / M$.
> 2. Let $M:=\braket{ m_{1} , \dots,m_{k} }$ for some $m_{1},\dots,m_{k}\in M$. Then, the module homomorphism: $$\varphi:R^k\to M,\quad (a_{1},..,a_{k})\mapsto a_{1}m_{1}+\dots+a_{k}m_{k}$$ is surjective and we have an exact sequence, $0 \to \text{ker }\varphi \to R^k \to M \to 0$. As $R$ is Noetherian /Artinian, so is $R^k$ by 1 and subsequently $M$ by Lemma 2.
---
> [!lemma] Lemma 4 (Noetherian, Artinian and Length)
> Let $M$ be a $R$-module.
> 1. $M$ is of finite [[Composition Series|length]] if and only if it is both Noetherian and Artinian.

> [!proof]-
> We have:
> 1. If $M$ is of finite length, then all strict chains of submodules of $M$ are finite by [[Composition Series|Proposition 1]]. Hence, $M$ is both Noetherian and Artinian.
> 	
> 	Conversely, assume $M$ is both Noetherian and Artinian. Starting from $M_{0}=0$, we construct a chain as follows: Let $M_{n+1}$ be the minimal submodule of $M$ that strictly contains $M_{n}$. As long as $M_{n}\neq M$, this works by Proposition 1.2 since $M$ is Artinian. However, as $M$ is Noetherian, this chain cannot grow indefinitely and we will have $M_{n}=M$ for some $n\in \mathbb{N}$. 
> 	
> 	This gives us a composition series by construction and $M$ is of finite length. 
> 	
---
> [!lemma] Proposition 5
> Let $M$ be a $R$-module and $\varphi:M\to M$ a $R$-module homomorphism.
> 1. If $M$ is Noetherian and $\varphi$ is surjective, $\varphi$ is isomorphic. 
> 2. If $M$ is Artinian and $\varphi$ is injective, $\varphi$ is isomorphic. 

> [!proof]
> We have:
> 1. If $M$ is Noetherian, then it is finitely generated and the rest follows from [[Module|Corollary 8]].
> 2. If $M$ is Artinian, then let $M_{n}:= \text{im }\varphi^n$. Then, $M_{n+1}\subseteq M_{n}$ for all $n$ and: $$M_{1}\supseteq M_{2}\supseteq \dots$$is a descending chain of submodules. Hence, there exists $n\in \mathbb{N}$ s.t. $\text{im }\varphi^k=\text{im }\varphi^n$ for all $k\geq n$. Assume $\varphi$ is not surjective, i.e. there exists $a\in M$ s.t. $\varphi(b)\neq a$ for all $b\in M$. Then, $$\varphi^n(\varphi^{k-n}(a))=\varphi^n(a)\implies \varphi^{k-n}(a)=a$$

---
##### Examples

> [!h] Example 1
> We have that:
> 1. Any field $K$ is both Noetherian and Artinian as it only has trivial ideals. 
> 2. For a $K$-vector space $V$, TFAE:
> 	1. $K$ is Noetherian.
> 	2. $K$ is Artinian.
> 	3. $K$ is finite dimensional.
> 3. $\mathbb{Z}$ is Noetherian but not Artinian.
> 4. $R:=\bigcup_{n}^{}\mathbb{R}[x_{0},x_{1},\dots,x_{n}]$ is neither Noetherian nor Artinian.
> 5. Every [[Principal Ideal Domain|PID]] $R$ is Noetherian by Proposition 1.3. 
> 6. $\mathbb{R}[x]$ is a Noetherian ring but a non-Noetherian $R$-module by 2.
> 7. $R/I$ is Noetherian/Artinian as a ring if and only if it is as a $R$-module.

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
---
> [!h] Example 2
> Let $p\in \mathbb{N}$ be a prime number and consider $M:= \mathbb{Z}_{p} / \mathbb{Z}$ as a $\mathbb{Z}$-module, where $\mathbb{Z}_{p}\subseteq \mathbb{Q}$ denotes the [[localization]] of $\mathbb{Z}$ at $p$. Then,
> 1. every proper submodule of $M$ is of the form $\braket{ \overline{\frac{1}{p^n}}  }$.
> 2. $M$ is Artinian but not Noetherian.

> [!proof]-
> We have: 
> 1. $$\mathbb{Z}_{p}:=\left\{  \frac{a}{p^n}:a\in \mathbb{Z},n\in \mathbb{N}  \right\}$$Then, let $N$ be a proper submodule of $M$. If $N=0$, then $N=\braket{ \overline{\frac{1}{p^0}}  }$. Assume $N\neq 0$. Let $0\neq\overline{\frac{a}{p^n}}\in N$. Wlog we may assume that $1\leq a< p^n$. Then, $\gcd(a,p^n)=d$. Then, $a=da'$ where $\gcd(a',p^n)=1$. Hence, by [[Principal Ideal Domain|Theorem 2]], there exists $x,y\in \mathbb{Z}$ s.t. $$1=a'x+p^ny$$Multiplying it by $\frac{d}{p^n}$, we get $\frac{d}{p^n}=\frac{a}{p^n}x+dy$ and $\overline{\frac{d}{p^n}}=x\overline{\frac{a}{p^n}}\in N$. As $d$ is a divisor of $a$, we can repeat this argument to get that $\overline{\frac{1}{p^n}}\in N$. Therefore, $N\geq \braket{  \overline{\frac{1}{p^n}} }$. To show the opposite inclusion, Let $\overline{\frac{1}{p^n}},\overline{\frac{1}{p^m}}\in N$ with $n<m$. Then, $\overline{\frac{1}{p^n}}=\overline{\frac{p^{m-n}}{p^m}}$ and $\overline{\frac{1}{p^n}}\in \braket{ \overline{\frac{1}{p^m}}  }$. This proves the statement.
> 2. We showed that $\braket{ \overline{\frac{1}{p^n }}}\subsetneq\braket{ \overline{\frac{1}{p^m }}}$ for all $n<m$. Hence, $M$ is not Noetherian. Conversely, let $$N_{0}\supsetneq N_{1} \supsetneq \dots $$be a descending chain. Then, $N_1=\braket{ \overline{\frac{1}{p^n}}  }$ for some $n$ and there can be only finitely many submodules strictly smaller. 
---
