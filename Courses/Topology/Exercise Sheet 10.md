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
1. Firstly, one easily sees that $\mathbb{R}$ is open as $\bigcup_{n\geq 1}^{}(-n,n)$ and $\varnothing$ is open as an empty union. Then, it suffices to show that it is closed under finite intersection. It is clear that it is sufficient to show that every combination of intersection of two basis sets is open. We have:
	$$(a,b)\cap(c,d)=\begin{cases}(\max\{ a,c \},\min\{ b,d \})&\max\{ a,c \}<\min\{ b,d \}\\\varnothing&\text{otherwise}\end{cases}$$and as $(a,b)\backslash B=(a,b)\cap B^c$, $\mathcal{T}^{*}$ is indeed a topology. Further, as $\mathcal{B}_{1}$ is a basis for the euclidean topology, $\mathcal{T}^{*}$ is a refinement of the euclidean topology. This shows that $\mathbb{R}$ is Hausdorff w.r.t. $\mathcal{T}^{*}$.
2. For $U:=\bigcup_{n\geq 1}^{}(-n,0)\cup (0,n)$ is open. Therefore, $A=U^c$ is closed. Similarly, $$X \backslash B=\bigcup_{n\geq 1}^{}(-n,n) \backslash B$$which is open. 
3. As $U$ is an open neighborhood of $0$, there exists a basis set $W\subseteq \mathcal{B}$ s.t. $W\subseteq U$ and $0\in W$. If $W\in\mathcal{B}_{2}$, we are done. Otherwise, $W\in \mathcal{B}_{1}$ and as $0\notin W$, $0\in W \backslash B\subseteq U$. This proves the statement.
4. There exists an integer $n\geq 1$ s.t. $\frac{1}{b}<n$. As $b>0$, $\frac{1}{n}<b$ and $\frac{1}{n}\in (a,b)$.
5. 
