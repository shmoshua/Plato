#Definition #Topology 

> [!definition]
> Let $X\subseteq \mathbb{A}_{K}^n$ be a [[variety]]. Then, 
> 1. ***Zariski topology*** on $X$ is given by $C\subseteq X$ is closed if and only if $C=V(I)$ for some ideal $I\unlhd A(X)$ where $A(X)$ is the [[Polynomial Function|ring of polynomial functions]].

^7f255b

 - **Remark**: Zariski topology is not Hausdorff: on $\mathbb{A}_{K}^1$, Zariski topology coincides with the [[Topological Space|cofinite topology]]. ^23c06e
---
##### Properties
> [!lemma] Proposition 1
> Let $n\geq 1$ be an integer. If $U\subseteq \mathbb{C}^n$ is any non-empty open set for the Zariski topology, then $U$ is dense for the Zariski topology. 

^da17d5

> [!proof]-
> Assume that $\overline{U}\neq \mathbb{C}^n$.
> 1. **Claim 1: there exist closed sets $A_{1}\neq \mathbb{C}^n$ and $A_{2}\neq \mathbb{C}^n$ s.t. such that $A_{1}\cup A_{2}=\mathbb{C}^n$.**
>    As $\overline{U}\neq \mathbb{C}^n$, we have $A_{1}=\overline{U}$ and $A_{2}= \mathbb{C}^n \backslash U$ are closed sets and $$A_{1}\cup A_{2}=\overline{U}\cup (\mathbb{C}^n \backslash U)=\mathbb{C}^n$$
>  
>  Let $I_{i}:=\{ f\in\mathbb{C}[X_{1},\dots,X_{n}]:f(x)=0,\quad \forall x\in A_{i} \}$  for $i\in \{ 1,2 \}$. 
>  1. **Claim 2: $I_{1}\cap I_{2}=\{ 0 \}$:** 
>      Assume we have $f\in I_{1}\cap I_{2}$ where $f\not\equiv 0$. Then, $f(x)=0$ for all $x\in A_{1}\cup A_{2}=\mathbb{C}^n$, which is a contradiction.
> 
> Assume that there exists non-zero $f,g\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $f\in I_{1}$ and $g\in I_{2}$. Then, $fg$ is non-zero and $f(x)g(x)=0$ for all $x\in A_{1}\cup A_{2}$. Therefore, $fg\in I_{1}\cap I_{2}$, which is a contradiction. Therefore, $I_{1}=\{ 0 \}$ or $I_{2}=\{ 0 \}$.
> 
> However, as $U$ is not dense, there exists non-zero $f\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $$\overline{U}\subseteq \{ x\in \mathbb{C}^n:f(x)=0 \}$$i.e. $f\in I_{1}$, which implies that $I_{2}=\{ 0 \}$. Then, $\mathbb{C}^n \backslash U$ is dense and $\mathbb{C}^n \backslash U = \mathbb{C}^n$, which implies that $U=\varnothing$. This is a contradiction.

---
##### Examples
> [!h] Example 1
> Let $n\geq 0$ be an integer. A subset $A\subseteq \mathbb{C}^n$ is called ***algebraic*** if there exists a set $I$ and a family $(f_{i})_{i\in I}\subseteq\mathbb{C}[X_{1},\dots,X_{n}]$ of polynomials s.t. $$A=\{ x\in \mathbb{C}^n:f_{i}(x)=0,\quad \forall i\in I \}$$ 
> 1. The Zariski topology $\mathcal{T}_{Z}$ on $\mathbb{C}^n$ given by: $A\subseteq \mathbb{C}^n$ is closed if and only if $A$ is algebraic is a topology.
> 2. For $n=1$, the Zariski topology on $\mathbb{C}$ is identical with the [[Topological Space|cofinite topology]] $\mathcal{T}_{\text{cof}}$.
> 3. Let $m\geq 0$ be an integer and $f:\mathbb{C}^n\to \mathbb{C}^m$ be a polynomial map. Then, $f$ is continuous for $\mathcal{T}_{Z}.$
> 4. For $n\geq 1$, the Zariski topology on $\mathbb{C}^n$ is not Hausdorff.
> 5. $A\subseteq \mathbb{C}^n$ is dense for the Zariski topology unless there exists $f\in \mathbb{C}[X_{1},..,X_{n}]$, $f\neq 0$, s.t. $A\subseteq \{ x\in \mathbb{C}^n:f(x)=0 \}$
> 6. $\mathbb{Z}^n$ is dense in $\mathbb{C}^n$ for the Zariski topology.

