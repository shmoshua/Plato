#Series #Algorithms 

##### 1. Covering Cliques
We define the following variables:
1. $z_{e}\in \{ 0,1 \}$ for $e\in E$ to denote whether $e\in F$.
2. $y_{e,i}\in \{ 0,1 \}$ 
For $v\in V$ and $i\in [\ell]$, let $x_{v,i}\in \{ 0,1 \}$ denote the binary variable if $v\in V_{i}$. Similarly, for $v,w\in V$ and  let $y_{e,i}$. 

Let $z_{e}$ denote if $e$ is in $F$.  

Then, $$\begin{align}\text{min}\quad &k\\\text{subject to}\quad&\sum_{e\in E}^{}z_{e}\leq k\\&\sum_{e\in E}q_{e,i}\geq s&&\forall i\in [\ell]\\&q_{e,i}-z_{e}=0&&\forall i\in[\ell], e\in {V_{i} \choose 2}\cap E\\&q_{e,i}\end{align}$$


Then,$$\begin{align}\text{min}\quad &k\\\text{subject to}\quad&\sum_{n=1}^{}p_{e,\ell}\\&x_{v,i}+x_{w,i}-1\leq y_{e,i}\quad &\forall e:= \{ v,w \}\in E,i\in[\ell]\\&\sum_{e\in E}^{}z_{e}\leq k\\&\sum_{e\in E}^{}q_{e,i}\geq s\\&q_{e}\geq y_{e,i}+z_{e}-1\\&q_{e}\leq y_{e,i}\\&q_{e}\leq z_{e}\end{align}$$
