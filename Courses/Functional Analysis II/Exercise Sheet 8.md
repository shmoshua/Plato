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
	- (3=>4): 
	- (1=>2): For $s_{1}$, let $U$ be all the points $x\in S$ s.t. there exists no clopen decomposition $S=S_{1}\sqcup S_{2}$ with $s_{1}\in S$ and $x\in S_{2}$. Firstly, we claim that $U$ is closed. For $x\in \overline{U}$, if there exists such decomposition $S=S_{1}\sqcup S_{2}$, as $S_{2}$ is an open neighborhood of $x$, there exists $y\in U$ s.t. $S_{1}\sqcup S_{2}$ is still a valid decomposition. This is a contradiction and $U$ is closed.
	  
	  We claim that $U=\{ s_{1} \}$. It suffices to show that $U$ is connected. Let $U=C_{1}\sqcup C_{2}$ for $C_{1},C_{2}$ closed in $U$. As $U$ is closed, $C_{1},C_{2}$ are closed in $S$. Therefore, due to $S$ being Hausdorff, there exists $V,W\subseteq X$ disjoint open s.t. $C_{1}\subseteq V$ and $C_{2}\subseteq W$. 