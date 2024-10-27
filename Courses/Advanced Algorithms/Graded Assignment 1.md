#Series #Algorithms 

#### 1. Covering Cliques

**Part 1**: We define $z_{e}\in \{ 0,1 \}$ for all $e\in E$ to denote whether $e\in F$. Then, 
$$
\begin{aligned}\text{min}\quad &\sum_{e\in E}^{}z_{e}\\\text{subject to}\quad &\sum_{e\in {V_{i}\choose 2}\cap E}z_{e}\geq s&&\forall i\in [\ell]\\&z_{e}\in \{ 0,1 \}&&\forall e\in E\end{aligned}
$$
describes the problem as an ILP problem.

---
**Part 2**  Let $q:={k \choose 2}$. In our algorithm, let $\{z_e^*\}_{e\in E}$ be the optimal solution given by solving the LP. Then, we construct $F:=\{e\in E: z_e^*\ge \frac{1}{q-s+1}  \}$. 

-  **Claim 1**:  $F$ is feasible, i.e. $\left| {V_{i} \choose 2}\cap F \right|\ge s$ for all $i\in [\ell]$.
  Assume otherwise, i.e. let $i\in[\ell]$ s.t. $\left| {V_{i} \choose 2}\cap F \right|\le s-1$. Then, $$\sum_{e\in {V_{i} \choose 2}\cap E}^{}z^*_{e}< (s-1)\cdot 1+\left(\left|{V_{i} \choose 2}\cap E\right|-s+1\right)\cdot \frac{1}{q-s+1}\le (s-1)+1=s$$which is a contradiction. 


Now, for all $e\in F$, we have that $(q-s+1)z^*_e\ge 1$. Hence, 

$$\mathbb{E}[\left| F \right| ]=\sum_{e\in F}^{}1\leq(q-s+1)\sum_{e\in F}z^*_{e}=(q-s+1)\cdot |F_\text{OPT}|\leq (q+1)\cdot |F_\text{OPT}|$$This shows that our algorithm is a $\text{O}(k^2)$-approximation in expectation. Further, as we have polynomially many constraints, this is a polynomial algorithm.

---
#### 2. Graph Coloring

We have $E_{R},E_{B},E_{V}$ as the edge sets. Let $R\sqcup B$ denote the vertex partition by color, i.e. the red and blue vertices. Let $S:=\{ v\in V:r_{v}\geq 1,b_{v}\geq 1 \}$
1. $\frac{\left| E \right|-\left| E_{V} \right|}{2}\leq\frac{\left| E_{R} \right|+\left| E_{B} \right|}{2}\leq\max \{ \left| E_{R} \right|,\left| E_{B} \right| \}\leq \text{OPT}\leq \left| E \right|-\frac{\left| S \right|}{2}$.
2. 

$$ \text{OPT}\leq \frac{1}{2}\sum_{v\in V}^{}d_{v}-\min\{ r_{v},b_{v} \}=\left| E \right| -\frac{1}{2}\sum_{v\in V}^{}\min\{ r_{v},b_{v} \}$$

For vertex $x$, let $r_{x},b_{x},\ell_{x}$ denote the number of red, blue and violet edges respectively. Then, for each color red with probability $\frac{r_{e}}{r_{x}+b_{x}}$. If $r_{x}=b_{x}=0$, then color it red with probability $1 /2$. 


