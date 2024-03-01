 #Series #Topology 

> [!definition] Problem 1
> Let $X$ be a set.
> 1. Let $d_{1}$ and $d_{2}$ be distances on $X$. If there exist $a,b>0$ s.t.$$d_{1}(x,y)\leq d_{2}(x,y)^a,\quad d_{2}(x,y)\leq d_{1}(x,y)^b,\quad \forall(x,y)\in X\times X$$ show that the topologies defined by $d_{1}$ and $d_{2}$ are the same.
> 2. Let $d$ be a distance on $X$. Show that: $$\delta(x,y)= \frac{d(x,y)}{1+d(x,y)}$$is a distance on $X$. Show that the topology defined by $\delta$ is the same as the topology defined by $d$. Show that $\delta(x,y)\leq 1$ for all $(x,y)\in X\times X$. 

We have:
1. Let $U\subseteq \mathcal{T}_{d_{1}}$. Then, for any $x\in X$, there exists $r>0$ s.t. $B^1_{<r}(x)\subseteq U$. Consider $B^2_{<r^{1/a}}(x)$. We have:$$B^2_{<r^{1 /a}}(x)=\{ y\in X:d_{2}(x,y)<r^{1/a} \}\subseteq \{ y\in X:d_{1}(x,y)<r \}=B^1_{<r}(x)\subseteq U$$Therefore, $U\subseteq \mathcal{T}_{d_{2}}$. The opposite inclusion holds by symmetry.
2. We have: 
	- **Showing $\delta$ is a distance**: The non-negativity, non-degeneracy and symmetry are clear from the definition. For triangle inequality, notice that for $a,b,c\geq 0$ s.t. $a\leq b+c$, we have: $$\frac{a}{1+a}\leq \frac{b+c}{1+b+c}=\frac{b}{1+b+c}+ \frac{c}{1+b+c}\leq \frac{b}{1+b}+\frac{c}{1+c}$$This shows the triangle inequality.
	- **Showing $\delta$ and $d$ define the same topology**: For any $x\in X$ and $r>0$, as $\delta(x,y)\leq d(x,y)$ (from the non-negativity of $d(x,y)$), $B_{<r}^d(x)\subseteq B_{<r}^\delta(x)$. On the other hand, $d(x,y)= \delta(x,y)/(1-\delta(x,y))$ and $B_{< \frac{r}{1-r}}^\delta(x)\subseteq B^\delta_{<r}(x)$. This shows that the topologies coincide.  
	- **Showing that $\delta(x,y)\leq 1$**: Indeed, $d(x,y)\leq 1+d(x,y)$ for all $x,y\in X\times X$.
---
> [!definition] Problem 2
> Let $X=\mathbb{R}^2$. Let $d$ denote the euclidean distance on $X$. Define for $(x,y)\in X\times X$, $$\delta(x,y)=\begin{cases}d(x,y)&\exists\lambda\in \mathbb{R}: y=\lambda x\\d(x,0)+d(0,y)&\text{otherwise}\end{cases}$$
> 1. Show that $\delta$ is a distance on $\mathbb{R}^{2}$.
> 2. Give a geometric description of the sets: $$B^\delta_{<r}(x):=\{ y\in \mathbb{R}^{2}:\delta(x,y)<r \}$$
> 3. Show that $\mathcal{T}_{d}\subseteq \mathcal{T}_{\delta}$.
> 4. Show that $\mathcal{T}_{\delta}\not\subseteq \mathcal{T}_{d}$.

