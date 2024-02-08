#Definition #Algebra-I #Theorem 

> [!definition]
> Let $G$ be a finite group with order $\left| G \right|=p^mn$ where $p \nmid n$ and $p$ prime. Then, there exists a [[Subgroup|subgroup]] of $G$ of order $p^m$ called the ***Sylow $p$-subgroup***. The set of all Sylow $p$-subgroups of $G$ are denoted as $\text{Syl}_{p}(G)$.
---
##### Properties
> [!lemma] Lemma 1
> Let $G$ be a finite group with $|G|=p^m n$ where $p$ is prime and $p \nmid n$ . Let $P,Q \leq G$ s.t. $|P|=|Q|=p^m$. Then, $$Q\leq N(P)\iff P=Q$$
> where $N(P)$ is the [[Fixed Point of a Group|normalizer]] of $P$.

> [!proof]-
> One direction is clear as $P \leq N(P)$. Conversely, if $Q \leq N(P)$, then as $P \unlhd N(P)$, by [[Inner Product of Groups|Theorem 2]], $$PQ \leq N(P)$$Therefore, it holds that: $$\left| PQ \right| =\frac{\left| P \right| \cdot \left| Q \right| }{\left| P\cap Q \right|}= \frac{p^m\cdot p^m}{p^t}=p^k$$
> As $t\leq m$, we have that $k \geq m$. Further, as $p^k|p^m\cdot n$ and as $p \nmid n$, therefore, $k\leq m$. This proves that $k=m$, i.e. $t=m$ and $P\cap Q=P$. This proves that $P=Q$.
---
> [!lemma] Theorem 2 (Sylow Theorem)
> Let $\left| G \right|=p^mn$ where $p$ prime and $p \nmid n$. Then, 
> 1. there exists a Sylow $p$-subgroup of $G$
> 2. all Sylow $p$-subgroups are pairwise conjugated (and therefore isomorphic), i.e. for $P,Q\in \text{Syl}_{p}(G)$, there exists $x\in G$ s.t. $xP x^{-1}=Q$.
> 3. $\left| \text{Syl}_{p}(G) \right| \equiv_{p}1$
> 4. $\left. \left| \text{Syl}_{p}(G) \right|  \right| n$

