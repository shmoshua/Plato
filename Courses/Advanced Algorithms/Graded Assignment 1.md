#Series #Algorithms 

##### 1. Covering Cliques
We define the following variables:
1. $z_{e}\in \{ 0,1 \}$ for $e\in E$ to denote whether $e\in F$.
2. $q_{e,i}\in \{ 0,1 \}$ for $e\in E$ and $i\in [\ell]$ to denote whether $e\in {V_{i} \choose 2}\cap F$.
3. $p\in \mathbb{Z}$ to denote the size $\left| F \right|$.

Then, $$\begin{align}\text{min}\quad &\sum_{e\in E}^{}z_{e}\\\text{subject to}\quad &\sum_{e\in {V_{i}\choose 2}\cap E}z_{e}\geq s&&\forall i\in [\ell]\\&z_{e}\in \{ 0,1 \}&&\forall e\in E\end{align}$$

Then, $$\begin{align}\text{min}\quad &p\\\text{subject to}\quad&\sum_{e\in E}^{}z_{e}\leq p\\&\sum_{e\in E}q_{e,i}\geq s&&\forall i\in [\ell]\\&q_{e,i}-z_{e}=0&&\forall i\in[\ell], e\in {V_{i} \choose 2}\cap E\\&q_{e,i}=0&&\forall i\in[\ell],e\notin {V_{i} \choose 2}\\&q_{e,i}\in \{ 0,1 \}&&\forall i\in [\ell],e\in E\\&z_{e}\in \{ 0,1 \}&&\forall e\in E\end{align}$$
.
---
Consider the relaxed LP version of the problem, i.e. $q_{e,i},z_{e}\in[0,1]$ for all $e\in E$, $i\in [\ell]$ and $k\in \mathbb{R}$. 

---
##### Approach 2 
Let $w:={k \choose 2}$ and $F:=\left\{  e\in E: z_{e}\geq \frac{1}{w-s+1}  \right\}$. Then, 
1. **Claim 1: $F$ is feasible.**
   Let $i\in[\ell]$  and assume that $\left| {V_{i} \choose 2}\cap F \right|=:p\leq s-1$.   Then, $$\sum_{e\in {V_{i} \choose 2}\cap E}^{}z_{e}<(s-1)\cdot 1+1=s$$which is a contradiction.

We have that: $$\mathbb{E}[\left| F \right| ]=\sum_{e\in F}^{}1\leq(w-s+1)\sum_{e\in F}^{}z_{e}=(w+1)p^{*}\leq$$
   

```pseudo
\begin{algorithm} \caption{FirstFit($\mathcal{S},s$)} 
\begin{algorithmic}
\State $\mathcal{B}\to \empty$
\end{algorithmic}
\end{algorithm}
```


---


##### Approach 1. 
Take $e\in F$ with probability $z_{e}$. Then, let $X_{i}:=\left| {V_{i}\choose 2}\cap F \right|$. We also define $n_{i}:= \left| {V_{i}\choose 2}\cap E \right|$. Then, We have that 
1. $\sum_{e\in E}^{}z_{e}=p$.
2. $p=\sum_{e\in E}^{}z_{e}\geq \sum_{e\in {V_{i} \choose 2}\cap E}^{}z_{e}=\mathbb{E}[X_{i}]$


$$\mathbb{E}[X_{i}]=\sum_{e\in {V_{i} \choose 2}\cap E}^{}\mathbb{P}(e\in F)=\sum_{e\in {V_{i} \choose 2}\cap E}^{}z_{e}\geq s$$

 $$\mathbb{P}(X_{i}\leq s-1)=\mathbb{P}(n_{i}-X_{i}\geq n_{i}-s-1 )\leq\frac{n_{i}-\mathbb{E}[X_{i}]}{n_{i}-s-1}\leq \frac{n_{i}-s}{n_{i}-s-1}$$

 $$\begin{align}\mathbb{P}(X_{i}<s)&=\mathbb{P}(X_{i}\leq s-1)\\&=\mathbb{P}\left( X_{i}\leq\left( 1-s ^{-1} \right)s \right)\\&\leq \mathbb{P}\left( X_{i}\leq \left( 1-s ^{-1} \right) \mathbb{E}[X_{i}] \right)\\&\leq \exp \left( -\frac{\mathbb{E}[X_{i}]}{2s^{2}} \right) \\&\leq \exp \left( -\frac{1}{2s} \right) \end{align}$$
 
Let $Y$ denote the number of $i\in[n]$ s.t. $X_{i}<s$. Then, $$\mathbb{E}[Y]=\sum_{i=1}^{\ell}\mathbb{P}(X_{i}<s)$$

Therefore, $$\mathbb{P}(\exists i\in [\ell]:X_{i}<s)\leq \sum_{i=1}^{\ell}\frac{m-\mathbb{E}[X_{i}]}{m-s-1}=\frac{m-\sum_{i=1}^{\ell}\sum_{e\in{V_{i} \choose 2}\cap E }^{}q_{e,i}}{m-s-1}$$

$$\mathbb{E}[\left| F \right|]=k^{*}\cdot \mathbb{P}(\forall i\in [\ell]:X_{i}\geq s)+$$
$$\left| G \right| =\left| F \right|+\sum_{i=1}^{\ell}\max \{ s-X_{i},0 \} $$Hence, $$\begin{align}\mathbb{E}[\left| G \right| ]&\leq \mathbb{E}[\left| F \right| ]+\sum_{i=1}^{\ell}\mathbb{E}[\text{max}\{ s-X_{i},0 \}]\\&=\mathbb{E}[\left| F \right| ]+\sum_{i=1}^{\ell}\sum_{d=1}^{s}d \cdot \mathbb{P}(X_{i}=s-d)\\&\leq p^{*}+s\sum_{i=1}^{\ell}\mathbb{P}(X_{i}< s)\\&\leq p^{*}+s\sum_{i=1}^{\ell}\frac{m-\mathbb{E}[X_{i}]}{m-s-1}\\&\leq p^{*}+s\frac{\ell m-\sum_{i=1}^{\ell}\mathbb{E}[X_{i}]}{m-s-1}\end{align}$$

$\mathbb{P}(X_{i}\cap X_{j})$ $$ s\sum_{e\in E}^{}z_{e}$$

