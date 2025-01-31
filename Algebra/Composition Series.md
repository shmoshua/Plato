#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module. 
> 1. A ***composition series*** of $M$ is a finite chain: $$0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M $$of submodules s.t. there is no submodule $N$ with $M_{i-1}\subsetneq N\subsetneq M_{i}$ for all $i$.
> 2. the ***length*** of $M$, denoted as $\ell_{R}(M)$ is the shortest length of a composition series of $M$. If $M$ does not admit a composition series, then $\ell _R(M):=\infty$. 

^7b6826

- **Remark**: From [[module|Proposition 5]], $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ forms a composition series if and only if $M_{i} / M_{i-1}$ has no non-trivial proper submodules for all $i$.  ^8cc574
- **Remark**: For vector spaces, the length is equivalent to their dimension. ^009d6e
---
##### Properties
> [!lemma] Proposition 1 (Length)
> Let $M$ be a $R$-module of finite length. 
> 1. if $N<M$ be proper submodule. Then, $\ell(N)<\ell(M)$.
> 2. every composition series of $M$ has length $\ell(M)$.
> 3. every chain $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ can be refined into a composition series.

^4f96d6

> [!proof]-
> We have:
> 1. Let $n:=\ell(M)$ and  $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ be a composition series of $M$. Consider,  $$0=N\cap M_{0}\subsetneq N\cap M_{1}\subsetneq\dots\subsetneq N\cap M_{n} =N\cap M $$ is a chain of submodules from $N$ to $0$. Then, by the isomorphism theorem, $$(N\cap M_{i}) / (N\cap M_{i-1})=(N\cap M_{i}) / (N\cap M_{i}\cap M_{i-1})\cong (N\cap M_{i}+M_{i-1}) / M_{i-1}$$which is a submodule of $M_{i} / M_{i+1}$, which is simple. Hence, $(N\cap M_{i}) / (N\cap M_{i-1})$ is trivial or simple. Hence, we have that $\ell(N)\leq \ell(M)$. 
>    
>    To show that $\ell(N)< \ell(M)$, notice that $(N\cap M_{i}) / (N\cap M_{i-1})$ is simple only when $N\cap M_{i}+M_{i-1}=M_{i}$. Assume this happens at every $i$. Then, by induction, $$M_{i}=N\cap M_{i}+M_{i-1}=N\cap M_{i}+N\cap M_{i-1}=N\cap M_{i}$$ In particular, $M=N\cap M$, which contradicts our assumption. Hence, there exists $i$ s.t. $(N\cap M_{i}) / (N\cap M_{i-1})= 0$. By taking this out of the composition series, we have that $\ell(N)<\ell(M)$.
>  2. Let $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ be a composition series.  Then, by 1, $$0=\ell(M_{0})<\ell(M_{1})<\dots< \ell(M_{n})=\ell(M)$$Hence, $\ell(M)\geq n$. But we have that $\ell(M)\leq n$. Therefore, $\ell(M)=n$. 
>  3. Let $M_{i+1}, M_{i}$ s.t. $M_{i+1} / M_{i}$ is not simple. Then, let $P$ be a non-trivial submodule and $\pi ^{-1}(P)$ is a submodule between $M_{i}$ and $M_{i+1}$ where $\pi:M_{i+1}\to M_{i+1} / M_{i}$. Hence, it follows.

^efe39a

