#Definition #Algebra

> [!definition]
> Let $R$ be a non-trivial [[ring]]. Two [[Ideal (Ring)|ideals]] $I,J\unlhd R$ are ***coprime*** if $I+J=R$.

^d314f8

---
##### Properties
> [!lemma] Proposition 1 (Powers of Coprime are Coprime)
> Let $I,J\unlhd R$ be coprime. Then, 
> 1. $I^n, J^m$ are coprime for all $n,m\in \mathbb{N}$.

^02798c

> [!proof]-
> Assume $I^n+J^m\subsetneq R$. Then, there exists some maximal ideal $M$ s.t. $I^n+J^m\subseteq M$. Therefore, $I^n\subseteq M$ and $J^m\subseteq M$. However, then for any $a\in I$, $a^n\in I^n \subseteq M$ and as $M$ is maximal, hence prime, $a\in M$. Therefore, $I\subseteq M$ and similarly $J\subseteq M$. 
>  
> This shows that $I+J\subseteq M$, which is a contradiction to $I,J$ being coprime.  


---
> [!lemma] Theorem 2
> Let $R$ be a commutative ring and $I_{1},\dots,I_{n}$ be pairwise coprime ideals. Then, $$I_{1}\cdot \dots \cdot I_{n}=I_{1}\cap\dots \cap I_{n}$$

> [!proof]-
> We will use induction over $n$. For $n=1$, it is trivial.
> 
> The inclusion $\subseteq$ trivially holds as $a_{1}\dots.a_{n}\in I_{1}\cap\dots \cap I_{n}$ for all $a_{i}\in I_{i}$. For the converse, let $J:= I_{1}\cap\dots \cap I_{n-1}$. We first claim that $I_{n}$ and $J$ are coprime. We have that: $$I_{n}+J \supseteq I_{n}+I_{1}=R$$Hence, $1\in I_{n}+J$ and there exists $a_{n}\in I_{n}$ and $b\in J$ s.t. $1=a_{n}+b$. It follows that for $x\in J\cap I_{n}$, we have that: $$x=xa_{n}+xb\in J\cdot I_{n}$$Finally, $I_{1}\dots I_{n}=J\cdot I_{n}=J\cap I_{n}=I_{1}\cap\dots \cap I_{n}$.

---
> [!lemma] Proposition 3
> Let $R$ be a commutative ring. Then, for two coprime ideals $\mathfrak{a,b}\subseteq R$:$$R / \mathfrak{ab}\cong R / \mathfrak{a}\times R / \mathfrak{b}$$ 

> [!proof]-
> We define the following isomorphism: $$\begin{array}{cccc} {\varphi:}&{R}&\to&{R / \mathfrak{a}\times R / \mathfrak{b}}\\&{x} &\mapsto & {(x+\mathfrak{a},x+\mathfrak{b})} \end{array}{}$$Then, $\varphi$ is of course a homomorphism. 