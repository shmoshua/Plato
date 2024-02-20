#Definition #Algebra

> [!definition]
> The ***dihedral group*** of degree $n\geq 3$, denoted as $(D_{n},\cdot)$ is defined as the group of [[Rigid Motions|rigid motions]] of a regular $n$-sided polygon. Formally, $$D_{n}:=\braket{ \rho, \sigma|\rho^n=e,\sigma^{2}=e,\sigma\rho=\rho^{n-1}\sigma } $$
---
> [!lemma] Proposition 1
> For every $m\mid n$, there exists $N\unlhd D_{n}$ with $\left| N \right|=m$.

> [!proof]-
> Let $k=n / m$. Then, $\text{ord}(\rho^k)=m$. Therefore, we just need to show that $\braket{ \rho^k  }\unlhd D_{n}$. We have: 
> 1. $\rho^\ell\rho^k\rho^{-\ell}=\rho^k\in \braket{ \rho^k  }$ 
> 2. $\sigma\rho^k\sigma=\sigma\sigma\rho^{n-k}=\rho^{n-k}=\rho^{k(m-1)}\in \braket{ \rho^k  }$
> 
> This proves the statement.
---
##### Properties
- $D_{3}=\{ \text{id}, \rho_{1},\rho_{2},\sigma_{1},\sigma_{2},\sigma_{3} \}$ where $\rho_{1},\rho_{2}$ are rotations with angle $\frac{2\pi}{3}$ and $\frac{4\pi}{3}$ respectively and $\sigma_{1},\sigma_{2},\sigma_{3}$ are the three reflections. If we label the vertices of the regular triangle with $1,2$ and $3$, then every permutation of $\{  1,2,3 \}$ corresponds to an element of $D_{3}$, and since $|D_{3}|=|S_{3}|$, we have $D_{3}\cong S_{3}$.
- For every $n\geq 3$, $D_{n}$ is non-abelian.
- For every $n\geq 3$, $D_{n}$ has the [[Normal Subgroup|normal divisor]] $C_{n}$ and $[D_{n} : C_{n}]=2$. Therefore, $D_{n} / C_{n}\cong C_{2}$.
- $D_{n}$ has a normal subgroup of order $x$ if $x| n$.
---
