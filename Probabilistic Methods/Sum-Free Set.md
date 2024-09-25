#Definition #ProbabilisticMethods 

> [!definition]
> Let $A\subseteq \mathbb{Z} \backslash \{ 0 \}$. A set $B\subseteq A$ is ***sum-free*** if $b_{1}+b_{2}\neq b_{3}$ for all $b_{1},b_{2},b_{3}\in B$. 

^a38971

---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> Let $A\subseteq \mathbb{Z} \backslash\{ 0 \}$ with $\left| A \right|=n$. Then, there exists a sum-free subset $B\subseteq A$ with size $\left| B \right|> \frac{n}{3}$.

^ae3312

> [!proof]-
> Let $p=3k+2$ be some prime s.t. $p>2\cdot \max_{a\in A}\left| a \right|$. Then, we can treat $A$ as a subset of $\mathbb{Z} / p\mathbb{Z} \backslash \{ 0 \}$. Let $I=[k+1,2k+1]$. Notice that $I$ is sum-free. Now, let $z\in \mathbb{Z} / p\mathbb{Z} \backslash\{ 0 \}$ chosen uniformly at random. We let $B:=zA\cap I\subseteq A$ be the set of elements $a\in A$ s.t. $za\in I$. Then, $B$ is sum-free as otherwise $b_{1}+b_{2}=b_{3}$ and $zb_{1}+zb_{2}=zb_{3}$. 
> 
> Now, let $X:=\left| zA\cap I \right|$ be a random variable. Then, $$\mathbb{E}[X]=\sum_{a\in A}^{}\mathbb{P}(za\in I)=n\cdot \frac{\left| I \right|}{p}=n\cdot \frac{k+1}{3k+2}> \frac{n}{3}$$where $\mathbb{P}(za\in I)=\left| I \right| / p$ as for any fixed $a$, $\{0, a,2a ,\dots,(p-1)a\}=A$.

^c6f226

- **Remark**: The bound is tight, Eberhard, Green and Manners have shown that for every fixed $\varepsilon>0$, there are $n$-element sets $A$ with no sum free subset of size $\left( \frac{1}{3}+\varepsilon \right) n$. ^68b7e6
---
