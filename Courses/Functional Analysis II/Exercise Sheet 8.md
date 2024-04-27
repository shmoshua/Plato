#Series #FunctionalAnalysis 

> [!def] Problem 1
> Recall that a compact Hausdorff space $S$ is called totally disconnected if the connected components of $S$ are precisely the points. For each compact Hausdorff space $S$, we define $$C_{\text{fin}}(S):=\{ f\in C(S):\left| \text{im}(f) \right| <+\infty \}$$Note that $C_{\text{fin}}(S)$ is an involutive and unital subalgebra of $C(S)$.
> 1. Prove that the following conditions are equivalent for a compact Hausdorff space $S$:
> 	1. The space $S$ is totally disconnected. 
> 	2. For each pair of disctinct points $s_{1},s_{2}\in S$ there exists a clopen decomposition $S=S_{1}\sqcup S_{2}$ s.t. $s_{1}\in S_{1}$ and $s_{2}\in S_{2}$. 
> 	3. For each pair of distinct points $s_{1},s_{2} \in S$ there exists a continuous function $\phi:S\to \{ 0,1 \}$ s.t. $\phi(s_{1})=0$ and $\phi(s_{2})=1$. 
> 	4. The subalgebra $C_{\text{fin}}(S)\subseteq C(S)$  is dense.
> 2. Let $X$ be a compact Hausdorff space. Prove that there exists a totally disconnected compact Hausdorff space $S$ and a continuous surjection $S\to X$.

For a compact Hausdorff space $S$ and $s\in S$, let $S_{0}\subseteq S$ be the connected component of $s$. Then, we claim that:$$S_{0}=\bigcap_{s\in C\subseteq S, C\text{ clopen}}^{}C=:Q$$
Let $C\subseteq S$ be a clopen set s.t. $s\in C$. Then, $S_{0}\subseteq C$ as $S_{0}$ is connected and it does not contain any non-empty strict clopen subset. To show the other inclusion, it suffices to show that $Q$ is connected. Let $Q=W_{1}\sqcup W_{2}$ for $W_{1},W_{2}$ closed in $Q$, where we wlog assume that $s\in W_{1}$. As $Q$ is closed in $S$ by definition, so are $W_{1},W_{2}$. Therefore, due to $S$ being Hausdorff, there exists disjoint open sets $U,V\subseteq X$ s.t. $W_{1}\subseteq U$ and $W_{2}\subseteq V$ with $Q\subseteq U\cap V$. 
	  
Then, we claim that there exist $C_{1},\dots,C_{n}$ clopen sets containing $s$ s.t. $\bigcap_{i=1}^{n}C_{i}\subseteq U\cap V$. Otherwise, let: $$\mathcal{C}:=\{ C\subseteq S: C \text{ clopen}, s\in C \}$$ and $\mathcal{C}\cup \{ S \backslash (U\cap V) \}$ meets the finite intersection property. By compactness of $S$, $Q\not\subseteq U\cap V$, which is a contradiction.
	  
Therefore, $Q=\bigcap_{i=1}^{n}C_{i}$ is clopen and $s\in Q$. Consider $A:=Q\cap U$. As $s\in W_{1}\subseteq U$, $s\in A$. One easily sees that $A$ is open, however it is also closed as $A=Q\cap(S \backslash  V)$ . Therefore, $Q\subseteq A$ and thereby $W_{2}=V\cap Q=\varnothing$. This proves that $Q$ is connected and $Q\subseteq S_{0}$.

Now we solve the problems.



1. We will show as follows:
	- (1=>2): Let $s_{1}\neq s_{2}\in S$. From the above claim, $\{ s_{1} \}=\bigcap_{s\in C\subseteq S, C\text{ clopen}}^{}C$. Then, there exists a clopen set $S_{1}\ni s_{1}$ s.t. $s_{2}\notin S_{1}$. We prove the statement by taking $S_{2}:=S \backslash S_{1}$.
	- (2=>1): For any distinct $s_{1}\neq s_{2}\in S$, there exists a clopen set $S_{1}\ni s_{1}$ that does not contain $s_{2}$. By the above claim, $\{ s_{1} \}=\bigcap_{s\in C\subseteq S, C\text{ clopen}}^{}C$ and $S$ is totally disconnected.
	- (2=>3): Let $s_{1},s_{2}\in S$ be distinct and let $S=S_{1}\sqcup S_{2}$ be the clopen decomposition. Then, $$\begin{array}{cccc} {\phi:}&{S}&\to&{\{ 0,1 \}}\\&{x} &\mapsto & {\begin{cases}0&x\in S_{1}\\1&x\in S_{2}\end{cases}} \end{array}{}$$is continuous.
	- (3=>4): We notice that for any $s_{1}\neq s_{2}\in S$ and $\phi$ from 3, $\phi\in C_{\text{fin}}(S)$. Therefore, $C_{\text{fin}}(S)$ is a separating set and by Stone-Weierstrass, $C_{\text{fin}}(S)\subseteq C(S)$ is dense.
	- (4=>2): Let $s_{1}\neq s_{2}\in S$. As $S$ is normal, there exists a function $f:S\to[0,1]$ s.t. $f(s_{1})=0$ and $f(s_{2})=1$. By density of $C_{\text{fin}}(S)$, there exists $g\in C_{\text{fin}}(S)$ s.t. $\|g-f\|_{\infty}< \frac{1}{2}$. Therefore, there exists $g\in C_{\text{fin}}(S)$, s.t. $g(s_{1})\neq g(s_{2})$. As $\text{im }g$ is finite, $g^{-1}(\{ y\})$ is a clopen set for all $y\in \text{im }g$. Therefore, there exists a clopen set $S_{1}:=g^{-1}(\{ g(s_{1}) \})$ s.t. $s_{2}\notin S_{1}$.
