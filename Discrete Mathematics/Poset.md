#Definition 

> [!definition]
> A _**partial order**_ is a binary relation $\sqsubseteq\  \subseteq L\times L$ on a set $L$ with the following properties:
> 1. _**Reflexive**_: $\forall p\in L:p\sqsubseteq p$
> 2. _**Transitive**_: $\forall p,q,r\in L:(p\sqsubseteq q\land q\sqsubseteq r)\Longrightarrow p\sqsubseteq r$
> 3. _**Anti-symmetric**_: $\forall p,q\in L:(p\sqsubseteq q\land q\sqsubseteq p)\Longrightarrow p=q$
>    
> A ***poset*** is a tuple $(L,\sqsubseteq)$ where $L$ is a set and $\sqsubseteq$ is a partial ordering on $L$. A subset $Q \subseteq L$ is ***totally ordered*** if for all $p,q\in Q$, either $a \sqsubseteq b$ or $b \sqsubseteq a$.
> 
> For a poset $(L,\sqsubseteq)$ and a set $Y\subseteq L$:
> 1. $u\in L$ is an _**upper bound**_ of $Y$ if $\forall p\in Y:p\sqsubseteq u$
> 2. $l\in L$ is a _**lower bound**_ of $Y$ if $\forall p\in Y:l\sqsubseteq p$
> 
> An element $m \in L$ is ***maximal***, if $m \sqsubseteq x$ implies $m=x$. Finally, $L$ is ***inductive*** if every totally ordered subset $Q$ of $L$ has an ***upper bound***. 
---
##### Properties
> [!lemma] Lemma 1 (Zorn's Lemma)
> Let $(P,\leq)\neq \varnothing$ be a poset. If $P$ is inductive, then, $P$ admits a maximal element.