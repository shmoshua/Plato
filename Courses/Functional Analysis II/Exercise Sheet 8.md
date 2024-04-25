#Series #FunctionalAnalysis 

> [!def] Problem 1
> Recall that a compact Hausdorff space $S$ is called totally disconnected if the connected components of $S$ are precisely the points. For each compact Hausdorff space $S$, we define $$C_{\text{fin}}(S):=\{ f\in C(S):\left| \text{im}(f) \right| <+\infty \}$$Note that $C_{\text{fin}}(S)$ is an involutive and unital subalgebra of $C(S)$.
> 1. Prove that the following conditions are equivalent for a compact Hausdorff space $S$:
> 	1. The space $S$ is totally disconnected. 
> 	2. For each pair of disctinct points $s_{1},s_{2}\in S$ there exists a clopen decomposition $S=S_{1}\sqcup S_{2}$ s.t. $s_{1}\in S_{1}$ and $s_{2}\in S_{2}$. 
> 	3. For each pair of distinct points $s_{1},s_{2} \in S$ there exists a continuous function $\phi:S\to \{ 0,1 \}$ s.t. $\phi(s_{1})=0$ and $\phi(s_{2})=1$. 
> 	4. The subalgebra $C_{\text{fin}}(S)\subseteq C(S)$  is dense.
> 2. Let $X$ be a compact Hausdorff space. Prove that there exists a totally disconnected compact Hausdorff space $S$ and a continuous surjection $S\to X$.

We have: 
1. We will show as follows:
	- (1=>3): Assume that for all continuous function $\phi:S\to \{ 0,1 \}$, $\phi(s_{1})=\phi(s_{2})$. Then, $\phi|_{\{ s_{1},s_{2} \}}$ is continuous 
	

	- (1=>2): Let $s_{1}\neq s_{2}\in S$. Let $U$ be the smallest clopen set containing $s_{1}$, i.e. it is the intersection of all clopen neighborhoods of $s_{1}$. To show that $U=\{ s_{1} \}$, it suffices to show that $U$ is connected. Let $U=C_{1}\sqcup C_{2}$ for $C_{1},C_{2}$ closed in $U$. As $U$ is closed by definition, $C_{1},C_{2}$ are closed in $S$. Therefore, due to $S$ being Hausdorff, there exists $V,W\subseteq X$ disjoint open s.t. $C_{1}\subseteq V$ and $C_{2}\subseteq W$ with $U\subseteq V\cap W$. 
	  
	  Then, there exist $Q_{1},\dots,Q_{n}$ clopen sets containing $s_{1}$ s.t. $\bigcap_{i=1}^{n}Q_{i}\subseteq V\cap W$. Otherwise, let $\mathcal{C}$ be the family of all clopen neighborhoods of $s_{1}$ and $\mathcal{C}\cup \{ X \backslash (V\cap W) \}$ meets the finite intersection property and by compactness of $S$, $U\not\subseteq V\cap W$, which is a contradiction.
	  
	  Therefore, $Q:=\bigcap_{i=1}^{n}Q_{i}$ is clopen and $s_{1}\in Q$. Consider $D:=Q\cap V$. 
	  
	  Now, we claim 