1. For $\{ v,w \}\in E$ red, $\mathbb{P}(v\in R\land w\in R)=\frac{r_{v}}{r_{v}+b_{v}}\cdot\frac{r_{w}}{r_{w}+b_{w}}$
2. For $\{ v,w \}\in E$ blue, $\mathbb{P}(v\in B\land w\in B)=\frac{b_{v}}{r_{v}+b_{v}}\cdot\frac{b_{w}}{r_{w}+b_{w}}$
3. For $\{ v,w \}\in E$ violet, $\mathbb{P}(\text{point})=\frac{r_{v}}{r_{v}+b_{v}}\cdot\frac{b_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\cdot\frac{r_{w}}{r_{w}+b_{w}}$

We have:
1. $T:=\{ v\in V: r_{v}=b_{v}=0 \}$
2. $S_{B}:=\{ v\in V: r_{v}=0 \land b_{v}\geq1\}$
3. $S_{R}:=\{ v\in V: r_{v}\geq 1 \land b_{v}=0\}$
4. $U:=\{ v\in V:r_{v},b_{v}\geq 1 \}$

$$2\cdot \mathbb{E}[X]=\sum_{v\in V}^{}\mathbb{E}[X_{v}]=\sum_{v\in T}^{}\mathbb{E}[X_{v}]+\sum_{v\in S}^{}\mathbb{E}[X_{v}]+\sum_{v\in U}^{}\mathbb{E}[X_{v}]$$

For $v\in T$, $$\mathbb{E}[X_{v}]=\frac{1}{2}\sum_{w:\{ v,w \}\in E_{V}}^{}1=\frac{\left| E_{V,N(v)} \right|}{2} $$
For $v\in S_{R},S_{B}$, $$\mathbb{E}[X_{v}]=\sum_{w\in E_{R,N(v)} \backslash T}^{}\frac{r_{w}}{r_{w}+b_{w}}+\sum_{w\in E_{V, N(v)} \backslash T}^{} \frac{b_{w}}{r_{w}+b_{w}}+\frac{\left| N(v)\cap T \right| }{2}$$$$\mathbb{E}[X_{v}]=\sum_{w\in E_{B,N(v)} \backslash T}^{}\frac{b_{w}}{r_{w}+b_{w}}+\sum_{w\in E_{V, N(v)} \backslash T}^{} \frac{r_{w}}{r_{w}+b_{w}}+\frac{\left| N(v)\cap T \right| }{2}$$
For $v\in U$, $$\mathbb{E}[X_{v}]=p_{v}\sum_{w\in E_{R,N(v)} \backslash T}^{}\frac{r_{w}}{r_{w}+b_{w}}$$

Then, let $X$ be the number of points. We have that:
$$\begin{align}\mathbb{E}[X]&=\sum_{\{ v,w \}\in E_{R}}^{}\frac{r_{v}}{r_{v}+b_{v}}\cdot \frac{r_{w}}{r_{w}+b_{w}}+\sum_{\{ v,w \}\in E_{B}}^{}\frac{b_{v}}{r_{v}+b_{v}}\cdot \frac{b_{w}}{r_{w}+b_{w}}+\sum_{\{ v,w \}\in E_{V}}^{}\frac{r_{v}}{r_{v}+b_{v}}\cdot \frac{b_{w}}{r_{w}+b_{w}}+\sum_{\{ v,w \}\in E_{V}}^{}\frac{b_{v}}{r_{v}+b_{v}}\cdot \frac{r_{w}}{r_{w}+b_{w}}\\&\leq\end{align}$$

For each edge $v$, $$\begin{align}\mathbb{E}[X_{v}]&=\frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{}\frac{r_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{B}}^{}\frac{b_{w}}{r_{w}+b_{w}}+\frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{V}}^{}\frac{b_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{V}}^{}\frac{r_{w}}{r_{w}+b_{w}}\\&\leq\frac{r_{v}^{2}}{r_{v}+b_{v}}+\frac{b ^{2}_{v}}{r_{v}+b_{v}}+\frac{r_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}}+\frac{b_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}}\\&=\frac{r_{v}d(v)-r_{v}b_{v}+b_{v}d(v)-r_{v}b_{v}}{r_{v}+b_{v}}\\&=d(v)-\frac{2r_{v}b_{v}}{r_{v}+b_{v}}\end{align}$$
 Then, $$\mathbb{E}[X]=\frac{1}{2}\sum_{v\in V}^{}\mathbb{E}[X_{v}]=\left| E \right| -\sum_{v\in S}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}\geq \text{OPT}+\frac{\left| S \right|}{2}-\sum_{v\in S}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}$$
The optimum 

$$\sum_{v\in V}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}\leq \frac{2}{3}\text{OPT}$$

$\frac{a}{b}\leq \frac{a+c}{b+c}$ because $ab+ac\leq ab+bc$ if $a\leq b$

$$\frac{r_{v}b_{v}}{r_{v}+b_{v}}\leq\frac{\left( \frac{r_{v}+b_{v}}{2} \right)^{2}}{r_{v}+b_{v}}=\frac{r_{v}+b_{v}}{4}$$Therefore,  $$\text{OPT}\geq \frac{\left| E _{R}\right| +\left| E_{B} \right| }{2}=\frac{\sum_{v\in V}^{}r_{v}+b_{v}}{4}\geq \sum_{v\in V}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}$$

