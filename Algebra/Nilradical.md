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
> [!lemma] Proposition 3
> Let $x\in N(R)$. Then,
> 1. $1+x\in R^\times$.

> [!proof]-
> We have that:
> 1. Assume that $1+x\notin R^\times$. Then, there exists a maximal ideal $M$ containing $1+x$. However, as every maximal ideal is prime, we have that $x\in M$. Hence, $1\in M$, which is a contradiction.

---
##### Examples
> [!h] Example 1
> Let $R$ be a commutative ring. Let $f=a_{0}+a_{1}X+\dots+a_{n}X^n \in R[X]$.
> 1. $f\in R[X]^\times$ if and only if $a_{0}\in R^\times$ and $a_{1},\dots,a_{n}\in N(R)$.
> 2. $f\in N(R[X])$ if and only if $a_{0},\dots,a_{n}\in N(R)$.
> 3. $f$ is a zero-divisor if and only if $\exists a\ne 0$ s.t. $af = 0$.
> 4. $f$ is called primitive if $(a_{0},\dots,a_{n})=R$. For $f,g\in R[X]$, $fg$ is primitive if and only if $f,g$ are primitive.

> [!proof]-
> We have that:
> 1. Suppose $f\in R[X]^\times$. Then, there exists $g=b_{0}+b_{1}X+\dots+b_{m}X^m\in R[X]$ s.t. $fg = 1$. Hence, $a_{0}b_{0}=1$ and $a_{0}\in R^\times$. We claim that $a_{n}^{m+1}=0$. First, notice that $a_{n}b_{m}=0$. Now, for degree $n+m-1$ we have:$$a_{n}^2b_{m-1}+ a_{n-1}(a_{n}b_{m})=0$$Hence, $a^2_{n}b_{m-1}=0$. We can continue to get $a^{m+1}_{n}b_{0}=0$. However, as $b_{0}\in R^\times$, we have that $a^{m+1}_{n}=0$. Now, we get that $f-a_{n}X^n$ is a unit in $R[X]$. Hence, we can repeat the same process as above to get that $a_{1},\dots,a_{n}$ are nilpotent. 
>    
>    Conversely, assume $a_{0}$ is a unit and $a_{1},\dots,a_{n}$ are nilpotent. Then, $a_{i}X^i$ is nilpotent. Then, the sum of nilpotent elements is nilpotent. Further, the sum of nilpotent element and a unit is a unit. This shows the statement. 
> 1. Suppose $f\in N(R[X])$. Let $f^k=0$. Then, $a_{0}\in N(R)$ and $a_{n}\in N(R)$. Now, $f-a_{n}X^n$ is also nilpotent and we can continue to get it for $a_{1},\dots,a_{n}$. Conversely, the sum of nilpotent elements is nilpotent. 
> 2. Let $g$ be a polynomial with minimal degree s.t. $fg = 0$ for $g=b_{0}+b_{1}X+\dots+b_{m}X^m$. Then, we know that $a_{n}b_{m}=0$. However, as $a_{n}fg=0$ and $\deg(a_{n}g)<m$, we have that $a_{n}g=0$. We show via induction that $a_{n-i}g=0$. Suppose $a_{n-i}g=0$. 
> 3. If $fg$ is primitive then $\left( \sum_{i}^{}a_{k-i}b_{i} \right)_{k}=R$. 

---
> [!h] Example 2
> A ring $R$ is called boolean if $x^2=x$ for all $x\in R$. In a boolean ring $R$,
> 1. $2x=0$ for all $x\in R$.
> 2. every prime ideal $P$ is maximal and $R / P$ is a field with two elements. 
> 3. every finitely generated ideal in $R$ is principal.

> [!proof]-
> We have that:
> 1. $2x = 4x^2 =  4x$ and $2x = 0$.
> 2. Let $P$ be a prime ideal. Then, $R / P$ is an integral domain with $x(x-1) = 0$. Therefore, we have that $x-1 = 0$. Hence, $R / P$ has two elements $x= 0,1$.
> 3. We show that for $\braket{ x , y }=\braket{ e  }$ for $e:=x+y+xy$. We have that $e\in \braket{ x , y }$ and conversely,$$xe=x^2+2xy=x^2=x$$Hence, they are the same ideal.