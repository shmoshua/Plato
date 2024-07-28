#Definition #Algebra 

> [!definition]
> A $R$-[[module]] $M$ is ***free*** if it has a basis, a linearly independent collection $\{ x_{i} \}_{i\in I}\subseteq M$ s.t. every $m\in M$ is a finite linear combination of the collection.
- **Related definition**: A free module is ***finite***, if the basis is finite with rank $n$, where $n$ is the number of basis elements.
- **Related definition**: An $R$-module $M$ is ***free*** on a subset $A\subseteq M$ if for all $m\in M$, there exists $x_{1},\dots,x_{k}\in A$ and $r_{1},\dots,r_{k}\in R$ s.t. $m=\sum_{i=1}^{k}r_{i}x_{i}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring and $M$ a $R$-module. Then, TFAE:
> 1. $M$ is a rank-$n$ free module.
> 2. $M\cong R^n$

> [!proof]-
> We have:
> 1. (1=>2): Let $M$ be a free module with basis $\{ x_{1},..,x_{n} \}$. Then, $Rx_{i}$ is a submodule and $R\to Rx_{i},r\mapsto rx_{i}$ is an isomorphism because $\{ x_{i} \}$ are linearly independent. Therefore, $$\psi:M\to Rx_{1}\oplus \dots \oplus  Rx_{n} $$is an isomorphism and $M\cong R^n$.
> 2. (2=>1): If $M\cong R^n$, with isomorphism $\varphi:R^n\to M$, then $\{ \varphi(e_{i}) \}_{i}$ form a basis. We have: $$\sum_{i=1}^{n}a_{i}\varphi(e_{i})=0 \implies\varphi(a_{1},\dots,a_{n})=0\implies (a_{1},\dots,a_{n})=0$$Further, for any $m\in M$, we have $\varphi ^{-1}(m)=(a_{1},\dots,a_{n})$.
---
> [!lemma] Proposition 2
> For any set $A$, there exists a $R$-module $M(A)$ free on $A$ s.t. 
> 1. if $N$ is any $R$-module, any map $\varphi:A\to N$ extends to $\Phi\in \text{Hom}_{R}(M(A),N)$ uniquely.
> 2. if $A=\{ a_{1},\dots,a_{n} \}$, then $M(A)=Ra_{1}\oplus\dots \oplus Ra_{n}$ 

> [!proof]-
> If $A=\varnothing$, then $M(A)=\{ 0 \}$. If $A\neq \varnothing$, we define: $$M(A):=\{ f:A\to R| f(a)=0\text{ almost everywhere} \}$$Then, this is a $R$-module with pointwise addition and multiplication. Further, $A\subseteq M(A)$ as $a\mapsto \chi_{a}$. 
> 
> Hence, for any $f\in M(A)$, we have $a_{1},..,a_{n}$ where $f$ does not vanish with $r_{1},\dots,r_{n}$ and: $$f=\sum_{i=1}^{k}r_{i}\chi_{a_{i}}$$Now, for any $\varphi:A\to N$, we define $\Phi:M(A)\to N,\ \sum_{i=1}^{n}r_{i}a_{i}\mapsto \sum_{i=1}^{n}r_{i}\varphi(a_{i})$. $\Phi$ is well-defined as the expression is unique and clearly, $\Phi|_{A}=\varphi$. Further, it is clearly a homomorphism. Lastly, it is unique as the values uniquely depend on $\varphi(a)$ for $a\in A$. 
---
> [!lemma] Theorem 3
> Let $R$ be a [[Principal Ideal Domain|PID]] and $M$ a free $R$-module of rank $n$. Then, for a [[submodule]] $N$, 
> 1. $N$ is free of rank $m$ for $m\leq n$.
> 2. there exists a basis $y_{1},\dots,y_{n}$ of $M$ s.t. $a_{1}y_{1},\dots,a_{m}y_{m}$ is a basis of $N$ with $a_{1},\dots,a_{m}\in R \backslash\{ 0 \}$ and $a_{i}|a_{i+1}.$
---
> [!lemma] Theorem 4 (Fundamental Theorem of Finitely Generated Modules over PID)
> Let $R$ be a PID and $M,M'$ finitely generated $R$-modules. Then,
> 1. $M\cong R^r\oplus R/(a_{1})\oplus\dots \oplus R / (a_{n})$ for some integer $r\geq 0$ called ***free rank*** with $a_{1},\dots,a_{n}\in R \backslash\{ 0 \}$ called ***invariant factors*** s.t. $a_{i}\notin R^\times$ and $a_{i}|a_{i+1}$.  
> 2. $M$ is torsion free if and only if $M$ is free.
> 3. $\text{Tor}(M)\cong R / (a_{1})\oplus\dots \oplus R / (a_{n})$.
> 4. $M$ is a torsion module if and only if $r=0$. In this case, $\text{Ann}(M)=(a_{n})$.
> 5. We also have: $$M\cong R^r\oplus R / (p_{1}^{\alpha_{1}})\oplus \dots \oplus R / (p_{t}^{\alpha_{t}})$$for some primes $p_{i}$ and integers $\alpha_{i}$, with $p_{i}^{\alpha_{i}}$ called as **elementary divisors**.
> 6. $M'$ has the same free rank and invariant factors, if and only if $M\cong M'$.
> 7. $M'$ has the same free rank and elementary divisors, if and only if $M\cong M'$.

