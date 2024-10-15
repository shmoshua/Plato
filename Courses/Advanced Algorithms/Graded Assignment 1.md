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

We have $E_{R},E_{B},E_{V}$ as the edge sets. Let $R\sqcup B$ denote the vertex partition by color, i.e. the red and blue vertices. 
1. $\frac{\left| E \right|-\left| E_{V} \right|}{2}\leq\frac{\left| E_{R} \right|+\left| E_{B} \right|}{2}\leq\max \{ \left| E_{R} \right|,\left| E_{B} \right| \}\leq \text{OPT}\leq \left| E \right|$.
2. 



For vertex $x$, let $r_{x},b_{x},\ell_{x}$ denote the number of red, blue and violet edges respectively. Then, for each color red with probability $\frac{r_{e}}{r_{x}+b_{x}}$. 


1. For $\{ v,w \}\in E$ red, $\mathbb{P}(v\in R\land w\in R)=\frac{r_{v}}{r_{v}+b_{v}}\cdot\frac{r_{w}}{r_{w}+b_{w}}$
2. For $\{ v,w \}\in E$ blue, $\mathbb{P}(v\in B\land w\in B)=\frac{b_{v}}{r_{v}+b_{v}}\cdot\frac{b_{w}}{r_{w}+b_{w}}$
3. For $\{ v,w \}\in E$ violet, $\mathbb{P}(\text{point})=\frac{r_{v}}{r_{v}+b_{v}}\cdot\frac{b_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\cdot\frac{r_{w}}{r_{w}+b_{w}}$

Then, let $X$ be the number of points. We have that:

For each edge $v$, $$\begin{align}\mathbb{E}[X_{v}]&=\frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{}\frac{r_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{B}}^{}\frac{b_{w}}{r_{w}+b_{w}}+\frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{V}}^{}\frac{b_{w}}{r_{w}+b_{w}}+\frac{b_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{V}}^{}\frac{r_{w}}{r_{w}+b_{w}}\\&\leq\frac{r_{v}^{2}}{r_{v}+b_{v}}+\frac{b ^{2}_{v}}{r_{v}+b_{v}}+\frac{r_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}}+\frac{b_{v}(d(v)-r_{v}-b_{v})}{r_{v}+b_{v}}\\&=\frac{r_{v}d(v)-r_{v}b_{v}+b_{v}d(v)-r_{v}b_{v}}{r_{v}+b_{v}}\\&=d(v)-\frac{2r_{v}b_{v}}{r_{v}+b_{v}}\end{align}$$
 Then, $$\mathbb{E}[X]=\frac{1}{2}\sum_{v\in V}^{}\mathbb{E}[X_{v}]=\left| E \right| -\sum_{v\in S}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}\geq \text{OPT}+\frac{\left| S \right|}{2}-\sum_{v\in S}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}$$
The optimum 

$$\sum_{v\in V}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}\leq \frac{2}{3}\text{OPT}$$

$\frac{a}{b}\leq \frac{a+c}{b+c}$ because $ab+ac\leq ab+bc$ if $a\leq b$

$$\frac{r_{v}b_{v}}{r_{v}+b_{v}}\leq\frac{\left( \frac{r_{v}+b_{v}}{2} \right)^{2}}{r_{v}+b_{v}}=\frac{r_{v}+b_{v}}{4}$$Therefore,  $$\text{OPT}\geq \frac{\left| E _{R}\right| +\left| E_{B} \right| }{2}=\frac{\sum_{v\in V}^{}r_{v}+b_{v}}{4}\geq \sum_{v\in V}^{}\frac{r_{v}b_{v}}{r_{v}+b_{v}}$$

---
We have:
1. If $$\mathbb{E}[X_{v,R}]= \frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{}\frac{r_{w}}{r_{w}+b_{w}}\geq \frac{r_{v}}{r_{v}+b_{v}}\sum_{w:\{ v,w \}\in E_{R}}^{} \frac{1}{}$$