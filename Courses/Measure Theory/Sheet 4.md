#MeasureTheory #Series 

##### Exercise 4.1
Let $A \subseteq \mathbb{R}^n$. Then, we want to show that: 
$$\mathcal{L}^n(A)=\mathcal{L}^n(\Phi(A))$$
If $A$ is an interval, by the invariance of the Jordan measure, we have that $\Phi(A)$ are Jordan-measurable and: $$\mathcal{L}^n(\Phi(A))=\mu(\Phi(A))=\mu (A)=\mathcal{L}^n(A)$$
If $A$ is an open set, then $A=\bigcup_{k=1}^{\infty}I_{k}$ for disjoint intervals $\{ I_{k} \}_{k\geq 1}$. As $\Phi^{-1}$ is also an affine map between $\mathbb{R}^n$ and therefore continuous, we know that $\Phi(A)$ is an open set (therefore, $\mathcal{L}^n$-measurable). Therefore, $\Phi(A)=\bigcup_{k=1}^{\infty}\Phi(I_{k})$ where $\{\Phi(I_{k})\}_{k\geq 1}$ are disjoint. It follows that: $$\mathcal{L}^n(\Phi(A))=\sum_{k=1}^{\infty}\mathcal{L}^n(\Phi(I_{k}))=\sum_{k=1}^{\infty}\mathcal{L}^n(I_{k})=\mathcal{L}^n(A)$$Finally, for any $A$, we have that: $$\mathcal{L}^n(\Phi(A))=\inf_{\Phi(A)\subseteq \Phi(G), \Phi(G)\text{ open}}\mathcal{L}^n(\Phi(G))=\inf_{{A\subseteq G,G\text{ open}}}\mathcal{L}^n(G)=\mathcal{L}^n(A)$$
This proves the statement.
---
##### Exercise 4.2
1. **True**. Singleton sets are Borel and so is its countable union.
2. **False**. We saw $Q \cap [0,1]$ is not Jordan-measurable.
3. **True**. Singleton sets have Lebesgue-measure zero and the rest follows from the $\sigma$-sub-additivity.
4. **True**. We can use a similar argument as for $Q \cap [0,1]$.
5. **False**. We saw $Q \cap [0,1]$ has outer Jordan-measure 1.
---
##### Exercise 4.3
1. Let $P$ be the Vitali set. For any rational number $q$, we define: $$P_{q}:=\{ q+p:p\in P \}$$
	Then, we can have: $$0<\mathcal{L}^1(A)\leq \sum_{q\in \mathbb{Q}}^{}\mathcal{L}^1(A \cap P_{q})$$
	As all $\mathcal{L}^1$-measurable subsets of $A$ have measure zero, this means there exists $q$ s.t. $A \cap P_{q}$ is not $\mathcal{L}^1$-measurable.
2. Let $P$ be the Vitali set. As it is non-measurable, we have a subset $B$ s.t. $$\mathcal{L}^1(B)<\mathcal{L}^1(B\cap P)+ \mathcal{L}^1(B \backslash P)$$As $B \cap P$ and $B \backslash P$ are disjoint, we can set $E_{1}=B \cap P$, $E_{2}=B \backslash P$ and $E_{k}=\varnothing$ for $k\geq 3$.Then, $$\mathcal{L}^1\left( \bigcup_{k=1}^{\infty}E_{k} \right) =\mathcal{L}^1(B)<\mathcal{L}^1(B \cap P)+\mathcal{L}^1( B \backslash P)=\sum_{k=1}^{\infty}\mathcal{L}^1(E_{k})$$
---
##### Exercise 4.4
