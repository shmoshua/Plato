#### Exercise 1
1. Let $G=(V,E,c)$ be a directed and capacitated graph with $n$ vertices and $m$ edges. Let $d\  \bot\  1$ be an integral demand vector. We add edges into $G$ and create a new directed and capacitated graph $G'$ on $V':= V\sqcup \{ s,t \}$ as follows. Further, we assume we know the maximal value $F$ which we can find using binary search on the following algorithm by $O(\log n)$ factor.
   
   For every $v\in V$, if $d(v)> 0$, then we add an edge $vt$ in $G'$ with capacity $d(v)$. Otherwise, i.e. $d(v)< 0$, we add an edge $sv$ with capacity $-d(v)$. Then, $c'$ meets the capacity requirements of the $st$-maximum flow algorithm. 
   
   Assume $f'$ is a maximum flow for $G'$ with $s,t$ as the source and the sink. For $f:= f'|_{E}$, we have that: $$(Bf)(v)=(B'f')(v)+d(v)=-d(v)$$

   
   
	1. $V':= V\sqcup \{ s,t \}$.
	2. $E':=E\sqcup$
2. $$G:= (V':=V\sqcup \{ s,t \},E)$$