>[!proof]-
>We prove that:
>1. We will use induction over $\left| G \right|$. 
> 	  - If $\left| G \right|=1$, then it trivially holds.
> 	  - If $\left| G \right|>1$ and assume that (1) holds for $G'$ with $\left| G' \right|<G$. Consider the [[Conjugation (Group Theory)|conjugation]] $G \curvearrowright G$, defined as $(a,x)\mapsto a x a^{-1}$. Then, $$\left| G \right| =\left| Z(G) \right| +\sum_{j=1}^{s}[G:Z_{G}(x_{j})]$$for all $x_{j}$ with orbit size $>1$. 
> 	    
> 	    If $s=0$, then $Z(G)=G$. This means that $G$ is abelian and as a finitely generated abelian group, there exists a Sylow $p$-subgroup.
> 	    
> 	    If $s>0$, then $Z(G)<G$ and there exists $x_{j}$ s.t. $[G:Z_{G}(x_{j})]> 1$. We can then do a case distinction: 
> 	    
> 	    1. For all $1\leq j\leq s$, $p|[G:Z_{G}(x_{j})]$. Then, $p|\left| Z(G) \right|$ and $\left| Z(G) \right|>1$. As $Z(G)$ is abelian, $$Z(G)\cong C_{n_{1}}\times C_{n_{2}}\times\dots \times C_{n_{s}}$$with $n_{i}|n_{i+1}$. It follows that, $p|n_{s}$. Therefore, there exists $a\in Z(G)$ with $\text{ord}(a)=p$. As $\braket{ a }\leq Z(G)$, $\braket{ a } \unlhd G$. Let $\pi:G \to G / \braket{ a  }$ be the [[Group Homomorphism|natural homomorphism]]. Then, $$[ G  :\braket{ a  }  ] =\frac{\left| G \right|}{\left| \braket{ a }  \right| } =p^{m-1}n$$From the induction hypothesis, there exists a Sylow $p$-subgroup $P'$ of order $p^{m-1}$ in $G / \braket{  a  }$. Then, the pre-image $P=\pi^{-1}(P') \leq G$ is a subgroup of order $p^m$ and a Sylow $p$-subgroup.
> 	    2. There exists $1\leq j_{0}\leq s$ s.t. $p \nmid [G:Z_{G}(x_{j_{0}})]$. Then, $|Z_{G}(x_{j_{0}})|=p^mk$ for $k<n$ and $k | n$. Then, from the induction hypothesis, there exists a Sylow $p$-subgroup of order $p^m$.
>2. Let $P$ be the Sylow $p$-subgroup of $G$ from 1. Then, we define: 
>	1. $\Omega:=\{ xPx ^{-1}: x\in G \}$ with $\left| \Omega \right|=[G:N(P)]$ from [[Fixed Point of a Group|this example]].
>	2. $\Omega_{i}:=\{ y P_{i}y^{-1}: y\in P \}$ for $P_{i}\in \Omega$ with $\left| \Omega_{i} \right|=[P:N(P_{i})\cap P]$ from $P \curvearrowright \Omega$.
> 
>    Then, $\Omega$ is a disjoint union of $\Omega_{i}$, i.e. $\left| \Omega \right| =\sum_{i}^{}\left| \Omega_{i}\right|$. Followings are the observations:
>    1. For all $i$, $\left| \Omega_{i} \right|=p^{k_{i}}$ where $0\leq k_{i}\leq m$.
>    2. $\left| \Omega_{i} \right|=1$ if and only if $P\leq N(P_{i})$ if and only if $P=P_{i}$ from Lemma 1.
>
>    Therefore, $p | \left| \Omega_{i}\right|$ for all $i$ mit $P_{i}\neq P$. It follows that: $$\left| \Omega \right| =\sum_{i}^{}\left| \Omega_{i}\right| =1 \mod p$$
> 	
> 	Now we only have to show that $\Omega=\text{Syl}_{p}(G)$. The inclusion $\subseteq$ is clear. Conversely, assume that there exists a Sylow $p$-subgroup $Q \notin \Omega$, i.e. $Q$ is not conjugated to $P$. 
> 	
> 	Let us now consider $Q \curvearrowright\Omega$ similarly as above and for $P_{i}\in\Omega$, $\Omega_{i}^{Q}:=\{ yP_{i}y^{-1}: y\in Q \}$ has a cardinality divisible by $p$. Otherwise, we have that $Q \leq N(P_{i})$ and $Q=P_{i}$, i.e. $Q$ is a conjugate of $P_{0}$. Therefore, $p | \left| \Omega\right|$, which is a contradiction. 
> 	
> 	Therefore, $\left| \text{Syl}_{p}(G) \right|\equiv_{p}1$ and furthermore every Sylow $p$-subgroups are conjugates of each other. 
> 
> 3. From 2)
> 4. Let $P\in \text{Syl}_{p}(G)$. With 2, we have: $\text{Syl}_{p}(G)=\{ x P x^{-1}: x\in G\}$ and $|\text{Syl}_{p}(G)|=[G:N(P)]$. As $P\leq N(P)\leq G$, we have $\left| N(P) \right|=p^mk$ for $k\leq n$. Therefore, $k|n$ and if $n=sk$, $|\text{Syl}_{p}(G)|=s$.
- **Corollary**: $\text{Syl}_{p}(G)=\{ P \}\iff P\unlhd G$, i.e. a Sylow $p$-subgroup is a [[Normal Subgroup|normal divisor]] only if $\left| \text{Syl}_{p}(G) \right|=1$ .
---
##### Examples
- Let $G$ be the [[Cube Group|cube group]], i.e. $G \cong S_{4}$. Then, $\left| G \right|=24=3^1\cdot 8=2^3 \cdot 3$. Therefore, 
	- there exists subgroups with order $3$ and $8$.
	- $\left| \text{Syl}_{3}(G) \right|=1,4,7,10,\dots$ and $\left| \text{Syl}_{3}(G) \right| | 8$. Therefore, $\left| \text{Syl}_{3}(G) \right|=4$.
	- $\left| \text{Syl}_{2}(G) \right|=1,3,5,7,9,\dots$ and $\left| \text{Syl}_{2}(G) \right| | 3$. Therefore, $\left| \text{Syl}_{2}(G) \right|=3$.
- Let $D$ be the [[Dodecahedron group]]. Then, $\left| D \right|=60=2^{2}\cdot 3\cdot 5$. Then, 
	- $|\text{Syl}_{2}(D)|=1,3,5,15$ is isomorphic to $C_{2}\times C_{2}$. Therefore, $|\text{Syl}_{2}(D)|=5$, rotations from opposing points from $\pi$
	- $|\text{Syl}_{3}(D)|=1,4,10$ is isomorphic to $C_{3}$.
	- $\left| \text{Syl}_{5}(D) \right|=1,6$ is isomorphic to $C_{5}$.
---