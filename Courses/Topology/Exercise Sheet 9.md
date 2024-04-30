#Series #Topology 

> [!def] Problem 1
> For $z\in \mathbb{C}$ and $r\geq 0$, we denote: $$C(z,r)=\{ w\in \mathbb{C}:\left| w-z \right| =r \}$$Let $X=[0,2]\subseteq \mathbb{R}$ and $Y=C(i,1)\cup C(-i,1)$. 
> 1. Show that the map $\varphi:X\to Y$ s.t. $$\varphi(t):=\begin{cases}i+\exp\left( 2i\pi\left( t-\frac{1}{4} \right) \right)&0\leq t\leq 1\\-i+\exp\left( 2i\pi\left( t-\frac{3}{4} \right) \right)&1\leq t\leq 2\end{cases}$$ is well-defined, and that it is continuous. 
> 2. Define an equivalence relation on $X$ with equivalence classes $\{ 0,1,2 \}$ and $\{ t \}$ for $t\in X \backslash \{ 0,1,2 \}$. Let $X':=X / \sim$ and $p:X\to X'$ the projection. Show that there is a continuous map $\tilde{\varphi}:X'\to Y$ s.t. $\tilde{\varphi}\circ p=\varphi$, and that $\tilde{\varphi}$ is continuous when $X'$ has the quotient topology.
> 3. Show that $\tilde{\varphi}$ is a homeomorphism.

We have:
1. For any $0\leq t\leq 1$, $\varphi(t)$