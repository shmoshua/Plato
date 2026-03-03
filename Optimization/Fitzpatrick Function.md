#Definition #Optimization 

> [!definition]
> Let $A:X\to 2^{X^{*}}$. The ***$n$-th order Fitzpatrick function*** of $A$ is given as: $$\begin{array}{rccl}F_{A,n}:&X\times X^{*}&\to &\mathbb{R} \cup \{ \infty \},\\&\quad (x,x^{*})&\mapsto&\sup_{\{ (a_{i},a_{i}^{*}) \}_{i\in[n-1]}\subseteq \text{graph}(A)}\braket{ x-a_{n-1} , a_{n-1}^{*} } + \sum_{i=1}^{n-2} \braket{ a_{i+1}-a_{i} , a_{i}^{*} } +\braket{ a_{1},  x^{*}}\end{array}$$

- **Remark**: For $n=2$, $F_{A,2}(x,x^{*})=\sup_{{(a,a^{*})}\in \text{gra }A}\braket{ x,a^{*} }+\braket{ a , x^{*} }-\braket{ a , a^{*} }$
---
##### Properties
> [!lemma] Proposition 1 
> Let $A:X\to 2^X$. Then, TFAE:
> 1. $A$ is $n$-cyclically monotone.
> 2. $F_{A,n}\leq \braket{ \cdot , \cdot }$ on $\text{graph}(A)$.
> 3. $F_{A,n}= \braket{ \cdot , \cdot }$ on $\text{graph}(A)$.

---
##### Examples
> [!h] Example 1
> Let $X$ be a real Hilbert space and $C\subseteq X$ is a non-empty, closed, convex set. For $f:= \iota _C$:
> 1. $F_{\partial f,2}(x,x^{*})=$

> [!proof]+
> We have that: 
> $$\partial f(x)=\begin{cases}\{ v\in X:\braket{ v , z-x } ,\forall z\in C \}&x\in C\\\varnothing&x\notin C\end{cases}$$
---
> [!h] Example 1
> Let $X$ be a real Hilbert space. Then, 
> 2. $F_{\|\cdot\|,2}(x,x^{*})=$