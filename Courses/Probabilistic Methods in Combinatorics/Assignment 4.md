#Series #ProbabilisticMethods 

##### Problem 1
Let $\varepsilon_{n}$ be uniformly randomly chosen between $\{ +1,-1 \}$. Let $X:=\| \sum_{i=1}^{n}\varepsilon_{i}v_{i} \|^2_{2}$. Further, let $v_{ij}$ denote the $j$-th element of $v_{i}$. Then, $X=\sum_{j=1}^{n}\left( \sum_{i=1}^{n}\varepsilon_{i}v_{ij} \right) ^{2}$ and $$\mathbb{E}[X]=\sum_{j=1}^{n}\sum_{i,i'=1}^{n}\mathbb{E}[\varepsilon_{i}\varepsilon_{i'}]v_{ij}v_{i'j}=\sum_{j=1}^{n}\sum_{i=1}^{n}v_{ij}^2=\sum_{i=1}^{n}\left\| v_{i} \right\| ^{2}_{2}=n$$where for $i\neq i'$, $\mathbb{E}[\varepsilon_{i}\varepsilon_{i'}]=\mathbb{E}[\varepsilon_{i}]\mathbb{E}[\varepsilon_{i'}]=0$. Hence, there exists $\varepsilon_{1},\dots,\varepsilon_{n}$ s.t. $X\leq n$, i.e. $\sqrt{ X }\leq \sqrt{ n }$.

---