We have:
1. The symmetry and non-negativity are clear from the definition. For non-degeneracy, if $x=y$, then $\delta(x,y)=d(x,y)=0$. If $\delta(x,y)=0$, then $d(x,y)=0$ and $x=y$ or $d(x,0)+d(0,y)=0$ with $x$ not proportional to $y$, which cannot happen. Lastly, for triangle inequality, let $x,y,z\in \mathbb{R}^{2}$. Firstly, by triangle inequality of $d$, notice that $d(x,y)\leq\delta(x,y)$. If $x$ and $z$ are proportional, $$\delta(x,z)=d(x,z)\leq d(x,y)+d(y,z)=\delta(x,y)+\delta(y,z)$$If $x$ and $z$ are not proportional, by transitivity of proportionality, $y$ is not proportional to at least one of $x,z$. Wlog assume $y$ is not proportional to $x$. Then, $$\delta(x,z)=d(x,0)+d(0,z)\leq d(x,0)+d(0,y)+d(y,z)\leq\delta(x,y)+\delta(y,z)$$This proves the statement.
2. For $y,z\in \mathbb{R}^{2}$, let $[y:z]$ define the line that goes through $y$ and $z$. Then, geometrically we can consider the ball as follows: $$B_{<r}^\delta(x)=([0:x]\cap B_{<r}^d(x))\cup (B_{<r-d(x,0)}(0)\backslash [0:x])$$ where $B_{<\varepsilon}(0)=\varnothing$ for $\varepsilon\leq 0$. In other words, the open balls are a union of a line segment of length $2r$ that goes centered at $x$ and an open ball at $0$ with radius $r-d(x,0)$ minus the line that goes through the origin and $x$, if $r-d(x,0)$ is positive.
3. Let $U\in \mathcal{T}_{d}$. Then, for $x\in U$, there exists $r>0$ s.t. $B^d_{<r}(x)\subseteq U$. 
   If $x=0$, then, $B^\delta_{r}(x)=B^d_{r}(x)\subseteq U$. Otherwise, let $\varepsilon:=\min\{ r,d(x,0)\}>0$. Then, $$B_{<\varepsilon}^\delta(x)=[0:x]\cap B_{<\varepsilon}^d(x)\subseteq B_{<r}^d(x)\subseteq U$$
4. Consider $B^\delta_{1}((2,0))$, which is equal to a line segment between $(1,0)$ and $(3,0)$. This is clearly not open in the Euclidean space.
---
> [!definition] Problem 3
> Let $X$ be a set. 
> 1. Show that a topology $\mathcal{T}$ on $X$ is the discrete topology if and only if, for all $x\in X$, $\{ x \}\in \mathcal{T}$.
> 2. Find a metric $d$ on $X$ such that the topology defined by $d$ is the discrete topology on $X$.

We have:
1. If $\mathcal{T}$ is discrete, by definition $\{ x \}$ is open for all $x\in X$. Conversely, if $\{ x \}\in \mathcal{T}$ for all $x\in X$, then for any $Y\subseteq X$, $Y=\bigcup_{x\in Y}^{}\{ x \}\in \mathcal{T}$ as a union of open sets. 
2. We define: $$d(x,y)=\begin{cases}0&x=y\\1&x\neq y\end{cases}$$We first show that $d$ is a metric. The non-negativity, non-degeneracy and symmetry are obvious by definition. For triangle inequality with $x,y,z\in X$, if $x=z$, then $d(x,z)=0$ and triangle inequality holds, if $x\neq z$, then $x\neq y$ or $y\neq z$, which proves the statement.
	
	Now, notice that $\{ x \}=B_{<1}(x)$ for every $x\in X$. Therefore, $\{ x \}$ is open and by 1, $\mathcal{T}_{d}$ is the discrete topology.
---
> [!definition] Problem 4
> Let $C$ be the [[Cantor space]] of sequences $(x_{n})_{n\geq 1}$ with $x_{n}\in \{ 0,1 \}$, with the topology defined in the lecture.
> 1. Show that the map: $$\begin{array}{cccc} {t:}&{C}&\to&{[0,1]}\\&{x} &\mapsto & {\sum_{n=1}^{\infty}\frac{2x_{n}}{3^n}} \end{array}{}$$is well-defined and that it is continuous and injective.
> 2. Show that the image of $t$ in closed in $[0,1]$. 
> 3. Show that the reciprocal map $t^{-1}:t(C)\to C$ is continuous.

We have:
1. Firstly, for any $x\in C$, $0\leq t(x)\leq \sum_{n=1}^{\infty} \frac{2}{3^n}=1$ as $0\leq x_{n}\leq 1$.  Therefore, $t(x)\in [0,1]$ as a convergent sum. 
	1. **Showing that $t$ is continuous**: Let $U\subseteq [0,1]$ open. Then, for $x\in t^{-1}(U)$, there exists $r>0$ s.t. $B_{<r}(t(x))\subseteq U$. Let $n_{0}\in \mathbb{N}$ s.t. $\sum_{n=1}^{n_{0}} \frac{2}{3^n}=$