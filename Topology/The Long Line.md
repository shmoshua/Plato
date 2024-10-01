#Definition #Topology 

> [!definition]
> Let $I$ be a totally-ordered, well-ordered uncountable set with the property that for any $a\in I$, the set $\{ i\in I:i\leq a \}$ is countable. Then, 
> 1. the ***long ray*** is given as: $$L:=\bigsqcup_{i\in I}^{}[0,1)$$
> 2. the ***long line*** is given by glueing two long rays together. 
---
##### Properties
> [!lemma] Proposition 1 (Existence of I)
> There exists a totally-ordered, well-ordered set $I$ that is not countable, s.t. 
> 1. for any $a\in I$, the set $\{ i\in I:i\leq a \}$ is countable. 

> [!proof]-
> By Zermelo's theorem, $\mathbb{R}$ can be given an ordering s.t. it is well-ordered. If this has the property above, we are done. Otherwise, let $$A:=\{ a\in \mathbb{R}:\{ i\in \mathbb{R}:i\leq a \}\text{ is not countable} \}$$This has a smallest element $b$. Then, we define $I$ as the set of all elements smaller than $b$, which is uncountable. However, we get the desired set. 
---
> [!lemma] Proposition 2
> For the long ray $L$, 
> 1. $L$ is totally ordered with $(i,s)<(j,t)$ if and only if $i<j$ or, $i=j$ and $s<t$.
> 2. $L$ can be endowed with the topology given by the base:
> 	- $[0,b):=\{ \ell\in L:0\leq \ell<b \}$ for $b\in L$ or
> 	- $(a,b):=\{ \ell\in L:a<\ell<b \}$ for $a,b\in L$
> 	
> 	where $0:=(i,0)$ with $i$ as the smallest element of $I$.
---
> [!lemma] Proposition 3
> We have that:
> 1. $L$ is not separable.
> 1. $L$ is not second countable.
> 2. $L$ is locally euclidean.
---
