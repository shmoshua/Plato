#Definition #Algebra

> [!definition]
> Let $M$ be an $R$-[[module]]. 
> 1. The ***internal direct sum***  $M_{1}\oplus\dots \oplus M_{n}$ of [[Submodule|submodules]] $M_{1},\dots,M_{n}$ of $M$ is the set $M_{1}\times\dots \times M_{n}$ with component-wise addition and multiplication given by the bijective map: $$\pi:M_{1}\oplus \dots \oplus M_{n}\to M_{1}+\dots+M_{n},\quad (m_{1},\dots,m_{n})\mapsto m_{1}+\dots +m_{n}$$
> 2. The ***external direct sum*** of a collection $M_{1},\dots,M_{n}$ of $R$-modules is $M_{1}\times\dots \times M_{n}$ with component-wise addition and multiplication. Also called the ***direct product***.

- **Remark**: The direct sum $R_{1}\oplus\dots \oplus R_{n}$ is also a ring.
---
##### Properties
> [!lemma] Proposition 1
> Let $M_{1},\dots,M_{n}$ be submodules of an $R$-module $M$. Then, TFAE:
> 1. The map $\pi:M_{1}\times \dots \times M_{n}\to M_{1}+\dots+M_{n},(m_{1},\dots,m_{n})\mapsto m_{1}+\dots+ m_{n}$ is bijective.
> 2. $M_{j}\cap(M_{1}+\dots+ M_{j-1}+M_{j+1}+\dots+M_{n})=(0)$ for all $j\in [n]$.
> 3. every $x\in M_{1}+\dots+M_{n}$ can be uniquely written as $x=m_{1}+\dots+m_{n}$ with $m_{i}\in M_{i}$.

> [!proof]-
> We have:
> 1. (1=>2): Let $x\in M_{j}\cap(M_{1}+\dots+ M_{j-1}+M_{j+1}+\dots+M_{n})$. Then, we notice that $x+x\in M_{1}+\dots+M_{n}$ and 
---
##### Examples
- $\mathbb{R}\oplus \mathbb{R}$ is a ring, but not a [[Field|field]], as $(0,1)(1,0)=(0,0)$.
---