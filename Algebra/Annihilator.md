#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]] and $M$ a $R$-[[module]].
> 1. for $N,N'\leq M$, a ***module quotient*** is given as: $$N'{:}N:=\{ a\in R: aN\subseteq N' \}$$
> 2. the ***annihilator*** of $N\leq M$ is given as: $\text{Ann }N:=\{ a\in R:aN = 0 \}$, i.e. $0{:}N$.
- **Related definition**: We can apply these definitions to a single element and get:
	1. $N'{:}m:=\{ a\in R :am \subseteq N' \}$ and
	2. $\text{Ann }m:=\{ a\in R:am=0 \}$.
- **Remark**: if $M$ is a ring itself, then the definitions coincide with ones defined on ideals.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $N'{:}N\unlhd R$, in particular $\text{Ann }N\unlhd R$.
> 3. $N'{:}m\unlhd R$, in particular $\text{Ann }m\unlhd R$.
> 4. if $I\unlhd R$, then $\text{Ann}(R / I)=I$.

> [!proof]-
> We have: 
> 1. for $a,b\in N'{:}N$, $(a+b)N\subseteq N'$ and for every $r\in R$, $raN \subseteq rN'\subseteq N'$ and $ra\in N'{:}N$.
> 3. for $a,b\in N'{:}m$, $(a+b)m=N'$ and for every $r\in R$, $ram\subseteq rN'\subseteq N'$ and $ra\in N'{:}m$.
> 4. $\text{Ann}(R / I)=\{ a\in R:ar+I = 0, \forall r\in R \}=I$.
---