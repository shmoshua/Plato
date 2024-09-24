#Algebra #Definition 

> [!definition]
> Let $R$ be a [[Ring|ring]]. An element $a\in R$ is called a ***unit***, if there exists $b,c\in R$ s.t. $$ab=1_{R}=ca$$i.e. $a$ is invertible.

^4f9ab4

- **Related definition**: A ring $R$ is a division ring if every $a\neq 0\in R$ is invertible, i.e. $R^\times=R \backslash \{ 0 \}$ ^66fef9
---
##### Properties
> [!lemma] Proposition 1
> For the set $R^{\times}$ defined as: $$R^{\times}:=\{ a\in R:a\text{ is a unit} \},$$ $(R^\times,\cdot)$ is a group called the ***unit group***.

> [!proof]-
> We show that:
> 	1. if $ab=1_{R}=ca$ then $b=c$:$$b=(ab)b=(ca)b=c(ab)=c$$
> 	2. $R^*$ is closed. If $a,b\in R^{*}$, $$(ab^{-1})(ba^{-1})=1_{R}$$Therefore,$ab^{-1}\in R^{*}$.
---
##### Example
- $\mathbb{Z}^{\times}=\{ 1,-1 \}\cong C_{2}$
- $\mathbb{Z}[i]^{\times}=\{ 1,-1,i,-i \}\cong C_{4}$
-  $(\mathbb{Z} / 15\mathbb{Z})^{*}=\{ \overline{1},\overline{2},\overline{4},\overline{7},\overline{8},\overline{11},\overline{13},\overline{14} \}=\braket{ \overline{14}  }\times \braket{ \overline{2}  }\cong C_{2}\times C_{4}$
- $(\mathbb{Z} / 10\mathbb{Z})^{*}=\{ \overline{1},\overline{3},\overline{7},\overline{9} \}\cong C_{4}$
---
##### Unit group of $\mathbb{Z}/n\mathbb{Z}$
> [!lemma] Proposition 2
> $$\overline{a}\in (\mathbb{Z} / n\mathbb{Z})^{*}\iff \gcd(a,n)=1$$

> [!proof]-
> =>: If $\gcd(a,n)> 1$
> <=: Euclidean algorithm: 
> - $a_{0}=b_{0}\cdot a_{1}+a_{2}$ with $0<b_{0}$
> - $a_{1}=$
---
##### Examples
> [!h] Example
> We have that:
> 1. $\mathbb{Z}[i]^\times=\{ 1,-1,i,-i \}$
> 2. $\mathbb{Z}[ni]^\times=\{ 1,-1 \}$ for $n>1$.

> [!proof]-
> Let $(a+bni)\in \mathbb{Z}[ni]^\times$. Then, either $a\neq 0$ or $b\neq 0$. If we have: $$(a+bni)(c+dni)=(ac-n^2bd)+n(ad+bc)i=1$$Then, $ad=-bc$ and: 
> 1. if $a\neq0$, then $d=-bc /a$ and $a^2c+n^2b^2c=a$ from which we have $c=\frac{a}{a^2+n^2b^2}$
> 2. if $a=0$, then as $b\neq 0$, $c=0$ and $c=\frac{a}{a^2+n^2b^2}$.
> 3. if $b\neq 0$, then $c=-\frac{ad}{b}$ and ${a^2d}+n^2b^2d=-b$ from which we have $d=-\frac{b}{a^2+n^2b^2}$.
> 4. if $b=0$, then as $a\neq 0$, $d=0$ and $d=-\frac{b}{a^2+n^2b^2}$.
>    
> Let $x=a^2+n^2b^2\in \mathbb{Z}_{>0}$. As $c,d$ are integers, $a,b$ must be divisible by $x$. 
> 
> Let $a=px$ and $b=qx$.  Then, $p^2x^2+n^2q^2x^2=x$. Therefore, $(p^2+n^2q^2)x=1$. Therefore, $x=1$ and $p^2+n^2q^2=1$. From which we have that $p^2=1$ and $q^2=0$, i.e. $1,-1\in \mathbb{Z}[ni]^\times$.
> 
> Otherwise, if $n=1$, then $p^2=0$ and $q^2=1$ from which we get $i,-i\in \mathbb{Z}[ni]^\times$. 
---
