#Definition #Topology 

> [!definition]
> Let $(X_{i})_{i\in I}$ be an indexed family of [[Topological Space|topological spaces]]. Let $x_{i}\in X_{i}$ for all $i\in I$. 
> 1. The ***wedge sum*** of $(X_{i})_{i\in I}$ is given by: $$\bigvee_{i\in I}^{} X_{i}:=\bigsqcup_{i\in I}^{}X_{i} /_{\sim}$$where $\sim$ is the equivalence relation s.t. $x_{i}\sim x_{j}$ for all $i,j\in I$

^56869a

- **Related definition**: For $i\in I$,  ^6c44a6
	1. the ***inclusion*** $i_{i}:X_{i}\to \bigvee_{i\in I}X_{i}$.
	2. the **projection** $p_{i}:\bigvee_{i\in I}X_{i}\to X_{i}$ s.t. for every $x\notin X_{i}$, $p(x)=x_{i}$ and $p_{i}|_{X_{i}}=\text{id}|_{X_{i}}$. 
- **Related definition**: For $f:(X,x_{0})\to(X',x_{0}')$ and $g:(Y,y_{0})\to(Y',y_{0}')$, the map: $$f \lor g:(X\lor Y,*)\to(X'\lor Y',*),\quad [z]=\begin{cases}{[f(z)]}&z\in X\\{[g(z)]}&z\in Y\end{cases}$$
---
##### Properties
> [!lemma] Theorem 1
> Let $(X,x_{0})$ and $(Y,y_{0})$ be pointed spaces. Then, 
> 1. $X\lor Y\cong X\times \{ y_{0} \}\cup \{ x_{0} \}\times Y\subseteq X\times Y$

> [!proof]-
> Let $X\times \{ y_{0} \}\cup \{ x_{0} \}\times Y=:Z$. Then, we have that: $$\psi:Z \to X\lor Y,\quad (x,y)\mapsto \begin{cases}q(x)&y=y_{0}\\q(y)&x=x_{0}\end{cases}$$where $q:X \sqcup Y \to X \lor Y$ be the quotient map. Then, it is continuous as $q$ is continuous and $\psi(x_{0},y_{0})=q(x_{0})=q(y_{0})$ which is well-defined. Similarly, let $$\psi ^{-1}:X \lor Y\to Z,\quad [z]\mapsto \begin{cases}(x,y_{0})&z\in X\\(x_{0},y)&z\in Y\end{cases}$$then $\psi ^{-1} \circ q:X\sqcup Y\to Z$ is continuous $\psi ^{-1}\circ q|_{X}(x)\mapsto(x,y_{0})$ as and similarly for $Y$. Hence, this is a homeomorphism.

---
> [!lemma] Proposition 2
> Let $(X,x_{0})$ and $(Y,y_{0})$ be pointed spaces and $N\subseteq X$ a closed neighborhood of $x_{0}$ s.t. $\{ x_{0} \}$ is a strong deformation retract of $N$.
> 1. $\tilde{H}_{p}(X)\oplus \tilde{H}_{p}(Y)\cong H_{p}(X\lor Y)$ given by the inclusions and projections.

> [!proof]+
> Let $i^X:(X,\varnothing)\to(X \lor Y,\varnothing)$ and $i^Y:(Y,\varnothing)\to(X\lor Y,\varnothing)$ be inclusions. Further, let $k:(X\lor Y,\varnothing)\to(X\lor Y,X)$ also be an inclusion. Then, $$\dots\to H_{p+1}(X\lor Y,X)\xrightarrow{\partial_{*}} \tilde{H}_{p}(X)\xrightarrow{ i_{*}^X}\tilde{H}_{p}(X\lor Y)\xrightarrow{k_{*}} H_{p}(X \lor Y,X)\to \tilde{H}_{p-1}(X)\to \dots$$However, notice that: $$\tilde{H}_{p}(Y)\cong H_{p}(Y,y_{0})\cong H_{p}(N\cup Y,N)\cong H_{p}(X \lor Y,X)$$which is induced by the inclusion $j:(Y,\varnothing)\to(X\lor Y,X)$. Further, note that $j=k \circ i^Y$ and  as $j_{*}$ is an isomorphism, $k_{*} \circ i^Y_{*}\circ (j_{*})^{-1}=\text{id}$ and $k_{*}$ is surjective. Therefore, 
---
##### Examples
> [!h] Example 1 (Bouquet of Spheres)
> Let $S_{1}^\mathbf{n}\dots,S^n_{k}$ be spheres. Then, 
> 1. $X:=S_{1}^n\vee \dots \lor S^n_{k}$ is called a ***bouquet of $k$ spheres***.

^789a47

---
