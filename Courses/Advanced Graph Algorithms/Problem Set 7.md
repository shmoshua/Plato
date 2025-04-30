#### Exercise 1
1. Let $G=(V,E,c)$ be a directed and capacitated graph with $n$ vertices and $m$ edges. Let $d\  \bot\  1$ be an integral demand vector. We add edges into $G$ and create a new directed and capacitated graph $G'$ on $V':= V\sqcup \{ s,t \}$ as follows. Further, we assume we know the maximal value $F$ which we can find using binary search on the following algorithm by $O(\log n)$ factor.
   
   For every $v\in V$, if $d(v)> 0$, then we add an edge $vt$ in $G'$ with capacity $Fd(v)$. Otherwise, i.e. $d(v)< 0$, we add an edge $sv$ with capacity $-Fd(v)$. Lastly, we add $ts$ with $n^{10}$ capacity. Then, $c'$ meets the capacity requirements of the $st$-maximum flow algorithm. 
   
   Assume $f'$ is an integral maximum flow for $G'$ with $s,t$ as the source and the sink, which exists. For $f:= f'|_{E}$, we have that: $(Bf)(v)=(B'f')(v)+Fd(v)=Fd(v)$. Further $f$ is feasible as $f'$ is. 
2. Firstly, let $f$ be a maximal flow $f$ from 1, s.t. $Bf=Fd$. Then, we get that $\left\| \text{diag}(c)^{-1}f \right\|_{\infty}=1$, otherwise none of the edges are saturated and we can improve the flow contradicting the optimality. Hence, by setting $f':= \frac{1}{F}f$, we have that $Bf'=d$ and $$\left\| \text{diag}(c)^{-1}f' \right\|_{\infty} = \frac{1}{F}$$This shows that $Q\leq \frac{1}{F}$. To show the converse, for any flow $f\geq 0$ with $Bf=d$, if $\left\| \text{diag}(c)^{-1}f \right\|_{\infty}< \frac{1}{F}$, we again have that $\left\| \text{diag}(c)^{-1}Ff \right\|_{\infty}< 1$ and we can improve the flow. This contradicts the maximality of $F$. 
   
   Now, let $f$ be a flow that achieves $Q$. Then, $f':=\frac{f}{Q}=Ff$ is feasible as $$\max_{e\in E}\frac{f'(e)}{c(e)} = \left\| \text{diag}(c)^{-1}F f \right\|_{\infty}=F\cdot Q=1$$Further $Bf'=FBf=Fd$.

---
#### Exercise 3
