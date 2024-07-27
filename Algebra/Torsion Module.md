#Definition #Algebra 

> [!definition]
> For an [[integral domain]] $R$ and a $R$-[[module]] $M$, 
> 1. $m\in M$ is a ***torsion element*** if $rm=0$ for some $0\neq r\in R$.
> 2. the ***torsion submodule*** $\text{Tor}(M)\subseteq M$ is the set of all torsion elements.
> 3. $M$ is a ***torsion module*** if $\text{Tor}(M)=M$.
- **Related definition**: A module is a ***torsion free module*** if $\text{Tor}(M)=(0)$.
- **Remark**: if $R$ is not an integral domain, $\text{Tor}(M)$ is not a submodule.
- **Related definition**: The ***annihilator*** of $M$ is $\text{Ann}(M):=\{ r\in R:rM=(0) \}$.
---
##### Examples
> [!h] Example 1
> For an integral domain $R$ and $(0)\neq I\unlhd R$, 
> 1. $R / I$ is a torsion module.

> [!proof]-
> For $m+I\in R / I$, get $a\in I \backslash\{ 0 \}$. Then, $$a(m+I)=\underbrace{ am }_{ \in I }+I=I$$