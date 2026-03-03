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
> [!h] Example 1 (Indicator Function)
> Let $X$ be a real Hilbert space and $C\subseteq X$ is a non-empty, closed, convex set. For $f:= \iota _C$:
> 1. $F_{\partial f,2}(x,x^{*})=\iota_{C}(x)+\iota_{C}^{*}(x^{*})$.

> [!proof]-
> We have that: 
> $$\partial f(x)=\begin{cases}\{ v\in X:\braket{ v , z-x } \leq 0,\forall z\in C \}&x\in C\\\varnothing&x\notin C\end{cases}$$Then, let $(y,y^{*})\in X\times X$.  We have that: $$\begin{aligned}F_{\partial f,2}(y,y^{*})&=\sup_{a\in C,a^{*}\in \partial f(a)}\braket{ y , a^{*} } +\braket{ a , y^{*} } -\braket{ a , a^{*} } \end{aligned}$$
> 1. If $y\in C$, then for any $a\in C$ and $a^{*}\in \partial f(a)$, we have $\braket{ y-a , a^{*} }\leq 0$. As $0\in \partial f(a)$, we have that $\sup_{a^{*}\in \partial f(a)}\braket{ y-a , a^{*} }=0$. Hence, $$F_{\partial f,2}(y,y^{*})=\sup_{a\in C}\braket{ a , y^{*} }=\iota_{C}(y)+\iota^*_{C}(y^{*}) $$
> 2. If $y\notin C$, then $y-P_{C}(y)\in \partial f(P_{C}(y))$ and as $\alpha(y-P_{C}(y))\in \partial f(P_{C}(y))$ for all $\alpha> 0$, we have that: $F_{\partial f,2}(y,y^{*})=+\infty$. This proves the statement.

---
> [!h] Example 1
> Let $X$ be a real Hilbert space. For $f:=\left\| \cdot \right\|$:
> 1. $F_{\partial f,2}(y,y^{*})=\begin{cases}\left\| y \right\|&\left\| y^{*} \right\|\leq 1\\\end{cases}$