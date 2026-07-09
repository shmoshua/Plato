#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]]. The ***Jacobson radical*** $J(R)$ of $R$ is given by:
> $$J(R):=\bigcap_{M\unlhd R,M\text{{ maximal}}}^{}M$$i.e. the intersection of all [[Maximal Ideal|maximal ideals]].

---
#### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring. TFAE:
> 1. $x\in J(R)$.
> 2. $1-xy\in R^\times$ for all $y\in R$.

> [!proof]-
> We have that:
> 1. (1=>2): Suppose $1-xy\notin R^\times$. Then, by [[maximal ideal|every ideal is contained in a maximal ideal]], it is contained in some maximal ideal $M\unlhd R$. But as $x\in M$, we have that $xy\in M$ and we have that $1\in M$, which is a contradiction.
> 2. (2=>1): Suppose $x\notin M$ for some maximal ideal $M$. Then $M$ and $x$ generate $R$, i.e. we have $u+xy=1$ for some $u\in M$ and $y\in R$. Hence, $1-xy\in M$ and is therefore not a unit.