2. Consider the inclusion $i:C(X)\hookrightarrow C_{b}(X^{\text{disc}})$, which is well defined as $X$ is compact. Consider the adjoint map: $$\begin{array}{cccc} {I:}&{\widehat{C_{b}(X^\text{disc})}}&\to&{\widehat{C(X)}}\\&{\chi} &\mapsto & {\chi \circ i} \end{array}{}$$is then a surjective map. To see that it is also continuous, let $\chi_{0}\in \widehat{C(X)}$, $f_{1},\dots,f_{n}\in C(X)$ and $\varepsilon>0$. For $\chi\in \widehat{C(X)}$, $$\left| \chi(f_{i})-\chi_{0}(f_{i}) \right| $$Then, for $$\varphi\in I^{-1}(\mathcal{U}(\chi_{0};f_{1},\dots,f_{n};\varepsilon))$$, $$$$
   
   Then,  $C_{b}(X^\text{disc})$ is a $C^{*}$-algebra and:
	1. **Showing that $(C_{b}(X^{\text{disc}}))_{\text{fin}}\subseteq C_{b}(X^\text{disc})$ is dense**: 
	   Let $f\in C_{b}(X^\text{disc})$ s.t. $\text{im }f\subseteq[0,+\infty)$. Then, for $n\in \mathbb{N}$, we can define $$\begin{array}{cccc} {\phi_{n}:}&{[0,+\infty)}&\to&{\mathbb{R}}\\&{t} &\mapsto & {\begin{cases} k2^{-n} &\text{if }k 2^{-n}\leq t<(k+1),\  k= 0,1,\dots,n2^{n}-1\\n&\text{if }t\geq n\end{cases}} \end{array}{}$$
	   Then, $\{ \phi_{n}\circ f \}_{n}\subseteq (C_{b}(X^{\text{disc}}))_{\text{fin}}$ s.t. $\phi_{n}\circ f_{n}\to f$ in $C_{b}(X^{\text{disc}})$. For a general $f\in C_{b}(X^{\text{disc}})$, we can use the decomposition: $$f=(f^+ -f^-)+i(g^+ -g^-)$$where $f^+,f^-,g^+,g^-$ are positive valued functions.
	2. **Showing that $\widehat{C_{b}(X^\text{disc})}\to X$ is surjective**: 
	   Consider $$\begin{array}{cccc} {T:}&{\widehat{C_{b}(X^\text{disc})}}&\to&{\widehat{C(X)}}\\&{\chi} &\mapsto & {\chi|_{C(X)}} \end{array}{}$$is a surjective map. Let $\varphi\in \widehat{C(X)}$. Let $f\in C(X)$, then, $$\widehat{f}(\widehat{C(X)})$$
	3. **Showing that $\widehat{C_{b}(X^\text{disc})}$ is totally disconnected**:
	   As $C_{b}(X^\text{disc})$ is unital, $\widehat{C_{b}(X^\text{disc})}$ is compact Hausdorff. Further, for $f\in C_{b}(X^\text{disc})$ and $\lambda\in \mathbb{C}$, it holds that $\lambda\in \text{Sp}_{C_{b}(X^\text{disc})}(f)$ if and only if $\lambda \in \text{im }f$. Therefore, $$\text{im }f=\text{Sp}_{C_{b}(X^\text{disc})}(f)=\widehat{f}(\widehat{C_{b}(X^\text{disc})})=\text{im }\widehat{f}$$Therefore, the Guelfand isomorphism holds for $(C_{b}(X^\text{disc}))_{\text{fin}}\cong C(\widehat{C_{b}(X^\text{disc})})_{\text{fin}}$. It follows that $(C_{b}(X^{\text{disc}}))_{\text{fin}}\subseteq C_{b}(X^\text{disc})$ being dense implies that $C(\widehat{C_{b}(X^\text{disc})})_{\text{fin}}\subseteq C(\widehat{C_{b}(X^\text{disc})})$ is dense. Consequently, $\widehat{C_{b}(X^\text{disc})}$ is totally disconnected.
	   
---
> [!def] Problem 2
> Prove that the quotient groups $\mathbb{Q}_{p}/\mathbb{Z}_{p}$ are discrete for each prime $p\in \mathbb{N}$. Moreover, prove that they are isomorphic to $$\{ z\in \mathbb{T}\ |\  \exists n\geq 1:z^{p^n}=1 \}$$ as abstract groups.
---
> [!def] Problem 3
> Let $G$ be a connected topological group and $\Gamma\unlhd G$ a discrete normal subgroup. Show that $\Gamma \subseteq Z(G)$.

For each $h\in \Gamma$, we can consider the continuous map: $$\begin{array}{cccc} {\varphi_{h}:}&{G}&\to&{\Gamma}\\&{g} &\mapsto & {ghg^{-1}} \end{array}{}$$Then, the image is connected and as $\Gamma$ is discrete, $\varphi_{h}(G)=\{ h \}$. In other words, $ghg^{-1}=h$ for all $g\in G$ and $h\in Z(G)$.

---
