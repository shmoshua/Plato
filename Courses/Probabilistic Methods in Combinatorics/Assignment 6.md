#Series #ProbabilisticMethods 

##### Problem 1
![[Expected Value#^d75029]]
![[Expected Value#^36878b|p]]

---
##### Problem 2
1. Let $c$ be an arbitrary $k$-coloring where for every $i\in[k]$: $\mathbb{P}(c(v)=i)=1 / k$ independently for each vertex, i.e. uniform distribution on the set of $k^n$ possible colorings.
   
   Let $c$ be a coloring. We have that: $$\mathbb{P}(c \text{ is not proper})=\mathbb{P}(\exists \{ u,v \}\in E: c(u)=c(v))\leq \frac{m}{k}$$Therefore, $\mathbb{P}(c\text{ is proper})\geq (1-\frac{m}{k})$ and there are at least $k^n\left( 1-\frac{m}{k} \right)$ proper colorings. 
2. In the above setting, let $X_{e}$ denote the indicator variable that $e\in E$ is monochromatic. Then, $c$ is proper if and only if $X:=\sum_{e\in E}^{}X_{e}=0$. 
	1. We have that: $$\mathbb{E}[X]=\sum_{e\in E}^{}\mathbb{P}(e\text{ is monochromatic}) = \frac{m}{k}$$
	2. We have that: $$\begin{align}\mathbb{E}[X^{2}]&=\mathbb{E}\left[ \sum_{e\in E}^{} X_{e}+\sum_{(e,f):e \neq f}^{} X_{e}X_{f} \right] =\sum_{e\in E}^{} \frac{1}{k}+\sum_{(e,f):e \neq f} \frac{1}{k^{2}}\\&=\frac{m}{k}+\frac{m^{2}-m}{k^{2}}=\frac{m^{2}+mk-m}{k^{2}}\end{align}$$
	
	Therefore, $$\mathbb{P}(X=0)\leq \frac{\text{Var}(X)}{\mathbb{E}[X]^{2}}= \left( \frac{(k-1)m}{k^{2}} \right)\cdot  \frac{k^{2}}{m^{2}}=\frac{k-1}{m} $$This proves the statement.
3. We have from Problem 1: $$\mathbb{P}(X=0)\leq \frac{\text{Var}(X)}{\mathbb{E}[X^{2}]}=\left( \frac{(k-1)m}{k^{2}} \right) \cdot \frac{k^{2}}{m(m+k-1)}=\frac{k-1}{k+m-1}$$
---
