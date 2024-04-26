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
	- (1=>2): Let $s_{1}\neq s_{2}\in S$. We first show the claim that: $$\{ s_{1} \}=\bigcap_{s_{1}\in C\subseteq S,C\text{ clopen}}^{}C=:Q$$As $s_{1}\in Q$, it suffices to show that $Q$ is connected. Let $Q=W_{1}\sqcup W_{2}$ for $W_{1},W_{2}$ closed in $Q$, where we wlog assume that $s_{1}\in W_{1}$. As $Q$ is closed in $S$ by definition, so are $W_{1},W_{2}$. Therefore, due to $S$ being Hausdorff, there exists disjoint open sets $U,V\subseteq X$ s.t. $W_{1}\subseteq U$ and $W_{2}\subseteq V$ with $Q\subseteq U\cap V$. 
	  
	  Then, we claim that there exist $C_{1},\dots,C_{n}$ clopen sets containing $s_{1}$ s.t. $\bigcap_{i=1}^{n}C_{i}\subseteq U\cap V$. Otherwise, let: $$\mathcal{C}:=\{ C\subseteq S: C \text{ clopen}, s_{1}\in C \}$$ and $\mathcal{C}\cup \{ S \backslash (U\cap V) \}$ meets the finite intersection property. By compactness of $S$, $Q\not\subseteq V\cap W$, which is a contradiction.
	  
	  Therefore, $Q:=\bigcap_{i=1}^{n}C_{i}$ is clopen and $s_{1}\in Q$. Consider $D:=Q\cap V$. As $s_{1}\in C_{1}\subseteq V$, $s_{1}\in D$. One easily sees that $D$ is open, however it is also closed as $D=Q\cap(X \backslash  W)$ . Therefore, $U\subseteq D$ and $U\cap W=\varnothing$
	  
	  Now, we claim 