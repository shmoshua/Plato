#Algebra #Definition 

> [!definition]
> Let $R$ be a [[ring]]. The ***nilradical*** of $R$ is defined as the [[Radical (Ring)|radical]] of $(0)$, i.e.: $$\sqrt{ (0) }:=\{ a\in R: a^n=0\text{ for some }n\in \mathbb{N} \}$$

^2063c5

- **Related definition**: The elements of the nilradical are called ***nilpotent***. ^107274
- **Related definition**: A ring $R$ is ***reduced*** if $\sqrt{ (0) }=(0)$, i.e. $(0)$ is radical. ^417ef2
- **Remark**: the nilradical is given by $\sqrt{ (0) }=\bigcap_{P\unlhd R, P\text{ prime}}^{} P$. (cf. [[Radical (Ring)|Lemma 2]])
---
##### Property
> [!lemma] Lemma 1
> For a ring $R$ and $I\unlhd R$, TFAE:
> 1. $I$ is radical.
> 2. $R / I$ is reduced.

^ec2c2e

> [!proof]-
> We have that $I$ is radical if and only if for all $a\in R$ and $n\geq 1$, $a^n\in I$ implies $a\in I$. By passing to the quotient $R/I$, this is equivalent to for all $a\in R / I$ and $n\geq 1$, $a^n\in 0$ implies that $a= 0$. Hence, $I$ is radical if and only if $(0)_{R / I}$ is radical and $R / I$ is reduced.

^f5705d

---
> [!lemma] Proposition 2
> For a commutative ring $R$, TFAE:
> 1. $R$ has exactly one prime ideal.
> 2. for all $a\in R$, $a$ is a unit or nilpotent.
> 3. $\sqrt{ (0) }$ is a maximal ideal.

> [!proof]-
> We have that:
> 1. (1=>2): Let $R$ have one prime ideal $P$. Then, $\sqrt{ (0) }=P$ by [[Radical (Ring)|Lemma 2]]. Now, assume there exists $a\in R$ where $a$ is nor a unit. Then, consider $I:=(a)$, which is contained in some maximal ideal $M$ by [[Maximal Ideal|Theorem 2]]. 
>    
>    As $M$ is prime, we have that $M=\sqrt{ (0) }$ and $a\in \sqrt{ (0) }$. Hence, $a$ is nilpotent.
> 2. (2=>3): Assume $\sqrt{ (0) }$ is not maximal, i.e. $\sqrt{ (0) }\subsetneq M\subsetneq R$. Then, let $a\in M \backslash \sqrt{ (0) }$. This element is not a unit nor nilpotent. 
> 3. (3=>1): Let there be two distinct prime ideals $I,J$. Then, $\sqrt{ (0) }\subseteq I\cap J$. Hence, $\sqrt{ (0) }$ cannot be maximal.
---