> [!proof]-
> We have:
> 1. Firstly, for $f\equiv{1}$, $\varnothing=\{ x\in \mathbb{C}^n:f(x)=0 \}$. For $f\equiv 0$, $\mathbb{C}^n=\{ x\in \mathbb{C}^n:f(x)=0 \}$. Therefore, $\varnothing,X$ are algebraic, closed and thereby open.
>    
>    Let $A_{1},A_{2}$ be two algebraic sets with $(f_{i})_{i\in I},(g_{j})_{j\in J}$ as the associated sets respectively. Then, consider $\{ f_{i}g_{j}: i\in I,j\in J \}$. We claim that: $$A_{1}\cup A_{2}=\{ x\in \mathbb{C}^n:f_{i}(x)g_{j}(x)=0,\quad \forall i\in I,j\in J \}$$Let $x\in A_{1}\cup A_{2}$. Then, wlog assume that $x\in A_{1}$. Indeed, $f_{i}(x)g_{j}(x)=0$ for all $i\in I$ and $j\in J$ as $f_{i}(x)=0$ for all $i\in I$. Conversely, if $x\notin A_{1}\cup A_{2}$, then $x\notin A_{1}$ and $x\notin A_{2}$. Therefore, there exists $f_{i}$ and $g_{j}$ s.t. $f_{i}(x)g_{j}(x)\neq 0$. This proves the claim, i.e. $A_{1}\cup A_{2}$ is algebraic.
>    
>    Let $(A_{n})_{n}$ be an arbitrary family of algebraic sets with $(f_{n,i})_{i\in I_{n}}$ as the associated polynomials. Then, $$\bigcap_{n=1}^{\infty}A_{n}=\{ x\in \mathbb{C}^n:f_{n,i}(x)=0,\quad \forall n\geq 1,i\in I_{n} \}$$Therefore, any arbitrary intersection is also algebraic. This shows the statement.
> 2. We have from above that $\mathbb{C}$ is algebraic. Now, for any $x_{0}\in \mathbb{C}$, let $f(x)=x-x_{0}$ and $$\{ x_{0} \}=\{ x\in \mathbb{C}^n:f(x)=0 \}$$Therefore, $\{ x_{0} \}$ is closed w.r.t the Zariski topology and thereby any finite set. If $A\subseteq \mathbb{C}^n$ is infinite with $A\neq \mathbb{C}$, then there exists a non-zero $f\in \mathbb{C}[X]$ with infinitely many roots which is a contradiction. Therefore, no non-$\mathbb{C}$ infinite set is algebraic.
> 3. Let $A\subseteq \mathbb{C}^m$ be algebraic with $(g_{i})_{i\in I}$ as its associated polynomials. Then, $(g_{i}\circ f)_{i\in I}$ is a set of polynomials and: $$f^{-1}(A)=\{ x\in \mathbb{C}^n:(g_{i}\circ f)(x)=0,\quad\forall i\in I \}$$If for $x\in \mathbb{C}^n$ $(g_{i}\circ f)(x)=0$ for all $i\in I$, $f(x)\in A$. Similarly, if $x\in f^{-1}(A)$, then $g_{i}(f(x))=0$ for all $i\in I$. Therefore, $f$ is continuous.
> 4. From Proposition 1. 
> 5. Assume that $A$ is not dense. Then, there exists $x\in \mathbb{C}^n$ and an open neighborhood $U$ of $x$ s.t. $U\cap A=\varnothing$. In other words, $A\subseteq X \backslash U=:F$ which is algebraic, i.e. there exists $(f_{i})_{i\in I}$ s.t. $$A\subseteq\{  y\in \mathbb{C}^n:f_{i}(y)=0,\quad \forall i\in I\}$$Notice that if $f_{i}=0$ for all $i\in I$, then $f_{i}(x)=0$ for all $i\in I$ and $x\in F$, which is a contradiction. 
>    
>    On the other hand, if such function $f$ exists, then $\{ x\in \mathbb{C}^n:f(x)=0 \}\subsetneq\mathbb{C}^n$ is a closed set and $\overline{A}\subsetneq \mathbb{C}^n$.
> 6. It is clear that there exists no non-zero polynomial $f\in \mathbb{C}[X]$ s.t. $f(z)=0$ for every $z\in \mathbb{Z}$. Therefore, by 5, $\mathbb{Z}$ is dense in $\mathbb{C}$. Now assume $n\geq 2$ and $\mathbb{Z}^{n-1}$ is dense in $\mathbb{C}^{n-1}$. If $\mathbb{Z}^{n}$ is not dense in $\mathbb{C}^n$, there exists $f\in \mathbb{C}[X_{1},\dots,X_{n}]$ s.t. $f(x)=0$ for all $x\in \mathbb{Z}^n$. Now, we write: $$f(x)=f_{m}(x_{1:n-1})x_{n}^{m}+\dots+f_{1}(x_{1:n-1})x_{n}+f_{0}(x_{1:n-1})$$ where $f_{i}\in \mathbb{C}[X_{1},\dots,X_{n-1}]$. Then, consider $x\in \mathbb{Z}^{n-1}\times \{ 0 \}$. We have that: $$f(x)=f_{0}(x_{1:n-1})=0$$ Therefore, there exists a function $f_{0}\in \mathbb{C}[X_{1},\dots,X_{n-1}]$ s.t. for all $z\in \mathbb{Z}^{n-1}$, $f_{0}(z)=0$, i.e. $\mathbb{Z}^{n-1}$ is not dense in $\mathbb{C}^{n-1}$, a contradiction.
---
