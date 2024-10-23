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

```pseudo
\begin{algorithm} \caption{PTASItemDist($T,I,\text{size},h$)} 
\begin{algorithmic}
\State $L\gets $
\For{$i\in I$}
\State $\text{size}'(i)\gets \lceil \text{size}(i)\cdot L/h\rceil$
\EndFor
\Return \Call{ExactItemDist}{$T,I,\text{size}',L$}
\end{algorithmic}
\end{algorithm}
```

Then, let $\varphi$ be the item distribution given by the algorithm. We have:
1. **Claim 1: $\varphi$ is feasible.**
   Note that for any item $i\in I$, $\text{size}(i)\leq \text{size}'(i)\cdot h / L$. Therefore,  $$\sum_{w\in N(v)}^{}\text{size}(\varphi_{w})\leq \frac{h}{L}\sum_{w\in N(v)}^{}\text{size}'(\varphi_{w})\leq \frac{h}{L}\cdot L=h,\quad \forall v\in V$$
2. **Claim 2:** 
   Let $\psi$ be the optimal distribution of $\mathcal{I}$. Then, $$\left\| \varphi \right\| \geq$$

---
Case 1:

```pseudo
\begin{algorithm} \caption{PTASItemDist($T,I,\text{size},h$)} 
\begin{algorithmic}
\State $L\gets \lceil 1/  \varepsilon\rceil$
\State Sort the items into increasing order: $i_1,...,i_m$
\State $q\gets\lfloor m / L^2\rfloor$
\State $r\gets m-qL^2$
\For{$j\in [L^2]$}
\If{$j\le r$}
\State $G_j\gets $ first $q+1$ items from $I \backslash \bigcup_{\ell=1}^{j-1} G_\ell$
\Else 
\State $G_j\gets $ first $q$ items from $I \backslash \bigcup_{\ell=1}^{j-1} G_\ell$
\EndIf


\State $s\gets \max_{i\in G_j}\text{size}(i)$
\For{$i\in G_j$}
\State $\text{size}'(i)\gets s$
\EndFor
\EndFor
\Return \Call{ExactItemDist}{$T,I,\text{size}',L$}
\end{algorithmic}
\end{algorithm}
```
We have:
1. Claim 1: $\text{OPT}(\mathcal{J})\geq \text{OPT}(\mathcal{I})-q-1$
   Let $\varphi:V\to I\cup \{ \bot \}$ be the optimal distribution on $\mathcal{I}$ where $\varphi(v)=\bot$ means no item has been assigned. Then, consider following item  distribution: $$\varphi'(v)=\begin{cases} {\bot}&\text{if }\varphi(v)\in G_{1}\text{ or }\varphi(v)={\bot}\\ G_{j-1}&\text{if }\varphi(v)\in G_{j}\text{ for }j\in\{ 2,\dots,L^2 \}\end{cases}$$This is clearly an item distribution on $\mathcal{J}$ and also feasible as we are only decreasing the size on the nodes. Hence, $$\text{OPT}(\mathcal{J})\geq \left| \{ v\in V:\varphi'(v)\neq {\bot} \} \right|\geq \left| \{ v\in V:\varphi(v)\neq {\bot} \} \right|-\left| G_{1} \right| =\text{OPT}(\mathcal{I})-q-1$$ 

Then, $q\leq m / L^2< q+1$ and $-q\geq-m / L^2$ and as $L-1< \frac{1}{\varepsilon}\leq L$, we have $\frac{1}{L}\leq \varepsilon$ and $-\frac{1}{L^{2}}\geq-\varepsilon^{2}$
$$\text{OPT}(\mathcal{J})\geq \text{OPT}(\mathcal{I})-m\varepsilon^{2}-1$$

if $m\leq\frac{\text{OPT}(\mathcal{I})}{\varepsilon}-\frac{1}{\varepsilon^{2}}$.

---
Case 2: if there are $m\geq\frac{\text{OPT}(\mathcal{I})}{\varepsilon}-\frac{1}{\varepsilon^{2}}$, then: 

---
Case 3: if $m\leq L^{2}$ then, $$\text{OPT}(\mathcal{J})=$$

Case 4: if $L^3\leq m\leq L^2 /$, then 

---
Let $\text{size} \subseteq(0,1]$. Then, $$\text{OPT}(\mathcal{I})\geq$$
Case 4: if $m>L^{2}$. Tgen 

$$(\text{OPT}(\mathcal{I})+1)>s(I)$$
Let $\varphi$ be optimal. Then, $$\sum_{w\in N(v)}^{}\text{size}(\varphi_{w})\leq h$$
$$\begin{align}\text{OPT}(\mathcal{I})=\sum_{v:\varphi_{v}\neq 0}^{}1\geq\end{align}$$

Let $s$ be the smallest item. Then, $$s\cdot  \text{OPT}(\mathcal{I})=\sum_{v:\varphi_{v}\neq 0}^{}s\geq \sum_{v\in V}^{}\text{size}(\varphi_{v})\geq \text{OPT}(\mathcal{I})$$

1. Claim 1: $$i_{k}\cdot k\geq \sum_{j=1}^{k}i_{j}$$



