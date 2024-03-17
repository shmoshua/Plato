#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $X$ be a locally compact Hausdorff space. Show that the canonical map $$X\to \widehat{C_{0}(X)}$$is a homeomorphism while $\widehat{C_{0}(X)}$ is endowed with the Guelfand topology.

Consider the map $X\to \widehat{C_{0}(X)}, x\mapsto \text{ev}_{x}$. 
1. **Showing that the map is bijective**:
	We first find $\text{Max }C_{0}(X)$, the set of maximal regular proper ideals in $C_{0}(X)$. By Proposition 3.10, there exists a bijection $I:X\to \text{Max }C_{0}(X),x\mapsto I_{x}$, where: $$I_{x}:=\{ f\in C_{0}(X):f(x)=0 \}$$Further, by Theorem 3.15, there exists a bijection $J:\widehat{C_{0}(X)}\to\text{Max }C_{0}(X),\chi\mapsto \text{ker }\chi$. Then, we can factor the original map as: $$\begin{array}{cccccc} &{X}&\xrightarrow{I}&{\text{Max }C_{0}(X)}&\xrightarrow{J^{-1}}&{\widehat{C_{0}(X)}}\\&{x} &\mapsto & {I_{x}}&\mapsto&\text{ev}_{x} \end{array}{}$$as a bijective map.
2. **Showing that the map is a homeomorphism**:
	Firstly, by definition, for any $f\in C_{0}(X)$, $x\mapsto f(x)=\text{ev}_{x}(f)$ is continuous. Therefore, $x\mapsto \text{ev}_{x}$ is continuous in the weak*-topology and thereby the Guelfand topology. 
	
	Conversely, let $U\subseteq X$ be open. It suffices to show that $\{ \text{ev}_{x}: x\in U \}$ is open in Guelfand topology. Let $x\in U$. Then, there exists a compact neighborhood $K$ of $x$ s.t.  $K\subseteq U$. Then, by Urysohn's lemma, there exists a function $f\in C_{0}(X)$ s.t. $f(X)\subseteq[0,1]$, $f|_{K}=1$, especially $f(x)=1$ and $\text{supp }f\subseteq U$. Now, $$\begin{align}N(\text{ev}_{x},f,1)\cap \{ \text{ev}_{y}: y\in X \}&=\{ \text{ev}_{y}: y\in X,|f(x)-f(y)|<1 \}\\&=\{ \text{ev}_{y}: y\in X,|1-f(y)|<1 \}\\&\subseteq \{ \text{ev}_{y}: y\in U \}\end{align}$$This proves the statement.
---
> [!def] Problem 2
> Find an example of a commutative Banach algebra $A$ for which the Guelfand transform $A\to C_{0}(\widehat{A})$ is not surjective.
---
> [!def] Problem 3
> Consider the Banach algebra $A:=\ell^1(\mathbb{Z})$ with convolution product and $$B:=\{ f\in A:f(n)=0, \forall n<0 \}$$Show that $B$ is a unital subalgebra of $A$. Moreover, prove $\text{Sp}_{A}(\delta_{1})\subsetneq \text{Sp}_{B}(\delta_{1})$.

Firstly, let $f,g\in B$. Then, for $n<0$, $$(f*g)(n)=\sum_{m\in \mathbb{Z}}^{}f(n-m)g(m)=\sum_{m=0}^{\infty}\underbrace{ f(n-m) }_{ =0 }g(m)+\sum_{m=1}^{\infty}f(n+m)\underbrace{ g(-m) }_{ =0 }=0$$Therefore, $B$ is closed under convolution. Further, $\delta_{0}\in B$ is a unit as: $$(f*\delta_{0})(n)=\sum_{m\in \mathbb{Z}}^{}f(n-m)\delta_{0}(m)=f(n),\quad (\delta_{0}*f)(n)=\sum_{m\in \mathbb{Z}}^{}\delta_{0}(n-m)f(m)=f(n)$$Indeed $B$ is a unital subalgebra of $A$. 