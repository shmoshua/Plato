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

> [!proof]-
> We have:
> 1. follows from [[Localization|Proposition 2]].
> 2. Let $n:= \text{dim}R/P$ and $m:=\text{codim}P=\text{dim}R_{P}$. Then, there are chains of prime ideals: $$P_{0}\subsetneq\dots \subsetneq P_{m}\subseteq P,\quad P\subseteq Q_{0}\subsetneq\dots \subsetneq Q_{n}$$which gives us a chain of prime ideals of length $m+n$.
> 3. if $P_{0}\subsetneq \dots \subsetneq P_{n}$ then this also translates to $R / P$ where $P$ is any maximal ideal containing $P_{n}$. Conversely, any chain of prime ideals in the localization corresponds to one in $R$ of the same length.
---
> [!lemma] Lemma 2
> Let $R$ be a ring with $\text{dim}R<+\infty$ in which all maximal chains of prime ideals have the same length. Then, for $P\unlhd R$, 
> 1. $\text{dim} R / P< \infty$ and every maximal chain of prime ideals in $R / P$ have the same length.
> 2. $\text{dim}R=\text{dim}R/P+\text{codim}P$.
> 3. $\text{dim}R_{P}=\text{dim}R$ if $P$ is maximal.

> [!proof]-
> We have:
> 1. As the chains of prime ideals in $R$ correspond to the chains of prime ideals in $R / P$. 
> 2. $\geq$ is given by Proposition 1.2. For the converse, for any maximal chain of prime ideals in $R$, we can find the corresponding chain of prime of ideals in $R / P$ and by maximality we must have $Q_{0}=P$. Hence, $$\text{dim}R\leq \text{dim}R / P+\text{codim}P$$
> 3. If $P$ is maximal $R /P$ is a field and $\text{dim}R / P=0$. 

---
> [!lemma] Proposition 3
> Let $R$ be a [[Noetherian and Artinian Module|Noetherian ring]]. Let $I\unlhd R$.
> $$\text{dim}R / I=\max\{ \text{dim} R / P:P\text{ is an isolated prime ideal of }I \}$$

> [!proof]-
> We have that by [[Primary Ideal|Primary Decomposition in Noetherian Rings Proposition 1]], the isolated prime ideals of $I$ are exactly the minimal prime ideals containing $I$. Therefore, for any isolated prime ideal $P$ of $I$:$$P\subsetneq P_{0}\subseteq \dots \subseteq P_{n}$$be a chain of prime ideals s.t. $\text{dim}R / P=n$. Hence, $I\subseteq P\subsetneq P_{0}\subseteq \dots \subseteq P_{n}$ and $\text{dim}R / I\geq n$. 
> 
> Conversely, if $I\subseteq P_{0}\subsetneq \dots \subsetneq P_{n}$ is a chain of prime ideals s.t. $\text{dim} R / I=n$. Then, $P_{0}$ is an isolated prime ideal. Otherwise there exists $I\subseteq P\subsetneq P$ for a prime $P$ and $\text{dim} R / I\geq n+ 1$. Therefore, $\text{dim}R / I\leq \text{dim}R / P_{0}$. 
---
> [!lemma] Proposition 4 (Invariance of dimension under integral extensions)
> Let $R':R$ be an [[Ring Extension|integral ring extension]]. Then, $\text{dim}R=\text{dim}R'$.

> [!proof]-
> We have:
> 1. $\leq$: Let $P_{0}\subsetneq\dots \subsetneq P_{n}$ be a chain of prime ideals in $R$. Then, by [[Ring Extension|Lying over]] and [[Ring Extension|Going up]], we get a chain of prime ideals $P'_{0}\subsetneq\dots \subsetneq P'_{n}$ in $R'$.
> 2. $\geq$: Let $P'_{0}\subsetneq \dots \subsetneq P_{n}'$ be a chain of prime ideals in $R'$. Then, by taking the chain intersected with $R$, i.e. $P_{i}:= P_{i}'\cap R$, we get $P_{0}\subseteq\dots \subseteq P_{n}$ where the strictness comes from [[Ring Extension|Imcomparability]].

---
> [!lemma] Proposition 5 (Dimension of Polynomial Rings)
> Let $K$ be a field. 
> 1. $\text{dim}K[x_{1},\dots,x_{n}]=n$.
> 2. all maximal chains of prime ideals in $K[x_{1},\dots,x_{n}]$ have length $n$.

> [!proof]+
> We prove both by induction on $n$. 
> 1. If $n=0$, then $\text{dim}K=0$ and all maximal chains have length $n$.
> 2. if $n\geq 1$ and let $P_{0}\subsetneq\dots \subsetneq P_{m}$ be a chain of prime ideals in $K[x_{1},\dots,x_{n}]$. We have to show that $m\leq n$ and that equality holds for a maximal chain. 
>    
>    By possibly extending the chain, we may assume that $P_{0}=0$, $P_{1}$ is a minimal non-zero prime ideal and $P_{m}$ is a maximal ideal. Then, $P_{1}=(f)$ for some non-zero $f$ by [[Noetherian and Artinian Module|Noetherian Rings Proposition 3.2]], as $K[x_{1},\dots,x_{n}]$ is a UFD.
>    
>    By changing the coordinates similarly to the [[Algebra|proof of Noether normalization]], we may assume wlog that $f$ is monic in $x_{n}$. Hence, $K[x_{1},\dots,x_{n}] / (f)$ is integral over $K[x_{1},\dots,x_{n-1}]$ by [[Ring Extension|Proposition 1]]. 
>    
>    Now, we can take $P_{i}$ and extend it to $P_{i} / P_{1}\unlhd K[x_{1},\dots,x_{n}] / P_{1}$ and contract it to $(P_{i} / P_{1})\cap K[x_{1},\dots,x_{n-1}]$ in $K[x_{1},\dots,x_{n-1}]$. Then, both these steps preserve prime ideals and their strict inclusions. Hence, it transfers maximal chains to maximal chains. 
---
##### Examples 
> [!h] Example 1
> We have that:
> 1. Any field $K$ has dimension $0$.
> 2. $\text{dim}R=0$ if and only if all prime ideals are maximal.
> 3. A [[Principal Ideal Domain|PID]] $R$ that is not a field, then $\text{dim}R=1$ with $0\subsetneq P$ as a chain for any non-zero prime.
> 4. 