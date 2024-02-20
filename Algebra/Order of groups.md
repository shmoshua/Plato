#Definition #Algebra

> [!Definition]
> For a [[group]] $G$, the **order** of the group denoted by $|G|$ is the cardinality of $G$.
> 
> For a group $G$ and an element $x\in G$, the **order** of $x$ denoted by $\text{ord}(x)$ is the least positive integer, s.t. $$x^n=e$$
> If such integer does not exist, $\text{ord}(x)=\infty$.

- If $G$ has finitely many elements, then $|G|=n$ for some positive integer $n$ and if $G$ is infinite, then we set $|G|=\infty$.
- There are no groups with order 0, because a group *needs to have a neutral element*.
---
> [!lemma] Proposition 1
> If $G$ is a finite group with $\left| G \right|=m$ and $x\in G$, then $\text{ord}(x)\leq m$.

> [!proof]-
> As $G$ is finite, there is going to be $0<n<m$ s.t. $x^n=x^m=x^nx^{m-n}$. By cancellation, we have $e=x^{m-n}$, where $m-n$ is a positive integer. 
---
> [!lemma] Proposition 2
> Let $G$ be a group and $x\in G$ with finite order. Then, for any $k\in \mathbb{N}$, it holds that: $$\text{ord}(x^k)= \frac{\text{lcm}(k,\text{ord}(x))}{k}$$

> [!proof]-
> Let $t:=\text{lcm}(k,\text{ord}(g))/k$. From the definition, $t$ is the smallest number s.t. $\text{ord}(g)|kt$ . However, we also have that for any $n$:$$ g^n=e\iff \text{ord}(g)|n $$Therefore, $t$ is the smallest number s.t. $g^{kt}=e$. It follows that $\text{ord}(g^k)=t$.
---
> [!lemma] Proposition 3
> Let $g,h\in G$ commute and $\gcd(\text{ord}(g),\text{ord}(h))=1$. Then, $$\text{ord}(gh)=\text{ord}(g)\cdot \text{ord}(h)$$

> [!proof]-
> Let $\text{org}(g)=m$ and $\text{org}(h)=n$, s.t. $\gcd(m,n)=1$. Let $x$ be s.t. $(gh)^x = e$. Then, we have:
> 1.  $e=(gh)^{xm}=h^{xm}$ and $n|xm$ and $n|x$.
> 2. $e=(gh)^{xn}=g^{xn}$ and $m|xn$ and $m|x$.
>    
> Combining these two, we have $mn|x$ and $\text{ord}(gh)$ is smallest such $x$, therefore, $\text{ord}(gh)=mn$.
---
> [!lemma] Theorem 4 (Cauchy)
> Let $G$ be a finite group and $p$ a prime number s.t. $p\mid \left| G \right|$. Then, there exists $a\in G$ s.t. $\text{ord}(a)=p$. 

> [!proof]-
> We will use induction over $\left| G \right|$.
> 1. If $\left| G \right|=1$, then it trivially holds.
> 2. If $\left| G \right|>1$, assume that (1) holds for $G'$ with $\left| G' \right|<G$. Consider the [[Conjugation (Group Theory)|conjugation]] $G \curvearrowright G$, defined as $(a,x)\mapsto a x a^{-1}$. Then, $$\left| G \right| =\left| Z(G) \right| +\sum_{j=1}^{s}[G:Z_{G}(x_{j})]$$for all $x_{j}$ with orbit size $>1$. 
> 
> If $s=0$, then $Z(G)=G$. As $Z(G)$ is abelian, $$Z(G)\cong C_{n_{1}}\times C_{n_{2}}\times\dots \times C_{n_{s}}$$with $n_{i}|n_{i+1}$. It follows that, $p|n_{s}$. Therefore, there exists $a\in Z(G)$ with $\text{ord}(a)=p$.
> 
> If $s>0$, then $Z(G)<G$ and there exists $x_{j}$ s.t. $[G:Z_{G}(x_{j})]\geq 1$. We can then do a case distinction: 
> 1. For all $1\leq j\leq s$, $p|[G:Z_{G}(x_{j})]$. Then, $p|\left| Z(G) \right|$ with the same reasoning as above, there exists $a\in Z(G)$ with $\text{ord}(a)=p$.
> 2. There exists $1\leq j_{0}\leq s$ s.t. $p \nmid [G:Z_{G}(x_{j_{0}})]$. Then, $|Z_{G}(x_{j_{0}})|<|G|$ and $p|\left| Z_{G}(x_{j_{0}}) \right|$. Therefore, from the induction hypothesis, there exists an element $a\in G$ with order $\text{ord}(a)=p$.
---