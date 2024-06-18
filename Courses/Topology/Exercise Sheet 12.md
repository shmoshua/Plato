#Series #Topology 

> [!def] Problem 1
> Let $X\subseteq \mathbb{R}^{2}$ be the union of the circles $C_{n}$ with radius $\frac{1}{n}$ centered at $\left( \frac{1}{n},0 \right)$ for all $n\geq 1$. Each of them passes by the origin $(0,0)$, and we let $x_{0}:=(0,0)\in X$. The goal of this exercise is to prove that $\pi_{1}(X,x_{0})$ is an uncountable group (where $X$ has the subspace topology from $\mathbb{R}^{2}$)
> 1. Show that $X$ is path-connected.
> 2. Show that if $U$ is a neighborhood of $x_{0}$, then there exists $N$ s.t. $C_{n}\subseteq U$ for all $n\geq N$.
> 3. Let $n\geq 1$ be an integer. Show that the map $r_{n}:X\to C_{n}$ s.t. $$r_{n}(x)=\begin{cases}x&x\in C_{n}\\x_{0}&x\notin C_{n}\end{cases}$$is continuous.
> 4. Show that the induced map $r_{n*}:\pi_{1}(X,x_{0})\to \pi_{1}(C_{n},x_{0})$ is surjective. 
> 5. For $n\geq 1$, let $\gamma_{n}:[0,1]\to C_{n}$ be a loop at $x_{0}$ on $C_{n}$. Define $\gamma:[0,1]\to X$ by $$\gamma(t)=\gamma_{n}\left( n(n+1)\left( t-1+\frac{1}{n} \right)  \right) $$with $n$ s.t. $1-\frac{1}{n}\leq t<1 -\frac{1}{n+1}$ and $\gamma(1)=x_{0}$. Show that $\gamma$ is a well-defined continuous loop at $x_{0}$. 
> 6. Show that the class of $r_{n*}(\gamma)$ in $\pi_{1}(C_{n},x_{0})$ is the class of $\gamma_{n}$ in $\pi_{1}(C_{n},x_{0})$ for all $n\geq 1$. 
> 7. Conclude that there is a surjective group morphism $\pi_{1}(X,x_{0})\to \prod_{n}^{}\pi_{1}(C_{n},x_{0})$, and that $\pi_{1}(X,x_{0})$ is uncountable.