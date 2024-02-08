#Series #Algebra-I 

##### Problem 38
We will use induction over $\left| G \right|$. 
1. If $\left| G \right|=1$, then it trivially holds.
2. If $\left| G \right|>1$, assume that (1) holds for $G'$ with $\left| G' \right|<G$. Consider the [[Conjugation (Group Theory)|conjugation]] $G \curvearrowright G$, defined as $(a,x)\mapsto a x a^{-1}$. Then, $$\left| G \right| =\left| Z(G) \right| +\sum_{j=1}^{s}[G:Z_{G}(x_{j})]$$for all $x_{j}$ with orbit size $>1$. 

If $s=0$, then $Z(G)=G$. As $Z(G)$ is abelian, $$Z(G)\cong C_{n_{1}}\times C_{n_{2}}\times\dots \times C_{n_{s}}$$with $n_{i}|n_{i+1}$. It follows that, $p|n_{s}$. Therefore, there exists $a\in Z(G)$ with $\text{ord}(a)=p$.

If $s>0$, then $Z(G)<G$ and there exists $x_{j}$ s.t. $[G:Z_{G}(x_{j})]\geq 1$. We can then do a case distinction: 

1. For all $1\leq j\leq s$, $p|[G:Z_{G}(x_{j})]$. Then, $p|\left| Z(G) \right|$ with the same reasoning as above, there exists $a\in Z(G)$ with $\text{ord}(a)=p$.
2. There exists $1\leq j_{0}\leq s$ s.t. $p \nmid [G:Z_{G}(x_{j_{0}})]$. Then, $|Z_{G}(x_{j_{0}})|<|G|$ and $p|\left| Z_{G}(x_{j_{0}}) \right|$. Therefore, from the induction hypothesis, there exists an element $a\in G$ with order $\text{ord}(a)=p$.
---
##### Problem 39
1. Let $G$ be a group with order $\left| G \right|=40=2^3\cdot 5$. Then, $\left| \text{Syl}_{5}(G) \right|\equiv_{5}1$ and $|\text{Syl}_{5}(G)| | 8$. Therefore, $|\text{Syl}_{5}(G)|=1$. It follows that $G$ has a normal subgroup of order $5$. Thus, $G$ is not simple.
2. Let $G$ be a group with order $\left| G \right|=56=2^3\cdot 7$. Then, $\left| \text{Syl}_{7}(G) \right|\equiv_{7}1$ and $|\text{Syl}_{7}(G)| | 8$. Therefore, $|\text{Syl}_{7}(G)|=1$ or $8$. 
	- If $\left| \text{Syl}_{7}(G) \right|=1$, we have a normal subgroup of order $7$. Therefore, we are done. 
	- If $\left| \text{Syl}_{7}(G) \right|=8$, every non-trivial element in these subgroups have order $7$. Further, the subgroups only intersect trivially. This means, there are at least $48$ elements of order $7$. Now, as we know there exist a Sylow $2$-subgroup $P$ with order $2^{3}=8$, but no element in $P$ can have an order $7$, we know that there is only Sylow $2$-subgroup. Therefore, we have a normal subgroup of order $8$ and $G$ is not simple.
---
##### Problem 40
1. For the tetrahedron group $T$, we have $\left| T \right|=12=2^{2}\cdot 3$. Therefore,
	- As we know that $T$ has a normal subgroup of order $4$, $\left| \text{Syl}_{2}(T) \right|=1$.
	- $\left| \text{Syl}_{3}(T) \right|\equiv_{3}1$ and $\left| \text{Syl}_{3}(T) \right| | 4$. Therefore, $\left| \text{Syl}_{3}(T) \right|=1$ or $4$. But as there is no normal subgroup of order $3$, $\left| \text{Syl}_{3}(T) \right|=4$.
2. For the cube group $T$, we have $\left| C \right|=24=2^{3}\cdot 3$. Therefore, from the Sylow theorems,
	- $\left| \text{Syl}_{2}(T) \right|=1$ or $3$. However, for each pair of opposing faces of the cube,     the rotations by $\frac{\pi}{2}$ and $\pi$ have order $4$ and $2$, respectively and should be in at least one Sylow $2$-group. As there are 6 rotations of the first kind and 3 for the second, we need more than 1 Sylow $2$-group. Therefore, $\left| \text{Syl}_{2}(T) \right|=3$.
	- $\left| \text{Syl}_{3}(T) \right|=1$ or $4$. However, there are $8$ elements of order $3$ and they all have to be contained in at least one Sylow $3$-subgroup. Therefore, we cannot have 1 Sylow $3$-subgroup and $\left| \text{Syl}_{3}(T) \right|=4$.
