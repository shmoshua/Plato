#Definition #RepresentationTheory 

> [!definition]
> Let $V$ be a [[representation]] of an algebra $A$. A ***(finite) filtration*** of $V$ is a sequence of subrepresentations $$0=V_{0}\subseteq V_{1}\subseteq\dots \subseteq V_{n}=V$$
---
##### Properties
> [!lemma] Lemma 1
> Any finite dimensional representation $V$ of an algebra $A$ admits a finite filtration $$0=V_{0}\subseteq V_{1}\subseteq\dots \subseteq V_{n}=V$$ s.t. the successive quotients $V_{i} / V_{i-1}$ are irreducible.

> [!proof]-
> Let us prove via induction on $n:=\text{dim}V$. The statement is clear for $n=1$. For $n>1$, pick an irreducible subrepresentation $V_{1}\subseteq V$ and consider $U:= V / V_{1}$. Then, by the induction hypothesis, $U$ has a filtration $$0=U_{0}\subseteq U_{1}\subseteq\dots \subseteq U_{n-1}=U$$Define $V_{i}=\pi ^{-1}(U_{i-1})$. Then, $$0=V_{0}\subseteq V_{1}\subseteq V_{2}\subseteq\dots \subseteq V_{n}=V$$
---