We will denote the item distribution as a function $\varphi:V\to I\cup \{ \bot \}$ where $\varphi(v)=\bot$ means no item has been assigned. We further define $J:=\{ i\in I: \text{size}(i)\leq \varepsilon \}$. The idea is that we run the exact algorithm on the rest of the items $I \backslash J$, while ensuring there is space for $J$. 
1. $\left\| \varphi \right\|:=\{ v\in V:\varphi(v)\neq {\bot} \}$
2. $s(\varphi):=\sum_{v\in V}^{}\sum_{w\in N(v)}^{} \text{size}(\varphi(w))$. 

Then,

---
We define a DP table as follows:  
1. $\text{DP}[i,v,\ell,s]:=$ maximum number of assigned items from $\ell$ on the subtree rooted at $v$ s.t. $i$ is assigned at $v$ and $\sum_{w\in \text{child}(v)}^{}\text{size}(w)\leq s$. 

We have that:
 $$\text{DP}[{\bot},v,\ell,s]=\max_{\ell'\leq \ell}\max_{i: s}$$

---
hihi

4. Claim 1: $\text{OPT}(\mathcal{J})\geq \text{OPT}(\mathcal{I})-q$
   Let $\varphi:V\to I\cup \{ \bot \}$ be the optimal distribution on $\mathcal{I}$ where $\varphi(v)=\bot$ means no item has been assigned. Then, consider following item  distribution: $$\varphi'(v)=\begin{cases} {\bot}&\text{if }\varphi(v)\in G_{1}\text{ or }\varphi(v)={\bot}\\i_{pq}&\text{if }\varphi(v)=i_{pq+r}\text{ for }p\in[k-1],r\in\{ 0,\dots,k-1 \}\end{cases}$$This is clearly an item distribution on $\mathcal{J}$ and also feasible as we are only decreasing the size on the nodes. Hence, $$\text{OPT}(\mathcal{J})\geq \left| \{ v\in V:\varphi'(v)\neq {\bot} \} \right|\geq \left| \{ v\in V:\varphi(v)\neq {\bot} \} \right|-\left| G_{1} \right| =\text{OPT}(\mathcal{I})-q$$
2. Claim 2: After assignment $\varphi(j)\neq {\bot}$ for all $j\in J$. We have $$s(\varphi) \geq s(\psi)-\varepsilon n $$$$s(\varphi)\leq n(1-\varepsilon)-$$

---


 **Claim 1**: Let $\varphi$ be the optimum. Then, $\max_{v:\varphi_{v}={\bot}}\min_{w\in N(v)}1-\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})< \min_{i\notin \varphi(V)} \text{size}(i)$. 

  Assume otherwise. Then, there exists $v\in V$ with $\varphi_{v}={\bot}$ and an item $i\notin \varphi(V)$ s.t. $$1-\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})\geq \text{size}(i),\quad \forall w\in N(v)$$Let us define $\psi:V\to I\cup \{{\bot} \}$ with $\psi=\varphi$ on $V \backslash \{ v \}$ and $\psi(v)=i$. Then, clearly $\|\psi\|=\|\varphi\|+1$, which is a contradiction to the optimality of $\varphi$.

$$\min_{v:\varphi_{v}={\bot}}\max_{w\in N(v)}\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})>1-\min_{i\notin \varphi(V)} \text{size}(i)$$

**Claim 2:** Let $\varphi$ be optimum. Then, $\max_{v:\varphi_{v}={\bot}}\min_{w\in N(v)}1-\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})< \min_{i\in I} \text{size}(i)$. 

Assume $v\in V$ and item $i\in I$ with $$1-\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})\geq \text{size}(i),\quad \forall w\in N(v)$$
Let us define 


---
We have
$$\text{OPT}=\left\| \varphi_{\text{OPT}} \right\| =\sum_{v\in V}^{}(1-\delta_{{\bot},\varphi(v)})\geq n-\sum_{v\in V}^{}\left( s+\max_{w\in N(v)} \sum_{u\in N(w)}^{}\text{size}(\varphi_{u})-h\right) $$
and
Let $\varphi(v)={\bot}$. Then, $\min_{w\in N(v)}h-\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})\leq s_{\text{min}} -1$ and: $$h-\max_{w\in N(v)}\sum_{u\in N(w)}^{}\text{size}(\varphi_{u})\leq\min_{i\notin \varphi(V)}\text{size}(i)-1 $$

$$\delta_{{\bot},\varphi(v)}=\begin{cases}1\leq s+\max_{w\in N(v)}\sum_{u\in N(w)}\text{size}(\varphi_{u})-h\\0\leq\end{cases}$$


---
Assume we have that $m> x\left( \frac{1}{\varepsilon}+1 \right)$. Then

Then, let $S:=\{ i_{1},\dots,i_{x / \varepsilon} \}$ and $M:=\{ i_{x / \varepsilon+1},\dots,i_{x(1 / \varepsilon + 1)} \}$ Let us similarly split $S$ into $L^{2}$ groups and round up. For $i\notin S$, $\text{size}'(i)=\text{size}(i)$. 

Since $\text{OPT}(I)\leq x$ and $\left| S \right|= x / \varepsilon$, $$\text{OPT}(\mathcal{J})\geq \text{OPT}(\mathcal{I})-\varepsilon x$$

---

Assume that $\varepsilon^{2}\cdot m\leq \text{OPT}< \varepsilon \cdot m$. Then, let $S:=\{ i_{1},\dots,i_{\varepsilon m} \}$. Then, $$\text{OPT}(\mathcal{J})\geq \text{OPT}(\mathcal{I})-\varepsilon m$$

