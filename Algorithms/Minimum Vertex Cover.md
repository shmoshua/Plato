#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be a [[graph]] with vertex weights $c:V\to \mathbb{R}_{>0}$. 
> 1. The ***minimum vertex cover*** aims to find: $$S_{\text{OPT}}\in\underset{ S\subseteq V,\forall e\in E: e\cap S\neq \varnothing }{ \arg\min }c(S)$$

^37c645

---
##### Properties
> [!lemma] Theorem 1 (Linear Programming)
> Let $\{ x_{v} \}_{v\in V}\subseteq \mathbb{R}$ be the solution of the optimization problem $$\begin{align}\text{min}\quad&\sum_{v\in V}^{}x_{v}\cdot c(v)\\\text{subject to}\quad &x_{u}+x_{v}\geq 1 &&\forall \{ u,v \}\in E\\&0\leq x_{v}\leq 1&&\forall v\in V \end{align}$$Then, for $S:=\left\{  v\in V: x_{v}\geq \frac{1}{2}  \right\}$, 
> 1. $S$ is a $2$-approximation of the optimum. $c(S)\leq 2\cdot c(S_{\text{OPT}})$.
> 2. the [[Linear Programming|integrality gap]] $\text{IG}= 2$.

^bfb726


> [!proof]-
> We have:
> 1. Let $y_{v}\in \{ 0,1 \}$ where $y_{v}=\mathbb{1}_{\left\{  x_{v}\geq \frac{1}{2}  \right\}}$. We have:
> 	1. **Claim 1**: $\sum_{v\in V}^{}x_{v}\cdot c(v)\leq c(S_{\text{OPT}})$. 
>    Let $z_{v} =\chi_{S_{\text{OPT}}}(v)$. Then, $\sum_{v\in V}^{}z_{v}\cdot c(v)=c(S_{\text{OPT}})$ and $\{ z_{v} \}_{v}$ is a feasible solution. This proves the claim.
> 	1. **Claim 2**: $y_{v}\leq 2x_{v}$ for all $v\in V$. 
>	Trivial.
>	1. **Claim 3:** $\{ y_{v} \}_{v}$ is a feasible solution of the LP.
>   Also trivial. 
> 
> 	Therefore, $$c(S)=\sum_{v\in V}^{}y_{v}\cdot c(v)\leq 2\cdot \sum_{v\in V}^{}x_{v}\cdot c(v)\leq 2\cdot c(S_{\text{OPT}})$$
> 2. We have that $c(S_{\text{OPT}_{\text{ILP}}})\leq 2\cdot c(S_{\text{OPT}_{\text{LP}}})$. For the converse, consider $K_{n}$ with unit vertex cost. Then, $$\frac{c(S_{\text{OPT}_{\text{ILP}}})}{c(S_{\text{OPT}_{\text{LP}}})}= \frac{\left| S_{\text{OPT}_{\text{ILP}}} \right|}{\left| S_{\text{OPT}_{\text{LP}}} \right|} = \frac{n-1}{n / 2}\xrightarrow{n\to \infty}2$$Therefore, $\text{IG}\geq 2$. 

^af947a

---