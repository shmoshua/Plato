#TCS #Definition 

> [!definition]
> Let $G:=(V,E)$ be a finite [[graph|undirected graph]] with adjacency matrix $A$. For $\beta\geq 0$ and $h\in \mathbb{R}$, 
> 1. the ***ferromagnetic ising model*** with inverse temperature $\beta$ and external field $h$, is given by $\mu_{\beta,h}\in \Delta(\{ \pm 1 \}^{V})$ where: $$\mu_{\beta,h}(x) \propto \exp\left( \frac{\beta}{2}x^\top Ax + h\braket{ x , 1 }  \right),\quad \forall x\in \{ \pm 1 \}^V$$

---
##### Properties
###### FPRAS for Partition Function
> [!definition] Definition (Even Subgraphs Representation)
> For $F\subseteq E$, we define: 
> 1. $\textsf{odd}(F):=\{ v\in V:\text{deg}_{F}(v)\text{ is odd} \}$
> 2. For $0\leq\rho\leq 1$ and $\lambda \geq 0$, we define the ***even subgraphs model***: $$\widehat{\mu}_{\rho,\lambda}(F) \propto \rho^{\left| \textsf{odd}(F) \right| }\lambda^{\left| F \right| },\qquad \forall F\subseteq E$$with the partition function $\widehat{Z}(\rho,\lambda)=\sum_{F\subseteq E}\rho^{\left| \textsf{odd}(F) \right| }\lambda^{\left| F \right| }$

---

> [!lemma] Proposition 1
> For every $\beta,h\geq 0$, we have that:$$Z(\beta,h)=2^{\left| V \right| }\cosh(h)^{\left| V \right| }\cosh(\beta)^{\left| E \right| }\cdot \widehat{Z}(\tanh(h),\tanh(\beta))$$

> [!proof]-
> We have that: $$\begin{aligned}\exp\left( \frac{\beta}{2}x^\top Ax + h\braket{ x , 1 }  \right)&=\prod_{uv\in E} \exp\left( \beta x_{u}x_{v} \right)\prod_{u\in V}^{}\exp (hx_{u})
> \\&=\prod_{uv\in E} \cosh\left( \beta x_{u}x_{v} \right)\prod_{uv\in E} \left(1+ \tanh\left( \beta x_{u}x_{v} \right) \right)\prod_{u\in V}^{}\exp (hx_{u})
> \\&= \cosh\left( \beta  \right)^{\left| E \right| }\cosh(h)^{\left| V \right| }\prod_{uv\in E} \left(1+ x_{u}x_{v}\tanh\left( \beta  \right) \right)\prod_{u\in V}^{}(1+x_{u}\tanh (h))
> \\&= \cosh\left( \beta  \right)^{\left| E \right| }\cosh(h)^{\left| V \right| }\left( \sum_{F\subseteq E} \tanh(\beta)^{\left| F \right| }\prod_{uv\in F} x_{u }x_{v} \right)\left( \sum_{S \subseteq V}\tanh(h)^{\left| S \right|}\prod_{v\in S}x_{v} \right)
>  \\&= \cosh\left( \beta  \right)^{\left| E \right| }\cosh(h)^{\left| V \right| }\sum_{F\subseteq E, S\subseteq V} \tanh(\beta)^{\left| F \right| }\tanh(h)^{\left| S \right|}\prod_{v\in \textsf{odd}(F)\oplus  S} x_{v} \end{aligned}$$
>  It follows that: $$Z(\beta,h)=\cosh\left( \beta  \right)^{\left| E \right| }\cosh(h)^{\left| V \right| }\sum_{F\subseteq E, S\subseteq V} \tanh(\beta)^{\left| F \right| }\tanh(h)^{\left| S \right|}\sum_{x\in \{ \pm 1 \}^V}^{}\prod_{v\in \textsf{odd}(F)\oplus  S} x_{v} $$As $\sum_{x}^{}\prod_{v\in A}x_{v}=2^{\left| V \right|}$ if and only if $A=\varnothing$ and $0$ otherwise, we have that: $$Z(\beta ,h)=2^{\left| V \right| }\cosh\left( \beta  \right)^{\left| E \right| }\cosh(h)^{\left| V \right| }\sum_{F\subseteq E} \tanh(\beta)^{\left| F \right| }\tanh(h)^{\left| \textsf{odd}(F) \right|}$$
---
> [!lemma] Proposition 2 
> Suppose there exists a FPAS for sampling from $\widehat{\mu}_{\rho,\lambda}$ for every $0\leq \rho,\lambda\leq 1$. Then, 
> 1. there exists an FPRAS for estimating $\widehat{Z}(\rho,\lambda)$ for all $0\leq \rho,\lambda\leq 1$.