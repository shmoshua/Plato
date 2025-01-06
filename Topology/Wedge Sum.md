#Definition #Topology 

> [!definition]
> Let $(X_{i})_{i\in I}$ be an indexed family of [[Topological Space|topological spaces]]. Let $x_{i}\in X_{i}$ for all $i\in I$. 
> 1. The ***wedge sum*** of $(X_{i})_{i\in I}$ is given by: $$\bigvee_{i\in I}^{} X_{i}:=\bigsqcup_{i\in I}^{}X_{i} /_{\sim}$$where $\sim$ is the equivalence relation s.t. $x_{i}\sim x_{j}$ for all $i,j\in I$

^56869a

- **Related definition**: For $i\in I$,  ^6c44a6
	1. the ***inclusion*** $i_{i}:X_{i}\to \bigvee_{i\in I}X_{i}$.
	2. the **projection** $p_{i}:\bigvee_{i\in I}X_{i}\to X_{i}$ s.t. for every $x\notin X_{i}$, $p(x)=x_{i}$ and $p_{i}|_{X_{i}}=\text{id}|_{X_{i}}$. 
---
##### Properties
> [!lemma] Theorem 1
> Let $(X,x_{0})$ and $(Y,y_{0})$ be pointed spaces. Then, 
> 1. $X\lor Y\cong X\times \{ y_{0} \}\cup \{ x_{0} \}\times Y\subseteq X\times Y$

> [!proof]+
> Let $X\times \{ y_{0} \}\cup \{ x_{0} \}\times Y=:Z$. Then, we have that: $$\psi:Z \to X\lor Y,\quad (x,y)\mapsto \begin{cases}q(x)&y=y_{0}\\q(y)&x=x_{0}\end{cases}$$where $q:X \sqcup Y \to X \lor Y$ be the quotient map. Then, it is continuous as $q$ is continuous and $\psi(x_{0},y_{0})=q(x_{0})=q(y_{0})$ which is well-defined. Similarly, let $$\psi ^{-1}:X \lor Y\to Z,\quad [z]\mapsto \begin{cases}(x,y_{0})&z\in X\\(x_{0},y)&z\in Y\end{cases}$$

---
##### Examples
> [!h] Example 1 (Bouquet of Spheres)
> Let $S_{1}^\mathbf{n}\dots,S^n_{k}$ be spheres. Then, 
> 1. $X:=S_{1}^n\vee \dots \lor S^n_{k}$ is called a ***bouquet of $k$ spheres***.

^789a47

---
