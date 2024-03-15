#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $X$ be a locally compact Hausdorff space. Show that the canonical map $$X\to \widehat{C_{0}(X)}$$is a homeomorphism while $\widehat{C_{0}(X)}$ is endowed with the Guelfand topology.

Consider the map $X\to \widehat{C_{0}(X)}, x\mapsto \text{ev}_{x}$. 
1. **Showing that the map is bijective**:
	We first find $\text{Max }C_{0}(X)$, the set of maximal regular proper ideals in $C_{0}(X)$. By Proposition 3.10, there exists a bijection $I:X\to \text{Max }C_{0}(X),x\mapsto I_{x}$, where: $$I_{x}:=\{ f\in C_{0}(X):f(x)=0 \}$$Further, by Theorem 3.15, there exists a bijection $J:\widehat{C_{0}(X)}\to\text{Max }C_{0}(X),\chi\mapsto \text{ker }\chi$. Then, we can factor the original map as: $$\begin{array}{cccccc} &{X}&\xrightarrow{I}&{\text{Max }C_{0}(X)}&\xrightarrow{J^{-1}}&{\widehat{C_{0}(X)}}\\&{x} &\mapsto & {I_{x}}&\mapsto&\text{ev}_{x} \end{array}{}$$as a bijective map.
2. **Showing that the map is a homeomorphism**:
	First, notice that $\text{Rad }C_{0}(X)=\bigcap_{x\in X}^{}I_{x}=(0)$. Therefore, $C_{0}(X)$ is semi-simple.