> [!proof]-
> We have:
> 1. Let $x_{1},\dots,x_{n}$ be the set of generators of $M$ of minimal cardinality. Let $R^n$ be the free $R$-module of rank $n$ with basis $b_{1},\dots,b_{n}$. 
> 
> 	We then define the homomorphism $\pi:R^n\to M,b_{i}\mapsto x_{i}$. Then, we have: $$R^n / \text{ker }\pi\cong M$$Then, from Theorem 3 on $R^n$ and $\text{ker }\pi$ as the submodule, we can choose another basis $y_{1},\dots,y_{n}$ of $R^n$ s.t. $a_{1}y_{1},\dots,a_{m}y_{m}$ is a basis of $\text{ker }\pi$ with $a_{1},\dots,a_{m}\in R \backslash\{ 0 \}$ and $a_{i}|a_{i+1}$. Therefore, $$M\cong (Ry_{1}\oplus \dots \oplus Ry_{n}) / (Ra_{1}y_{1}\oplus \dots \oplus Ra_{m}y_{m})$$Then, we have the surjective homomorphism: $$\begin{array}{cccc} {\varphi:}&{Ry_{1}\oplus \dots \oplus Ry_{n}}&\to&{R / (a_{1})\oplus \dots \oplus R / (a_{m})\oplus R^{n-m}}\\&{(\alpha_{1}y_{1},\dots,\alpha_{n}y_{n})} &\mapsto & {(\alpha_{1}\text{ mod }a_{1},\dots,\alpha_{m}\text{ mod }a_{m},\alpha_{m+1},\dots,\alpha_{n})} \end{array}{} $$where $$\text{ker }\varphi:=Ra_{1}y_{1}\oplus \dots \oplus  Ra_{m}y_{m}$$
> 2. Since $R / (a)$ is a torsion module, we have that $\text{Tor}(M)\cong R / (a_{1})\oplus\dots \oplus R / (a_{n})$.
> 3. Therefore, $M$ is torsion free iff $(0)=R / (a_{1})\oplus\dots \oplus R / (a_{n})$ iff $M\cong R^r$ iff $M$ is free.
> 4. $M$ is a torsion module iff $\text{Tor}(M)=M$ iff $r=0$. 
> 5. As $R$ is a PID, it is a UFD and we have our unique factorization $a_{i}=up_{1}^{\alpha_{1}}\dots p_{m}^{\alpha_{m}}$ with $p_{i}$ primes. Hence, using the chinese remainder theorem, $$R / (a_{i})\cong R / (p_{1}^{\alpha_{1}})\oplus \dots \oplus R / (p_{m}^{\alpha_{m}})$$
---
##### Examples
> [!h] Example 1
> For any set $A$, 
> 1. The free $\mathbb{Z}$-module $M(A)$ is the free abelian group, isomorphic to $\mathbb{Z}^n$.
---
##### Non-Examples
> [!h] Non-Example 1
> 