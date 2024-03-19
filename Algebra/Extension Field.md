#Definition #Algebra 

> [!definition]
> Let $K$ be a [[field]] and $F\subseteq K$ a subfield. Then, $K$ is called an ***extension*** of $F$ denotes as $K:F$ or $K / F$.
- **Related definition**: For $K:F$ and $A\subseteq K$, we have:
	1. $F[A]:=$ intersection of all subrings of $K$ that contain $F,A$.
	2. $F(A):=$ intersection of all subfields of $K$ that contain $F,A$.
- **Related definition**: An extension $K:F$ is ***simple*** if there exists $a\in K$ s.t. $K=F(a)$. Then, $a$ is called the ***primitive element***.
- **Related definition**: If $L:K$ and $K:F$, then $K$ is the ***intermediate field*** of $L:F$.
- **Related definition**: The ***degree*** of extension $K:F$ is denoted as $[K:F]:=\text{dim}_{F} K$ as a $F$-vector space. (cf. Lemma 1)
---
##### Properties
> [!lemma] Lemma 1
> For a field extension $K:F$, $K$ is a [[Vector Space|$F$-vector space]].

> [!proof]-
> We have $(K,+,0)$ as an abelian group. Further, $$\begin{array}{cccc} &{F\times K}&\to&{K}\\&{(\lambda,x)} &\mapsto & {\lambda x} \end{array}{}$$defines the scalar multiplication.
---
> [!lemma] Theorem 2 (Dimension behaves multiplicatively)
> If $K$ is an intermediate field of a field extension $L:F$, then: $$[L:F]=[L:K][K:F]$$

> [!proof]+
> We have: 
> 1. **Case 1: $[K:F]=\infty$**:
>    Then, there are infinitely many linearly independent vectors in $K$ and thereby in $L$. Therefore, the dimension of $[L:F]$ is also infinite.
> 2. **Case 2: $[L:K]=\infty$**:
>    Then, there are infinitely many vectors linearly independent over $K$ and thereby over $F$. 
> 3. **Case 3: $[L:K],[K:F]<+\infty$**:
>    Let $\{ x_{1},\dots,x_{n} \}$ be the basis of $K / F$ and $\{ y_{1},\dots,y_{m} \}$ be a basis of $L / K$. Then, we show that: $$\{ x_{i}y_{j}: i\in [n],j\in [m] \}$$is a basis of $L / F$.
>    - **Showing that they are generating**:
> 	  Let $y\in L$. Then, $y=\sum_{j=1}^{m}b_{j}y_{j}$ with $b_{j}\in K$. Therefore, for all $j\in [m]$, $b_{j}=\sum_{i=1}^{n}a_{ij}x_{i}$ with $a_{ij}\in F$. It follows that: $$y=\sum_{i=1}^{n}\sum_{j}^{}$$
>    - **Showing that they are linearly independent**:
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{R}:\mathbb{Q}$
> 2. $\mathbb{C}:\mathbb{R}$
> 3. $\mathbb{C}:\mathbb{Q}$ with $\mathbb{R}$ as intermediate field.
---
