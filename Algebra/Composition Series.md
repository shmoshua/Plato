#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module. 
> 1. A ***composition series*** of $M$ is a finite chain: $$0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M $$of submodules s.t. there is no submodule $N$ with $M_{i-1}\subsetneq N\subsetneq M_{i}$ for all $i$.
> 2. the ***length*** of $M$, denoted as $\ell_{R}(M)$ is the shortest length of a composition series of $M$. If $M$ does not admit a composition series, then $\ell _R(M):=\infty$. 
- **Remark**: From [[module|Proposition 5]], $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ forms a composition series if and only if $M_{i} / M_{i-1}$ has no non-trivial proper submodules for all $i$. 
---
##### Properties
> [!lemma] Proposition 1 (Length)
> Let $M$ be a $R$-module of finite length. 
> 1. if $N<M$ be proper submodule. Then, $\ell(N)<\ell(M)$.
> 2. every composition series of $M$ has length $\ell(M)$.
> 3. every chain $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ can be refined into a composition series.

> [!proof]+
> We have:
> 1. Let $n:=\ell(M)$ and  $0=M_{0}\subsetneq M_{1}\subsetneq\dots\subsetneq M_{n} =M$ be a composition series of $M$. Consider,  $$0=N\cap M_{0}\subsetneq N\cap M_{1}\subsetneq\dots\subsetneq N\cap M_{n} =N\cap M $$ is a chain of submodules from $N$ to $0$. Then, by the isomorphism theorem, $$(N\cap M_{i}) / (N\cap M_{i-1})=(N\cap M_{i}) / (N\cap M_{i}\cap M_{i-1})\cong (N\cap M_{i}+M_{i-1}) / M_{i-1}$$which is a submodule of $M_{i} / M_{i+1}$, which is simple. 