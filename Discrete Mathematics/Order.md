#Definition 

> [!definition]
> Let $\leq$ be a binary relation on a set $M$.
> 1. $\leq$ is a ***partial order*** if:
> 	1. **reflexive**: $a\leq a$ for all $a\in M$.
> 	2. **transitive**: if $a\leq b$ and $b\leq c$ then $a\leq c$ for all $a,b,c\in M$.
> 	3. **anti-symmetric**: if $a\leq b$ and $b\leq a$ then $a=b$ for all $a,b\in M$.
> 2. $\leq$ is a ***total order*** if $\leq$ is a partial order and for all $a,b\in M$ either $a\leq b$ or $b\leq a$. 
> 3. for a set $A\subseteq M$, $b\in M$ is an ***upper bound*** if $a\leq b$ for all $a\in A$.
> 4. for a set $A\subseteq M$, $b\in M$ is an ***lower bound*** if $b\leq a$ for all $a\in A$.
> 5. $a\in M$ is ***maximal*** if $a\leq b$ implies $a=b$ for any $b\in M$.

- **Related definition**: If $\leq$ is a partial order on $M$, the tuple $(M,\leq)$ is called a ***poset***.
- **Related definition**: A poset $(M,\leq)$ is ***inductive*** if every totally ordered subset $A\subseteq M$ has an upper bound.

---
##### Properties
> [!lemma] Lemma 1 (Zorn's Lemma)
> Let $(M,\leq)$ be a non-empty poset.
> 1.  If $M$ is inductive, then, $M$ admits a maximal element.