#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module. 
> 1. A ***composition series*** of $M$ is a finite chain: $$0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M $$of submodules s.t. there is no submodule $N$ with $M_{i-1}\subsetneq N\subsetneq M_{i}$ for all $i$.
> 2. the ***length*** of $M$, denoted as $\ell_{R}(M)$ is the shortest length of a composition series of $M$. If $M$ does not admit a composition series, then $\ell _R(M):=\infty$. 
- **Remark**: From [[module|Proposition 5]], $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ forms a composition series if and only if $M_{i} / M_{i-1}$ has no non-trivial proper submodules for all $i$. 
- **Remark**: For vector spaces, the length is equivalent to their dimension.
---
##### Properties
> [!lemma] Proposition 1 (Length)
> Let $M$ be a $R$-module of finite length. 
> 1. if $N<M$ be proper submodule. Then, $\ell(N)<\ell(M)$.
> 2. every composition series of $M$ has length $\ell(M)$.
> 3. every chain $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ can be refined into a composition series.

> [!proof]-
> We have:
> 1. Let $n:=\ell(M)$ and  $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ be a composition series of $M$. Consider,  $$0=N\cap M_{0}\subsetneq N\cap M_{1}\subsetneq\dots\subsetneq N\cap M_{n} =N\cap M $$ is a chain of submodules from $N$ to $0$. Then, by the isomorphism theorem, $$(N\cap M_{i}) / (N\cap M_{i-1})=(N\cap M_{i}) / (N\cap M_{i}\cap M_{i-1})\cong (N\cap M_{i}+M_{i-1}) / M_{i-1}$$which is a submodule of $M_{i} / M_{i+1}$, which is simple. Hence, $(N\cap M_{i}) / (N\cap M_{i-1})$ is trivial or simple. Hence, we have that $\ell(N)\leq \ell(M)$. 
>    
>    To show that $\ell(N)< \ell(M)$, notice that $(N\cap M_{i}) / (N\cap M_{i-1})$ is simple only when $N\cap M_{i}+M_{i-1}=M_{i}$. Assume this happens at every $i$. Then, by induction, $$M_{i}=N\cap M_{i}+M_{i-1}=N\cap M_{i}+N\cap M_{i-1}=N\cap M_{i}$$ In particular, $M=N\cap M$, which contradicts our assumption. Hence, there exists $i$ s.t. $(N\cap M_{i}) / (N\cap M_{i-1})= 0$. By taking this out of the composition series, we have that $\ell(N)<\ell(M)$.
>  2. Let $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ be a composition series.  Then, by 1, $$0=\ell(M_{0})<\ell(M_{1})<\dots< \ell(M_{n})=\ell(M)$$Hence, $\ell(M)\geq n$. But we have that $\ell(M)\leq n$. Therefore, $\ell(M)=n$. 
>  3. Let $M_{i+1}, M_{i}$ s.t. $M_{i+1} / M_{i}$ is not simple. Then, let $P$ be a non-trivial submodule and $\pi ^{-1}(P)$ is a submodule between $M_{i}$ and $M_{i+1}$ where $\pi:M_{i+1}\to M_{i+1} / M_{i}$. Hence, it follows.
---
> [!lemma] Proposition 2 (Additivity of Length)
> Let $M$ be a $R$-module and $N\leq M$. Then, 
> 1. $\ell(N)+\ell(M / N)=\ell(M)$.

> [!proof]+
> We have:
> 1. We first assume that $\ell(M)<\infty$. By Proposition 1.3, we can refine $0\leq N\leq M$ into a composition series. $$0 =N_{0}\subsetneq \dots\subsetneq N_{n}=N= M_{0}\subsetneq\dots\subsetneq M_{m}=M$$where $\ell(M)=n+m$ and $\ell(N)=n$. By setting $P_{i}:= M_{i} / N$, we get a chain:$$0=P_{0}\subsetneq\dots\subsetneq P_{m}=M / N$$To show that this is a composition series, we have that: $$P_{i+1}/P_{i}=(M_{i+1} / N) / (M_{i} / N)\cong M_{i+1} / M_{i}$$Hence is simple. Therefore, $\ell(M/N)=m$.  This shows the statement.
> 2. We now assume that $\ell(N)$ and $\ell(M/N)$ are finite. 