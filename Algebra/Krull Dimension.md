#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]].
> 1. The ***Krull dimension*** $\text{dim}R$ of $R$ is the maximum number $n\in\mathbb{N}$ s.t there is a chain of [[Prime Ideal|prime ideals]]: $$P_{0}\subsetneq P_{1}\subsetneq\dots \subsetneq P_{n}$$of length $n$ in $R$. 
> 2. The ***codimension/height*** $\text{codim}_{R}P$of a prime $P\unlhd R$ is the maximum number $n\in \mathbb{N}$ s.t. there is a chain of prime ideals as above with $P_{n}\subseteq P$.
> 
> If such maximum number doesn't exist, then $\text{dim}R=\infty$ and $\text{codim}_{R}P=\infty$.
---
##### Properties
> [!lemma] Proposition 1 (Properties of a Dimension)
> Let $R$ be a ring.
> 1. for any prime $P\unlhd R$, $\text{codim}P=\text{dim}R_{P}$.
> 2. for any prime $P\unlhd R$, $\text{dim}R\geq \text{dim}R / P+\text{codim}P$
> 3. dimension is a local property, i.e. $$\text{dim}R=\sup_{P\in \text{Max}(R)}\text{dim}R_{P}$$

> [!proof]+
> We have:
> 1. follows from [[Localization|Proposition 2]].
> 2. Let $n:= \text{dim}R/P$ and $m:=\text{codim}P=\text{dim}R_{P}$. Then, there are chains of prime ideals: $$P_{0}\subsetneq\dots \subsetneq P_{m}\subseteq P,\quad P\subseteq Q_{0}\subsetneq\dots \subsetneq Q_{n}$$which gives us a chain of prime ideals of length $m+n$.
> 3. if $P_{0}\subsetneq \dots \subsetneq P_{n}$ then this also translates to $R / P$ where $P$ is any maximal ideal containing $P_{n}$. 

---
##### Examples 
> [!h] Example 1
> We have that:
> 1. Any field $K$ has dimension $0$.
> 2. $\text{dim}R=0$ if and only if all prime ideals are maximal.
> 3. A [[Principal Ideal Domain|PID]] $R$ that is not a field, then $\text{dim}R=1$ with $0\subsetneq P$ as a chain for any non-zero prime.
> 4. 