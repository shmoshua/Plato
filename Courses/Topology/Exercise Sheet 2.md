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
> 2. Give a geometric description of the sets: $$B^\delta_{<r}(x_{0}):=\{ y\in \mathbb{R}^{2}:\delta(x,y)<r \}$$
> 3. Show that $\mathcal{T}_{d}\subseteq \mathcal{T}_{\delta}$.
> 4. Show that $\mathcal{T}_{\delta}\not\subseteq \mathcal{T}_{d}$.
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
