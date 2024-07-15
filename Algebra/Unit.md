#Algebra #Definition 

> [!definition]
> Let $R$ be a [[Ring|ring]]. An element $a\in R$ is called a ***unit***, if there exists $b,c\in R$ s.t. $$ab=1_{R}=ca$$i.e. $a$ is invertible.
- **Related definition**: A ring $R$ is a division ring if every $a\neq 0\in R$ is invertible, i.e. $R^\times=R \backslash \{ 0 \}$
---
##### Properties
> [!lemma] Proposition 1
> For the set $R^{*}$ defined as: $$R^{*}:=\{ a\in R:a\text{ is a unit} \},$$ $(R,\cdot)$ is a group called the ***unit group***.

> [!proof]-
> We show that:
> 	1. if $ab=1_{R}=ca$ then $b=c$:$$b=(ab)b=(ca)b=c(ab)=c$$
> 	2. $R^*$ is closed. If $a,b\in R^{*}$, $$(ab^{-1})(ba^{-1})=1_{R}$$Therefore,$ab^{-1}\in R^{*}$.
---
##### Example
- $\mathbb{Z}^{*}=\{ 1,-1 \}\cong C_{2}$
- $\mathbb{Z}[i]^{*}=\{ 1,-1,i,-i \}\cong C_{4}$
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