3. For the dodecahedron group $D$, we have $\left| D \right|=60=2^{2}\cdot 3\cdot 5$. Then, from the Sylow theorems,
	 - $\left| \text{Syl}_{2}(T) \right|=1,3,5$ or $15$. As we know that each Sylow 2-group is isomorphic to $C_{2}\times C_{2}$ and there are $15$ elements of order-2 in $D$, we have that $\left| \text{Syl}_{2}(T) \right|=5$.
	 - $\left| \text{Syl}_{3}(T) \right|=1,4$ or $10$. As each 3-cycle has to be in one of the groups and there are 20 of them, we have that $\left| \text{Syl}_{3}(T) \right|=10$.
	 - $\left| \text{Syl}_{5}(T) \right|=1$ or $6$. As each 5-cycle has to be in one of the groups and there are 24 of them, we have that $\left| \text{Syl}_{5}(T) \right|=6$.
---
##### Problem 41
We can define a homomorphism $\varphi:G \to S_{n}$ where $\varphi(a)(b)=ab$. Then, we have: $$\text{ker}\varphi=\{ a\in G:ab=b\quad \forall b\in G \}=\{ e \}$$Therefore, by the first isomorphism theorem, we have that: $$G\cong \text{Im}\ \varphi$$which proves the statement.

---
##### Problem 42
1. Let $\rho,\sigma\in S_{n}$ be disjoint permutations. We will show that $\rho$ and $\sigma$ commute. Assume there exists $i_{0}\in[n]$ s.t. $(\rho\sigma)(i_{0})\neq(\sigma\rho)(i_{0})$. Then, we can perform a case distinction:
    - If $\sigma(i_{0})=i_{0}$, then:$$\sigma(i_{0})=i_{0}\implies\rho(i_{0})\neq\sigma\rho(i_{0})\implies\rho(\rho(i_{0}))=\rho(i_{0})\implies\rho(i_{0})=i_{0}$$Plugging this back, we get that: $(\rho\sigma)(i_{0})= i_{0}\neq i_{0}=(\sigma\rho)(i_{0})$.
     - If $\sigma(i_{0})\neq i_{0}$, then: $$\rho(i_{0})=i_{0}\implies(\rho\sigma)(i_{0})\neq\sigma(i_{0})\implies\sigma(\sigma(i_{0}))=\sigma(i_{0})\implies\sigma(i_{0})=i_{0}$$

	Therefore, $\rho$ and $\sigma$ commute and it follows that $(\rho\sigma)^k=\sigma^k\rho^k$.
2. Let $\rho$ be a $k$-cycle in $S_{n}$ and $i$ be an element s.t. $\rho^k(i)=i$. Then,
	- If $j\in \{ \rho^s(i):s\in \mathbb{N} \}$, then:$$\rho^k(j)=\rho^k(\rho^s(i))=\rho^s(\rho^k(i))=\rho^s(i)=j$$
	- If $j\in [n] \backslash\{ \rho^s(i):s\in \mathbb{N} \}$, then $\rho(j)=j$ and $\rho^k(j)=j$.
	  
	Therefore, $\rho^k=\iota$ and $\text{ord}(\rho)=k$.
3. First, we show that if $\rho$ is disjoint with $\sigma_{1},\dots,\sigma_{s}$, $\rho$ is disjoint with the product $\sigma$ as well. We have that:
	- If $\rho(i)\neq i$, then for all $i\in[s]$, $\sigma_{i}(i)=i$ and $\sigma(i)=i$.
	- If $\sigma(i)\neq i$, then there exists $i\in[s]$ s.t. $\sigma_{i}(i)\neq i$. Therefore, $\rho(i)=i$.
	  
	Therefore, let $\pi=\rho_{1}\circ\dots \circ\rho_{r}$ where $\rho_{1,\dots,}\rho_{r}$ are pairwise disjoint cycles of length $k_{1},\dots,k_{r}$. Then, for any $j\in \mathbb{N}$: $\pi^j=\rho_{1}^j\circ \dots \circ \rho^j_{r}$. As they are all pairwise disjoint, we have that the smallest number $j$ that would make $\pi^j=\iota$ is $\text{ord}(\pi)=\text{lcm}(k_{1},\dots,k_{r})$.
---
##### Problem 43
1. Let $(i,j)$ be a transposition. Wlog we can assume that $i < j$. Then, $$(i,j)=(i,i+1)(i+1,i+2)\dots(j-1,j)$$ 
2. We have that: 
	$$(i_{1},\dots,i_{k})=(i_{1},i_{2})(i_{2},i_{3}),\dots,(i_{k-1},i_{k})$$
3. We will show that every elementary transposition $(i,i+1)$ can be written as a product of $(1,2)$ and $(1,\dots,n)$. Then, the statement follows. 
   
   For $(i,i+1)$, we have:$$(i,i+1)=(1,\dots,n)^{i-1}(1,2)(1,\dots,n)^{n-i+1}$$
---