---
We have:
1. If $$\begin{align}\mathbb{E}[X_{v,R}]&= \frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{}\frac{r_{w}}{r_{w}+b_{w}}\geq \frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{} \frac{1}{\max\{ b_{w},1 \}}\\&\geq \frac{r_{v}^{2}}{r_{v}+b_{v}} \frac{1}{b_{N(v)}}\end{align}$$ $$\begin{align}\mathbb{E}[X]&\geq\frac{r_{v}^{2}}{r_{v}+b_{v}} \frac{1}{b_{N(v)}}+\frac{b_{v}^{2}}{r_{v}+b_{v}} \frac{1}{r_{N(v)}}+\frac{r_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}} \frac{1}{r_{N(v)}}+\frac{b_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}} \frac{1}{b_{N(v)}}\\&=\frac{1}{r_{v}+b_{v}}\left( \frac{1}{b_{N(v)}}(r^2_{v}+b_{v}d(v)-r_{v}b_{v}-b_{v}^{2})+\frac{1}{r_{N(v)}}(b^2_{v}+r_{v}d(v)-r_{v}b_{v}-r_{v}^{2}) \right) \end{align}$$
---
##### Approch 2 (LP)
Consider the following ILP: $$\begin{align}\text{max}\quad&\sum_{e\in E}^{}x_{e}\\\text{subject to}\quad&x_{e}\leq r_{v},x_{e}\leq r_{w}&& \forall \{ v,w \}\in E_{R}\\&x_{e}\leq 1-r_{v},x_{e}\leq 1-r_{w}&& \forall \{ v,w \}\in E_{B}\\&x_{e}\leq r_{v}+r_{w},x_{e}\leq 2- r_{v}-r_{w}&& \forall \{ v,w \}\in E_{V}\\&\sum_{e\in N(v)}^{}x_{e}\leq\max \{ \left| N_{R}(v),N_{B}(v) \right|  \}+\left| N_{V}(v) \right| &&\forall v\in V\\&\sum_{e\in N(v)}^{}x_{e}\leq \left| N(v) \right| -\min\{ \left| N_{R}(v) \right| ,\left| N_{B}(v) \right|  \} &&\forall v\in V\end{align}$$

Now, color the vertex red with probability $r_{v}$. Then,
1. For $e=\{ v,w \}\in E_{R}$, $\mathbb{P}(e\text{ no point})=\mathbb{P}(v\in B \lor w\in B)\leq(1-r_{v})+(1-r_{w})$
2. For $e=\{ v,w \}\in E_{B}$, $\mathbb{P}(e\text{ no point})=\mathbb{P}(v\in R \lor w\in R)\leq r_{v}+r_{w}$
3. For $e=\{ v,w \}\in E_{V}$, $\mathbb{P}(e\text{ no point})=r_{v}r_{w}+(1-r_{v})(1-r_{w})$

Then, let $X$ be the number of edges that did not get a point. We have: $$\begin{align}\mathbb{E}[X]&\leq\sum_{\{ v,w \}\in E_{R}}^{}(1-r_{v})+(1-r_{w})+\sum_{\{ v,w \}\in E_{B}}^{}r_{v}+r_{w}+\sum_{\{ v,w \}\in E_{V}}^{}r_{v}r_{w}+(1-r_{v})(1-r_{w})\\&\leq\sum_{\{ v,w \}\in E_{R}}^{}2(1-x_{e}) +\sum_{\{ v,w \}\in E_{B}}^{}2(1-x_{e})+\sum_{\{ v,w \}\in E_{V}}1-r_{v}-r_{w}+2r_{v}r_{w}\\&\leq\sum_{\{ v,w \}\in E_{R}}^{}2(1-x_{e}) +\sum_{\{ v,w \}\in E_{B}}^{}2(1-x_{e})+\sum_{\{ v,w \}\in E_{V}}1-x_{e}+2r_{v}r_{w}\\&=2\sum_{e\in E}^{}1-x_{e}+\sum_{\{ v,w \}\in E_{V}}^{}x_{e}-1+2r_{v}r_{w}\\&=2\left| E \right| -2p+\sum_{\{ v,w \}\in E_{V}}^{}x_{e}-1+2r_{v}r_{w}\\&\end{align}$$

Then, $$\mathbb{P}\left( \left| E \right| -X< \frac{1}{3}\text{OPT} \right)=\mathbb{P}\left( X>\left| E \right| -\frac{1}{3}\text{OPT} \right)\leq\mathbb{P}\left( X>\left| E \right| -\frac{1}{3}p \right) \leq \frac{2\left| E \right| -2p+\left| E_{V} \right| }{\left| E \right| -\frac{1}{3}p} $$