---
> [!lemma] Proposition 2 (Additivity of Length)
> Let $M$ be a $R$-module and $N,N'\leq M$. Then, 
> 1. $\ell(N)+\ell(M / N)=\ell(M)$.
> 2. $\ell(N+N')+\ell(N\cap N')=\ell(N)+\ell(N')$.
> 3. for any $R$-module homomorphism $\varphi:M\to M'$, $\ell(\text{ker }\varphi)+\ell(\text{im }\varphi)=\ell(M)$

^fb4863

> [!proof]-
> We have:
> 1. Notice that:
> 	1. We first assume that $\ell(M)<\infty$. By Proposition 1.3, we can refine $0\leq N\leq M$ into a composition series. $$0 =N_{0}\subsetneq \dots\subsetneq N_{n}=N= M_{0}\subsetneq\dots\subsetneq M_{m}=M$$where $\ell(M)=n+m$ and $\ell(N)=n$. By setting $P_{i}:= M_{i} / N$, we get a chain:$$0=P_{0}\subsetneq\dots\subsetneq P_{m}=M / N$$To show that this is a composition series, we have that: $$P_{i+1}/P_{i}=(M_{i+1} / N) / (M_{i} / N)\cong M_{i+1} / M_{i}$$Hence is simple. Therefore, $\ell(M/N)=m$.  This shows the statement.
> 	2. We now assume that $\ell(N)$ and $\ell(M/N)$ are finite. Let $$0=N_{0}\subsetneq\dots\subsetneq N_{n}=N,\quad 0=P_{0}\subsetneq\dots\subsetneq P_{m}=M / N$$be the composition series. Let $q:M\to M / N$ be the quotient map and we define $M_{i}:=q^{-1}(P_{i})$ for all $i$. Then, we have that: $M_{i+1}/M_{i}\cong P_{i+1} / P_{i}$ as above and we get a composition series for $m$ of length $m+n$. 
> 	3. If both sides of the equations are infinite, then the statement is trivially true. 
> 2. Let $Q:=(N+N') / N'\cong N / (N\cap N')$. Then, $$\ell(N')+\ell(Q)=\ell(N+N'),\quad \ell(N\cap N')+\ell(Q)=\ell(N)$$Hence, if $\ell(N')=\ell(N+N')=\infty$, then the statement is true. Similarly, if $\ell(N\cap N')=\ell(N)=\infty$, then it is also true. Otherwise, $$\ell(N+N')+\ell(N\cap N')=\ell(N)+\ell(N')$$
> 3. We have that $M / \text{ker }\varphi= \text{im }\varphi$. The rest follows from 1. 

^8891f4

- **Corollary**: For a $R$-module homomorphism, $\varphi:M\to M$ where $M$ is of finite length, TFAE: ^201ec3
	1. $\varphi$ is injective, i.e. $\ell(\text{ker }\varphi)= 0$.
	2. $\varphi$ is surjective, i.e. $\ell(\text{im }\varphi)= \ell(M)$.
	3. $\varphi$ is bijective.
	
---
> [!lemma] Proposition 3 (Tensor Product)
> Let $M,N$ be two $R$-modules. Then, 
> 1. $\ell(M\otimes N)\leq \ell(M)\ell(N)$

^e28bda

> [!proof]-
> We have:
> 1. Assume $\ell(M)=\infty$ or $\ell(N)=\infty$. Then, the RHS is $\infty$ and the statement holds.
> 2. if $\ell(M)=:n<\infty$, then we prove it by induction. If $M=1$, then: $$0 \to R \to M \to M / R \to 0$$is exact and therefore, $$N \xrightarrow{\psi} M\otimes _{R}N \xrightarrow{\varphi} N \otimes  M / R \to 0$$is exact. Hence,$$\ell(M\otimes _{R}N)=\ell(N\otimes M / R)+\ell(\text{im }\psi)\leq \ell(N\otimes M / R)+\ell(N)\leq \ell(M)\ell(N)$$

^204142

---
> [!lemma] Proposition 4 (Length of Localized Series)
> Let $M$ be a $R$-module of finite length and: $$0=M_{0}\subsetneq M_{1}\subsetneq \dots\subsetneq M_{n}=M$$be a composition series s.t. $M_{i} / M_{i-1}\cong R / I_{i}$ for some maximal $I_{i}\unlhd R$. Then,
> 1. for any maximal $P\unlhd R$, $\ell_{R_{P}}(M_{P})$ is the number of indices $i$ s.t. $I_{i}=P$.

> [!proof]-
> Consider the chain of localized modules: $$0=(M_{0})_{P}\subsetneq (M_{1})_{P}\subsetneq \dots\subsetneq (M_{n})_{P}=M_{P}$$Then, for all $i$, $$(M_{i})_{P} / (M_{i-1})_{P}\cong (M_{i} / M_{i-1})_{P}\cong (R / I_{i})_{P}\cong R_{P} / (I_{i})_{P}$$Now, by [[Localization|Example 4]], $R_{P} / (I_{i})_{P}\cong R / I_{i}$ if and only if $P=I_{i}$ and otherwise zero. This proves the statement.
- **Corollary**: $\ell(M)=\sum_{P\unlhd R, \text{maximal}}^{}\ell_{R_{P}}(M_{P})$. 