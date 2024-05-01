#Series #Topology 

> [!def] Problem 1
> For $z\in \mathbb{C}$ and $r\geq 0$, we denote: $$C(z,r)=\{ w\in \mathbb{C}:\left| w-z \right| =r \}$$Let $X=[0,2]\subseteq \mathbb{R}$ and $Y=C(i,1)\cup C(-i,1)$. 
> 1. Show that the map $\varphi:X\to Y$ s.t. $$\varphi(t):=\begin{cases}i+\exp\left( 2i\pi\left( t-\frac{1}{4} \right) \right)&0\leq t\leq 1\\-i+\exp\left( 2i\pi\left( t-\frac{3}{4} \right) \right)&1\leq t\leq 2\end{cases}$$ is well-defined, and that it is continuous. 
> 2. Define an equivalence relation on $X$ with equivalence classes $\{ 0,1,2 \}$ and $\{ t \}$ for $t\in X \backslash \{ 0,1,2 \}$. Let $X':=X / \sim$ and $p:X\to X'$ the projection. Show that there is a continuous map $\tilde{\varphi}:X'\to Y$ s.t. $\tilde{\varphi}\circ p=\varphi$, and that $\tilde{\varphi}$ is continuous when $X'$ has the quotient topology.
> 3. Show that $\tilde{\varphi}$ is a homeomorphism.

We have:
1. For any $0\leq t\leq 1$, $\left| i-\varphi(t) \right|=1$ and $\varphi(t)\in C(i,1)$. Similarly, for $1\leq t\leq 2$, $\left| -i-\varphi(t) \right|=1$ and $\varphi(t)\in C(-i,1)$. Further, for $t=1$, $$i+\exp\left( \frac{3}{2}\pi i \right)=0=-i+\exp\left( \frac{1}{2}\pi i \right)$$Therefore, $\varphi$ is well-defined. The continuity follows from the continuity of $\exp$. 
2. Let $\tilde{\varphi}:X'\to Y$ be defined as: $$\tilde{\varphi}(S)=\begin{cases}0&S=\{ 0,1,2 \}\\i+\exp\left( 2i\pi\left( t-\frac{1}{4} \right) \right)&S=\{ t \},0< t< 1\\-i+\exp\left( 2i\pi\left( t-\frac{3}{4} \right) \right)&S=\{ t \},1< t< 2\end{cases}$$Then, $\tilde{\varphi}\circ p = \varphi$ and $\tilde{\varphi}$ is continuous as $\varphi$ is.
3. One easily sees using analysis that $\tilde{\varphi}$ is bijective. As $X=[0,2]$ is compact and $Y$ is Hausdorff, $\tilde{\varphi}$ is a homeomorphism.
---
> [!def] Problem 2
> Let $X$ and $Y$ be topological spaces with equivalence relations $\sim_{X}$ and $\sim_{Y}$ on $X$ and $Y$ respectively. Let $Z=X\times Y$ with the product topology. On $Z$, let $\sim$ be the equivalence relation defined by $$(x_{1},y_{1})\sim(x_{2},y_{2})\iff x_{1}\sim_{X}x_{2}\land y_{1}\sim_{Y}y_{2}$$
> Let $X':=X /{\sim_{X}}$, $Y':=Y /\sim_{Y}$, $Z:= Z /\sim$  denote the respective quotients. Each is given the quotient topology. Let finally $p_{X}$, $p_{Y}$ and $p$ denote the projections. 
> 1. Show that there is a bijection $\phi:Z'\to X'\times Y'$ s.t. the class of $(x,y)$ is mapped to $(p_{X}(x),p_{Y}(y))$, and that $\phi$ is continuous when $X'\times Y'$ has the product topology. 
> 2. Suppose that $p_{X}$ and $p_{Y}$ are open maps. Show that $\phi(p(W))$ is open in $X'\times Y'$ for all $W\subseteq Z$ open. 
> 3. Deduce that $\phi$ is an homeomorphism in that case.

We have: 
1. We claim that $\phi$ is well-defined. Let $(x_{1},y_{1})\sim(x_{2},y_{2})$. Then, $x_{1}\sim x_{2}$ and $p_{X}(x_{1})=p_{X}(x_{2})$. Therefore, it holds that $(x_{1},y_{1})\sim(x_{2},y_{2})$ if and only if $(p_{X}(x_{1}),p_{Y}(y_{1}))=(p_{X}(x_{2}),p_{Y}(y_{2}))$ by symmetry and this shows the well-definedness and injectivity. For $(S,T)\in X'\times Y'$, there exists $x\in X,y\in Y$ s.t. $p_{X}(x)=S$ and $p_{Y}(y)=T$ by surjectivity of projection. Therefore, $\phi(p(x,y))=(p_{X}(x),p_{Y}(y))$. This shows that $\phi$ is bijective. 
   
   To show that $\phi$ is continuous, for a product space $V\times W$, let $\pi_{V}$ denote the projection onto $V$. Then, we notice that $\pi_{X'}\circ\phi \circ p=p_{X}\circ \pi_{X}$, which is continuous. By symmetry, it holds that $\phi$ is continuous.
2. 
---
> [!def] Problem 3
> Let $X$ be a topological space and $\sim$ an equivalence relation on $X$. Let $X':= X / \sim$ and $p:X\to X'$ the projection. Let $\Gamma:=\{ (x,y)\in X\times X:x \sim y \}$ be the graph of the equivalence relation. Define the relation $\equiv$ on $X\times X$ by $(x,y)\equiv(x',y')$ if and only if $x\sim x'$ and $y\sim y'$. 
> 1. Show that $\Gamma=q^{-1}(q(\Delta))$ where $$\Delta=\{ (x,x)\in X\times X: x\in X \}$$is the diagonal in $X\times X$ and $q:X\times X\to X\times X / \equiv$ is the projection.
> 2. If the map $p$ is open and $\Gamma$ is closed in $X\times X$, show that the diagonal $$\Delta':=\{ (x,x)\in X'\times X': x\in X' \}$$ is closed in X′ × X′ for the product topology. (Hint: use the previous exercise.) (c) Deduce that the space X′ is then Hausdorff. (Hint: use Exercise 3 of Exercise sheet 4).