Hence, $\mathbb{E}[\text{\#points}]=\left| E \right|-\mathbb{E}[X]\geq 2\text{OPT}-\left| E \right|-2\left| E_{V} \right|$ 

---
We have that: let $m_{v}:=\max\{ \left| N_{R}(v) \right|,\left| N_{B}(v) \right| \}$

$$r_{v}+r_{w}\leq 2-x_{e}\implies r_{v}^{2}+2r_{v}r_{w}+r_{w}^{2}\leq 4-4x_{e}+x_{e}^{2}$$ $$\sum_{\{ v,w \}\in E_{V}}^{}1-x_{e}+4-4x_{e}+x_{e}^{2}-r_{v}^{2}-r_{w}^{2}\leq\sum_{\{ v,w \}\in E_{V}}^{}5-4x_{e}$$
- $\text{OPT}\leq \frac{1}{2}\sum_{v\in V}^{}\max\{ N_{R}(v), N_{B}(v) \}+N_{V}(v)=\frac{1}{2}\sum_{v\in V}^{}\max\{ N_{R}(v), N_{B}(v) \}+\frac{\left| E_{V} \right|}{2}$
$$\begin{align}\mathbb{E}[X_{v}]&\leq \sum_{w\in N_{R}(v)}^{}(1-r_{v})+(1-r_{w})+\sum_{w\in N_{B}(v)}^{}r_{v}+r_{w}+\sum_{w\in N_{V}(v)}^{}r_{v}r_{w}+(1-r_{v})(1-r_{w})\\&\leq(1-r_{v})\left| N_{R}(v) \right| +r_{v}\left| N_{B}(v) \right|+\sum_{e\in N(v)}^{}(1-x_{e})+2\sum_{w\in N_{V}(v)}^{}r_{v}r_{w} \\&\leq \left| N_{R}(v) \right|+r_{v}(\left| N_{B}(v) \right|-\left| N_{R}(v) \right|+2\left| N_{V}(v) \right| ) +\sum_{e\in N(v)}^{}(1-x_{e})\end{align}$$and $$\begin{align}\mathbb{E}[X]=\frac{1}{2}\mathbb{E}[X_{v}]\leq \left| E_{R} \right| +\left| E \right| -p+\end{align}$$
---
We know that: 
1. $\frac{\left| E \right|-\left| E_{V} \right|}{2}\leq\frac{\left| E_{R} \right|+\left| E_{B} \right|}{2}\leq\max \{ \left| E_{R} \right|,\left| E_{B} \right| \}\leq \text{OPT}\leq \left| E \right|-\frac{\left| S \right|}{2}$.
2. 

$$ \text{OPT}\leq \frac{1}{2}\sum_{v\in V}^{}d_{v}-\min\{ r_{v},b_{v} \}=\left| E \right| -\frac{1}{2}\sum_{v\in V}^{}\min\{ r_{v},b_{v} \}$$


---
$$\begin{align}\mathbb{E}[X]&=\sum_{e\in E_{R}}^{}r_{v}r_{w}+\sum_{e\in E_{B}}^{}(1-r_{v})(1-r_{w})+\sum_{e\in E_{V}}r_{v}(1-r_{w})+r_{w}(1-r_{v})\\&= \sum_{e\in E_{R}}^{}r_{v}r_{w}+\sum_{e\in E_{B}}^{}(1-r_{v}-r_{w}+r_{v}r_{w})+\sum_{e\in E_{V}}^{}(r_{v}+r_{w}-2r_{v}r_{w})\end{align}$$

For $$\begin{align}\mathbb{E}[X_{v}]&=r_{v}\sum_{w\in E_{R}}^{}r_{w}+(1-r_{v})\sum_{w\in E_{B}}^{}(1-r_{w})+r_{v}\sum_{w\in E_{V}}^{}(1-r_{w})+(1-r_{v})\sum_{w\in E_{V}}^{}r_{w}\\&\geq r_{v}\sum_{w\in E_{R}}^{}r_{w}+(1-r_{v})\sum_{w\in E_{B}}^{}(1-r_{w})+r_{v}\sum_{e\in E_{V}}^{}(x_{e}-1+r_{v})+(1-r_{v})\sum_{e\in E_{V}}^{}(x_{e}-r_{v})\\&\geq r_{v}\sum_{e\in E_{R}}^{}x_{e}+(1-r_{v})\sum_{e\in E_{B}}^{}x_{e}+\sum_{e\in E_{V}}^{}x_{e}+(2r_{v}^{2}-2r_{v})\left| N_{V}(v) \right| \end{align}$$Then, 

$$\begin{align}\mathbb{E}[X_{v}]&=\sum_{w\in E_{R}}^{}(1-\max(r_{v},r_{w}))+\sum_{w\in E_{B}}^{}\min(r_{v},r_{w})+\sum_{w\in E_{V}}^{}\max(r_{v},r_{w})-\min(r_{v},r_{w})\\&= \end{align}$$

---
##### Approach 3
Consider the following ILP: $$\begin{align}\text{max}\quad&\sum_{e\in E \backslash E_{V}}^{}x_{e}+\sum_{e\in E_{V}}^{}y_{e}+z_{e}\\\text{subject to}\quad&x_{e}\leq r_{v}+r_{w}-1&& \forall \{ v,w \}\in E_{R}\\&x_{e}\leq 1-r_{v}-r_{w}&& \forall \{ v,w \}\in E_{B}\\&y_{e}\leq r_{v}-r_{w},z_{e}\leq r_{w}-r_{v}&& \forall \{ v,w \}\in E_{V}\\&r_{v}\in \{0,1 \}&&\forall v\in V\\&x_{e}\in \{-1, 0,1 \}&&\forall e\in E\\&y_{e},z_{e}\in \{ -1,0,1 \}&&\forall e\in E_{V}\end{align}$$

Now, color the vertex red with probability $r_{v}$. Then,
1. For $e=\{ v,w \}\in E_{R}$, $\mathbb{P}(e\text{ no point})=(1-r_{w})+(1-r_{v})r_{w}$
2. For $e=\{ v,w \}\in E_{B}$, $\mathbb{P}(e\text{ no point})=r_{v}+r_{w}(1-r_{v})$
3. For $e=\{ v,w \}\in E_{V}$, $\mathbb{P}(e\text{ no point})=r_{v}r_{w}+(1-r_{v})(1-r_{w})$

Then, let $X$ be the number of edges that did not get a point. We have: $$\begin{align}\mathbb{E}[X]&\leq\sum_{\{ v,w \}\in E_{R}}^{}(1-r_{v})+(1-r_{w})+\sum_{\{ v,w \}\in E_{B}}^{}r_{v}+r_{w}+\sum_{\{ v,w \}\in E_{V}}^{}r_{v}r_{w}+(1-r_{v})(1-r_{w})\\&\leq\sum_{\{ v,w \}\in E_{R}}^{}(1-x_{e}) +\sum_{\{ v,w \}\in E_{B}}^{}(1-x_{e})+\sum_{\{ v,w \}\in E_{V}}1-y_{e}-z_{e}\\&=\left| E \right| -p\end{align}$$
Therefore, $$\mathbb{P}\left( \left| E \right| -X< \frac{1}{3}\text{OPT} \right)=\mathbb{P}\left( X>\left| E \right| -\frac{1}{3}\text{OPT} \right)\leq\mathbb{P}\left( X>\left| E \right| -\frac{1}{3}p \right) \leq \frac{\left| E \right| -p}{\left| E \right| -\frac{1}{3}p}=1-\frac{2p}{3\left| E \right| -p} $$ 



---
#### 3. Item Distribution

We denote an item distribution with a vector $\varphi:V\to I\cup \{ {\bot} \}$ where $\varphi_{v}$ denotes the item assigned to $v\in V$ and ${\bot}$ if no item has been assigned to $v$. Then, we can use $\|\varphi\|_{0}$ to denote the number of vertices with an item. 
1. We have:
	1. For any tree, there exists at least a leaf $v\in V$ and $T \backslash\{ v \}$ is also a tree. Hence, we can define an ordering on the vertices $v_{1},\dots,v_{n}$ s.t. the induced subgraph $T_{i}:=T[v_{1},\dots,v_{i}]$ is a tree and $v_{i}$ is a leaf in $T_{i}$. 
	   
	   Let $w_{1},\dots,w_{k}$ be the $k$ different weights. Then, $I$ can be represented using a $k$-tuple $(\ell_{1},\dots,\ell_{k})\in \mathbb{N}^k$ where $\ell_{j}:=\left| \{ i\in I: \text{size}(i)=w_{j} \}\right|$. 
	   
	   ```pseudo
		\begin{algorithm} \caption{ExactItemDist($T,I,\text{size},h$)} 
		\begin{algorithmic}
		\State Compute $(\ell_1,...,\ell_k)$ from $I$. 
		\State $v\gets$ a leaf in $T$
		\For{$i\in I$}
		\State $\varphi\gets $ \Call{ExactItemDist}{$T\backslash \{v\},I\backslash \{i\}, \text{size},h$}
        \EndFor
		\end{algorithmic}
		\end{algorithm}
		```
	   
	   Then, we define a dynamic programming algorithm. Firstly, let $$D[(\ell_{1},\dots,\ell_{k}),i,h]=\max_{}$$

2. 

---
First remember that a tree is bipartite. Hence, 

Let $v_{1},\dots,v_{n}$ be the order.
We define a DP table as follows:
1. $\text{DP}[j,\ell,v,s,q]:=$ maximum number of assigned items from $\ell$ on $T[v_{1},\dots,v_{j}]$ s.t. $\sum_{w\in N(v)}^{}\text{size}(w)\leq s$ with $v$ has item $q$.

We have that:
Let $v_{j}$ and $u\in \{ v_{1},\dots,v_{j-1} \}$ be the only neighbor of $v_{j}$ in $T_{j}$. Then, 

$$\text{DP}[j,\ell,v_{j},s,q]=\begin{cases}\text{DP}[j-1,\ell,u,h-q,]\end{cases}$$
 $$\text{DP}[j,\ell,u,s]=\max_{k: \ell_{p}\geq 1}\text{DP}[j-1,\ell-1,u,s-s_{p}]+1,\text{DP}[j-1,\ell,u,s]$$

---
Let C1,...,C_n be different configurations. 

---


Easy to check if $\text{OPT}(\mathcal{I})=0$. 


```pseudo
\begin{algorithm} \caption{PTASItemDist($T,I,\text{size},h,\varepsilon$)} 
\begin{algorithmic}
\State $\varepsilon \gets \min\{\varepsilon,1/2\}$
\State $L\gets \lceil 1/  \varepsilon^2\rceil$
\State $m\gets |I|$
\State Sort the items into increasing order: $i_1,...,i_m$
\State $T\gets \lceil \log m / \log (1 / \varepsilon)\rceil-2$
\State $p_0\gets$ \Call{ExactItemDist}{$T,\{i_1,...,i_{\min\{m,L\}}\},\text{size}|_{\{i_1,...,i_{\min\{m,L\}}\}},h$}
\If{$p_0<L$}
\Return $p_0$
\EndIf
\For{$t\in[T]$}
\State $I_t\gets\{i_1,...,i_{\lceil m \varepsilon^{t-1}\rceil}\}$, i.e. the $\lceil m \varepsilon^{t-1}\rceil$ smallest items in $I$.
\State Partition $I_t$ into $L+1$ groups $G_1,...,G_{L+1}$ in increasing order with $\lfloor m\varepsilon^{t+1}\rfloor$ elements  each except the last group.

\For{$j\in[L+1]$}
\State $s\gets \max_{i\in G_j}\text{size}(i)$
\For{$i\in G_j$}
\State $\text{size}^t(i)\gets s$
\EndFor
\EndFor
\State $p_t\gets$ \Call{ExactItemDist}{$T,I^t,\text{size}^t,h$}
\EndFor

\Return $\max_{0\le t\le T}p_t$
\end{algorithmic}
\end{algorithm}
```

Let $\mathcal{\mathcal{I}}$ denote the original problem instance and $\mathcal{I}^t$ denote the problem with only $I^t$ as items. Lastly, let $\mathcal{J}^t$ be the problem instance with rounded item sizes, i.e. with $I^t$ and $\text{size}^t$. For the rest of the analysis we assume that $\varepsilon\leq \frac{1}{2}$. 
1. **Claim 1: For $x\in \mathbb{N}$ with $\text{OPT}(\mathcal{I})\leq x$, there exists an optimal item distribution only on $i_{1},\dots,i_{x}$, i.e. there exists an item distribution $\varphi:V\to I'$ with $\text{im}(\varphi)\subseteq \{ {\bot},i_{1},\dots,i_{x} \}$ and $\left\| \varphi \right\|=\text{OPT}(\mathcal{I})$**
   
   Let $\psi$ be an optimal item distribution. We can always swap an item with an item of a smaller size and get a feasible optimum. Therefore, there exists an optimum using only the smallest items possible.

Firstly, note that this algorithm runs in polynomial time. It calls 

Let's consider the following two cases:
1. If $\text{OPT}(\mathcal{I})< L$. Then, by claim 1, there exists an optimal distribution only using $i_{1},\dots,i_{L}$. Therefore, $p_{0}=\text{OPT}(\mathcal{I})<L$ and $\mathcal{A}(\mathcal{I})=p_{0}=\text{OPT}(\mathcal{I})$.
2. if $\text{OPT}(\mathcal{I})\geq L$, then as $m\varepsilon^T\leq m\varepsilon^{\log m / \log(1 / \varepsilon)}/\varepsilon^{2}\leq \varepsilon^{-2}\leq L$, there exists $t\in [T]$ s.t. $m\varepsilon^t<\text{OPT}(\mathcal{I})\leq m\varepsilon^{t-1}$. Then, by Claim 1, we have that $\text{OPT}(\mathcal{I})=\text{OPT}(\mathcal{I}^t)$. 
   
   Let $G_{1},\dots,G_{L+1}$ be the partition of $I_{t}$ where $\left| I_{t} \right|< m\varepsilon^{t-1}+1$. Further, assume we have an optimal distribution on $\mathcal{I}_{t}$. Then, we can create a new item distribution on $\mathcal{J}$ by replacing each item in $G_{j}$ by one from $G_{j-1}$. This is still feasible as we are only reducing the sizes of the items, i.e. the item size of any element in $G_{j}$ is lower bounded by the rounded size of any element in $G_{j-1}$. As $\left| G_{j} \right|\leq \left| G_{j-1} \right|$ for all $j$, we only lose at most $\left| G_{1} \right|$ items as there aren't other items to replace items in $G_{1}$ with. Therefore, $$p_{t}=\text{OPT}(\mathcal{J}_{t})=\text{OPT}(\mathcal{I}_{t})- m\varepsilon^{t+1}=\text{OPT}(\mathcal{I})- m\varepsilon^{t+1}>(1-\varepsilon)\text{OPT}(\mathcal{I})$$as $m\varepsilon^t<\text{OPT}(\mathcal{I})$. It follows that we have $\mathcal{A}(\mathcal{I})\geq p_{t}\geq (1-\varepsilon)\text{OPT}(\mathcal{I})$.
---
### 4. Ski Rental

Let $\mathcal{A}$ be a deterministic algorithm. The adversary works as follows:

1. Give ski until the algorithm buys the skis.
2. Then, give snowboard until the algorithm buys the snowboard.
3. Stops the input when the algorithm buys both the skis and the snowboard at once.

Analysis!
1. Case 1: $\mathcal{A}$ didn't buy in bundle, doesn't buy the skis.
	$c_{\mathcal{A}}\geq 2X$ and $c_{\text{OPT}}=X$. Therefore,
2. Case 2: $\mathcal{A}$ didn't buy in bundle, bought the ski after $a$ days but doesn't buy the board.
	$c_{\mathcal{A}}=a-1+X+2X-a$ and $c_{\text{OPT}}=Y$
1. Case 3: $\mathcal{A}$ didn't buy in bundle, bought the ski after $a$ days and board after $b$ days. 
   Then, the cost of the algorithm is: $$c_{\mathcal{A}}=a+b+2X-2$$whereas $c_{\text{OPT}}=\min\{a,X\}+\min\{b,X\}$
		Hence,
	1.  if $a< X,b<X$, then $c_{\mathcal{A}}=a+b+2X-2\geq 2(a+b)= (1+\lambda)(a+b)$
	2. if $a<X, b\geq X$, then $c_{\mathcal{A}}=a+b+2X-2\geq 2(a+X)-1$
	3. if $a\geq X, b< X$, then $c_{\mathcal{A}}=a+b+2X-2\geq 2(b+X)-1$
	4. if $a\geq X,b\geq X$, then $c_{\mathcal{A}}=a+b+2X-2\ge 2Y$
2. Case 2: $\mathcal{A}$ buys the bundle after $a$ ski days.
	$$c_{\mathcal{A}}=a-1+Y\geq 2\cdot \min\{a,X\}$$

Let $a$ days for ski then $b$ for snowboard. Then, we have:
1. $a<X,b<X$ then $c_{\text{OPT}}=\min\{a+b,Y\}$
3. $a\geq X,b<X$ then $c_{\text{OPT}}=\min\{b+X,Y\}$
4. $a<X,b\geq X$ then $c_{\text{OPT}}=\min\{a+X,Y\}$
5. $a\geq X,b\geq X$ then $c_{\text{OPT}}=Y$


Let $Y=(1+\sqrt{ 2 })X$. Then, $\min(1+\sqrt{ 2 },)$
$\min \left( \frac{Y}{X}, \frac{2X}{Y} \right)$. 

$$\frac{2X}{1+\sqrt{ 2 }}=-2(1-\sqrt{ 2 })=2\sqrt{ 2 }-2$$

Let $X=1$ and $Y=1+\sqrt{ 2 }$. 
1. $a<X,b<X$ then 

---
Let $\mathcal{A}$ be a deterministic algorithm. We construct the following pseudocode for the adversary:


```pseudo
\begin{algorithm} \caption{RentalAdversary($\mathcal{A}$)} 
\begin{algorithmic}
\State Send $X,Y$ as input.
\State $k\gets 1$
\While {$\mathcal{A}$ hasn't bought skis and $k\le 2X$}
\State $\sigma_k\gets $ skis
\State Send $\sigma_k$ as input for $\mathcal{A}$.
\State $k\gets k+1$
\EndWhile
\State $k\gets 1$
\While {$\mathcal{A}$ hasn't bought a snowboard and $k\le 2X$}
\State $\sigma_k\gets $ snowboard
\State Send $\sigma_k$ as input for $\mathcal{A}$.
\State $k\gets k+1$
\EndWhile
\end{algorithmic}
\end{algorithm}
```


Let $\sigma:=(\sigma_{1},\dots,\sigma_{n})$ where $n\leq 4X$. We claim that $\text{cost}_{\mathcal{A}}(\sigma)\geq (1+\sqrt{ 2 })\text{cost}_{\text{OPT}}(\sigma)$. We can denote the two different while loops above as two phases. Let $a,b\leq 2X$ denote the number of iterations of each phase. 

1. If $\mathcal{A}$ bought in bundle in phase 1:
   Then, $b=0$ and $\text{cost}_{\mathcal{A}}(\sigma)=a-1+Y$. It is impossible for the algorithm to buy $X$ and $Y$. $$\text{cost}_{\mathcal{A}}(\sigma)=$$
2. If $\mathcal{A}$ bought in bundle in phase 2:
	Then, $\text{cost}_{\mathcal{A}}(\sigma)\geq \min\{2X, a-1+X\}+b-1+Y\geq \min\{2X, a-1+X\}+b-1+X$
3. If $\mathcal{\mathcal{A}}$ doesn't buy in bundle: $$\text{cost}_{\mathcal{A}}(\sigma)\geq\min\{2X,a-1+X\}+\min\{2X,b-1+X\}$$
Notice if $\mathcal{A}$ bought the skis and the snowboard in bundle in phase 2, the cost will always be lower bounded by buying the 
Then, we have:

1. $\mathcal{A}$ buys the bundle in phase 1. 
	1. $\text{cost}_{\mathcal{A}}(\sigma)=a-1+Y$ and optimal cost $\min\{a,X\}$.
		$$\begin{align}\text{cost}_{\mathcal{A}}(\sigma)&=a-1+Y\geq2\cdot \min\{a,Y\}-1\geq 2\cdot \min\{a,X\}-1\\&=\left( 2-\frac{1}{\min \{a,X\}} \right)\min\{a,X\}\\&\geq \left( 2-\frac{1}{Y} \right) \end{align}$$
2. $\mathcal{A}$ doesn't buy the bundle. Then, $\text{cost}_{\mathcal{A}}(\sigma)=a+b+2X-2$ and:
	1. if $a<X,b<X$, the optimal cost is $\min\{a+b,Y\}$
	2. if $a<X,b\geq X$, the optimal cost is $\min\{a+X,Y\}$
	3. if $a\geq X,b<X$, the optimal cost is $\min\{b+X,Y\}$
	4. if $a\geq X,b\geq X$, the optimal cost is $Y$.

$\left( 1-\frac{1}{Y} \right)=\sqrt{ 2 }$

where $\min\left( 1+a,1+\frac{2}{a} \right)$

---
Let $\varepsilon>0$ and choose $X\in \mathbb{N}$ s.t. $\frac{1}{X}<\varepsilon$. Let $Y:= \sqrt{ 2 }\cdot X$. We show that $\mathcal{A}$ is not $(1+\sqrt{ 2 }-\varepsilon)$-competitive. 

Let $a$ be the number of days $\mathcal{A}$ rents skis and $b$ Then,
1. if $a<2X$,
	1. if $\mathcal{A}$ buys only skis, then let $b$ be the number of days $\mathcal{A}$ rents board. Then, 
		1. if $b=2X$ then  $$\frac{\text{cost}_{\mathcal{A}}(\sigma)}{\text{cost}_{\text{OPT}}(\sigma)}=\frac{a+3X}{\min\{a+1,Y\}}\geq 2-\frac{1}{Y}$$
	2. if $\mathcal{A}$ buys in bundle: $$\frac{\text{cost}_{\mathcal{A}}(\sigma)}{\text{cost}_{\text{OPT}}(\sigma)}=\frac{a+Y}{\min\{a+1,X\}}\geq 2-\frac{1}{Y}$$
	3. if $\mathcal{A}$ buys 
2. $a=T$. 
3. 