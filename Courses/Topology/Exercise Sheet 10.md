#Series #Topology 

> [!def] Problem 1
> Let $B:=\{ 1 / n:n\geq 1 \}\subseteq \mathbb{R}$. Define a topology $\mathcal{T^{*}}$ on $\mathbb{R}$ with basis $\mathcal{B}:=\mathcal{B}_{1}\cup \mathcal{B}_{2}$, where $$\mathcal{B}_{1}:=\{ (a,b):a<b,a,b\in \mathbb{R} \}$$$$\mathcal{B}_{2}:=\{ (a,b) \backslash B:a<b,a,b\in \mathbb{R} \}$$i.e., a set $U\subseteq \mathbb{R}$ is open for $\mathcal{T^{*}}$ if and only if it is an arbitrary union of sets in $\mathcal{B}$.
> 1. Show that $\mathcal{T}^{*}$ is indeed a topology, and that $\mathbb{R}$ is Hausdorff with this topology.
> 2. Let $A=\{ 0 \}$. Show that the sets $A$ and $B$ are closed in $(\mathbb{R},\mathcal{T}^{*})$.
> 
> We now suppose that $U,V$ are open sets with $0\in U$, $B\subseteq V$ and that $U\cap V=\varnothing$.
> 1. Show that there exist $a<b$ such that $a<0<b$ and $(a,b)\backslash B \subseteq U$.
> 2. Show that there exists an integer $n\geq 1$ such that $1/n\in (a,b)$.
> 3. Show that $1 / n\in V$ and that there exist $c < 1 / n < d$ such that $(c,d)\subseteq V$.
> 4. Show that there exists $x\in \mathbb{R}$ such that: $$\frac{1}{n+1}<x< \frac{1}{n}, \quad x>c$$
> 5. Show that $x\in U\cap V$.
> 6. Conclude that $(\mathbb{R},\mathcal{T^{*}})$ is not normal.

We have that: 
1. Firstly, one easily sees that $\mathbb{R}$ is open. 