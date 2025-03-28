#Series #GraphTheory 

#### Problem 1
We have that $K_{3,3}$ is not planar. Therefore, if $3\leq r$ then $K_{r,s}$ contains $K_{3,3}$ and is not planar. 
1. Assume that $r=1$. Then, $K_{r,s}$ is a star and is planar for any $s$.
2. Assume that $r=2$. Then, $K_{r,s}=(A\cup B,E)$ is planar by having the $s$ nodes from $B$ between the two nodes from $A$ for any $s$. 

Therefore, $K_{r,s}$ with $r\leq s$ is planar if and only if $r\leq 2$.

---
#### Problem 2
1. Assume that $\delta(G)\geq 6$. Then, $$e(G)=\frac{\sum_{v\in V(G)}^{}d(v)}{2}\geq 3\left| G \right| > 3\left| G \right| -6 $$Therefore $G$ cannot be planar. Further, this gives us that any planar graph with $\delta(G)= 5$ needs to have at least $12$ vertices. In fact, there is one on exactly 12 vertices.
2. As $G$ is bipartite, it is triangle free. Assume $\delta(G)\geq 4$. Then, $$e(G)\geq 2\left| G \right| > 2\left| G \right| -4$$