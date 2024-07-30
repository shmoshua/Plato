#Definition  #Algebra 

> [!definition]
> For a commutative [[ring]] $R$, an $R$-[[module]] $M$ is ***Noetherian*** if:
> 1. for an ascending chain of [[Submodule|submodules]] $M_{1}\subseteq M_{2}\subseteq\dots$ of $M$, there exists $m\in \mathbb{N}$ s.t. $M_{k}=M_{m}$ for all $k\geq m$.

---
##### Properties
> [!lemma] Theorem 1 (Equivalence of Noetherian Modules)
> Let $M$ be a $R$-module. Then, TFAE:
> 1. $M$ is Noetherian.
> 2. every non-empty subset of submodules of $M$ contains a maximal element under inclusion. 
> 3. every submodule of $M$ is finitely generated.

> [!proof]-
> We have that:
> 1. (1=>2): Let $M$ be Noetherian. We will use Zorn's lemma. Let $\mathcal{M}$ be the non-empty set of submodules of $M$. Then, $M$ being Noetherian gives us that $\mathcal{M}$ is inductive and by Zorn's lemma $\mathcal{M}$ admits a maximal element under inclusion.
> 2. (2=>3): Let $N$ be a submodule of $M$. Further let: $$\mathcal{M}:=\{ N'\subseteq N:N'\text{ is a finitely generated submodule of }M \}$$Then, as $(0)$ is a submodule, $\mathcal{M}$ is non-empty and $\mathcal{M}$ has a maximal element $N'$. However, for any $n\in N$, $N'+Rn$ is a finitely generated submodule of $M$ contained in $N$. Therefore, we have that $N'+Rn=N'$ and $n\in N'$. This shows that $N'=N$ and $N$ is finitely generated.
> 3. (3=>1): Assume that there exists an ascending chain $M_{1}\subseteq M_{2}\subseteq\dots$ that violates the Noetherian condition. Then, wlog we can assume that the chain is strictly ascending. Then, $M$ cannot be finitely generated. 
---
##### Examples
> [!h] Example 1 (PID)
> For a [[Principal Ideal Domain|PID]] $R$, every submodule of $R$ is an ideal $I=(a)$. Hence, 
> 1. every submodule of $M$ is finitely generated and $R$ is Noetherian.  