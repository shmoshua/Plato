##### Problem 1

Let $x$ be a randomly chosen vertex. Then, our algorithm assigns $f(u):=d_{C}(x,u)$.

Let $u,v\in C$. We have that: $$\mathbb{E}[\left| f(u)-f(v) \right| ]=\mathbb{E}[\left| d_{C}(x,u)-d_{C}(x,v) \right| ]$$ Let $P$ be a $u$-$v$-path with length $d_{C}(u,v)$. Then, let $S$ be the inner nodes of $P$.


1. if $x\in S$, then we have that $d_{C}(x,u)+d_{C}(x,v)=d_{C}(u,v)$. Then, $$\left| d_{C}(x,u)-d_{C}(x,v) \right| =d_{C}(u,v)-2d_{C}(x,v) $$
	1. 
2. Let $S$ be ordered from $v$ in $1$ to $p:=d_{C}(u,v)$, i.e. $P=v:=v_{0},v_{1},\dots,v_{p}=u$. Then, for $i\leq p /2$, $$\left| d_{C}(x,u)-d_{C}(x,v) \right| =d_{C}(u,v)-2i$$$$\left| d_{C}(x,u)-d_{C} \right| $$and for $i> \frac{p}{2}$ we have that $\left| d_{C}(x,u)-d_{C}(x,v) \right|=2i-d_{C}(u,v)$
	Therefore, $$\sum_{i=1}^{\left\lfloor p/2\right\rfloor }d_{C}(u,v)-2i=k\cdot  d_{C}(u,v)- k(k+1) $$
	$$\sum_{i=k+1}^{p}2i-d_{C}(u,v)= (p-k)(k+1+p)-(p-k)d_{C}(u,v)$$Therefore, $$\sum_{i=1}^{p}\left| d_{C}(x,u)-d_{C}(x,v) \right| =(2k-p)d_{C}(u,v)-k^{2}-k+pk+p+p^{2}$$
   
$\left| d_{C}(x,u)-d_{C}(x,v) \right|\leq d_{C}(u,v)$ and further, 
$$\mathbb{P}(x\in S)=\frac{d_{C}(u,v)-1}{n}$$with $\left| d_{C}(x,u)-d_{C}(x,v) \right|\geq \min\{ d_{C}(x,u),d_{C}(x,v) \}$
2. if $x\notin S$, then $\left| d_{C}(x,u)-d_{C}(x,v) \right| = d_{C}(u,v)$: $$\mathbb{P}(x\notin S)=\frac{n-d_{C}(u,v)+1}{n}$$Therefore, we need that: $$\frac{n-d_{C}(u,v)+1}{n}d_{C}(u,v)+\sum_{i=0}^{d_{C}(u,v)}$$