#Definition #Algorithms 

> [!definition]
> Let $\mathcal{U}:=\{ e_{1},\dots,e_{n} \}$ and $\mathcal{S}=\{ S_{1},\dots,S_{m} \}\subseteq \mathcal{P}(\mathcal{U})$ with a cost function $c:\mathcal{S}\to \mathbb{R}_{>0}$. costs $c_{i}:=\text{cost}(S_{i})>0$. 
> 1. The ***minimum set cover problem*** aims to find a collection of subsets  with union $\mathcal{U}$that has minimum total cost, i.e. $\arg\min_{J\subseteq[m],\bigcup_{j\in J}^{}S_{j}=\mathcal{U}}\sum_{j\in J}^{}c(S_{j})$

^2ed1e3

- **Remark**: We can represent the problem into a bipartite graph where on the left we have the sets $S_{1},\dots,S_{m}$ and $\mathcal{U}$ on the right, indicating the element relation.  ^0eb03c
---
> [!lemma] Theorem 1 (Greedy Algorithm)
> The greedy algorithm works as:
> 1. Pick the set $S_{i}$ that minimizes price per item, i.e. $\text{ppi}(S_{i}):=\frac{c_{i}}{\left| S_{i} \right|}$.
> 2. Remove elements in $S_{i}$ from the universe. 
> 3. Repeat until all elements are covered (with recomputation of $\text{ppi}$)
> 
> The greedy algorithm gives a $H_{n}$-approximation for $H_{n}:=\sum_{i\in [n]}^{}1 / i=\ln n+O(1)$.

^eb92be

> [!proof]-
> Let $\text{OPT}\subseteq [m]$ be the optimal solution where $O_{1},\dots,O_{r}$ denotes the sets $S_{i}$ in the chosen order. Then, 
> 1. **Claim 1: $\text{ppi}(O_{1})\leq \text{cost}(\text{OPT}) / n$.**
> 	Assume otherwise. Then, for any set $S_{i}$, $\text{ppi}(S_{i})> \text{cost}(\text{OPT}) / n$. Let $\mathcal{V_{i}}\subseteq \text{OPT}$ be the subsets that contain $e_{i}$ (which is non-empty by assumption), then: $$\text{cost}(\text{OPT})=\sum_{i\in [n]}^{} \frac{1}{\left| \mathcal{V}_{i} \right| }\sum_{O_{j}\in \mathcal{V_{i}}}^{}\frac{\text{cost}(O_{j})}{\left| O_{j} \right| } \geq \text{ppi}(S_{i})$$
>2. **Claim 2: Greedy picks a solution with cost $\leq H_{n}\cdot \text{cost}(\text{OPT})$**.
> 	  1. If $n=1$, the claim holds.
> 	  2. If $n>1$, then let the greedy algorithm pick a set $S_{i}$ of size $k$. Then, $$\begin{align}\text{cost}(\text{GREEDY})&\leq k\cdot \frac{\text{cost}(\text{OPT})}{n}+\text{cost}(\text{GREEDY}')\\&\leq \frac{k}{n}\text{cost}(\text{OPT})+H_{n-k}\cdot  \underbrace{ \text{cost}(\text{OPT}(P')) }_{ \leq \text{cost}(\text{OPT}) }\\&\leq\text{cost}(\text{OPT})\left( k / n+H_{n-k} \right) \\&\leq \text{cost}(\text{OPT})\cdot H_{n}\end{align}$$

^d320dd

- **Remark** (Steurer): It is $\mathcal{NP}$-hard to find a $(1-\varepsilon)\cdot H_{n}$-approximation for any constant $\varepsilon>0$.  ^4d9187

---
> [!lemma] Theorem 2 (Linear Programming)
> Let $\{ x_{i} \}_{i\in [m]}$ be the optimal solution of the problem: $$\begin{align}\text{min}\quad &\sum_{i\in [m]}^{}x_{i}\cdot c(S_{i})\\\text{subject to}\quad &\sum_{S_{i}\ni e_{j}}^{}x_{i}\geq 1&&\forall j\in [n]\\&0\leq x_{i}\leq 1&&\forall i\in[m]\end{align}$$Let 
> 1. $y_{i} \sim \text{Ber}(x_{i})$ and $J:=\{ i\in[m]: y_{i}=1 \}$. It holds that: 
> 	1. $\mathbb{E}[c(J)]=c(\text{OPT}_{\text{LP}})$ and 
> 	2. $\mathbb{P}(J\text{ is not feasible})\leq n / e$
> 2. $y_{i} \sim \text{Bin}(2 \ln n , x_{i})$ and $J:=\{ i\in [m]: y_{i}\geq 1 \}$. It holds that: 
> 	1. $\mathbb{E}[c(J)]\leq 2\ln n \cdot c(\text{OPT}_{\text{LP}})$ and 
> 	2. $\mathbb{P}(J\text{ is not feasible})\leq \frac{1}{n}$.
> 	3. $\mathbb{P}(J \text{ is feasible }\land c(J)\leq 4\ln n \cdot c(\text{OPT}_{LP}))\geq \frac{1}{3}$

^e18582

> [!proof]-
> We have that:
> 1. First, observe that $$\mathbb{E}[c(J)]=\mathbb{E}\left[ \sum_{i=1}^{m}y_{i}c(S_{i}) \right]=\sum_{i=1}^{m}c(S_{i})\cdot x_{i}=c(\text{OPT}_{\text{LP}})$$Then, 
> 	1. **Claim 1**: $\mathbb{P}\left( \sum_{S_{i} \ni e_{j}}^{}y_{i}=0 \right)\leq e^{-1}$.
> 	   Observe that:
>     $$\begin{align}\mathbb{P}\left( \sum_{S_{i} \ni e_{j}}^{}y_{i}=0 \right)&=\mathbb{P}\left( y_{i}=0,\forall S_{i}\ni e_{j}\right)=\prod_{S_{i}\ni e_{j}}^{}(1-x_{i})\\&\leq \prod_{S_{i}\ni e_{j}}^{}\exp \left( -x_{i} \right)=\exp \left( -\sum_{S_{i}\ni e_{j}}^{}x_{i} \right)\leq e^{-1}\end{align}$$
>     
>     Therefore, $\mathbb{P}(J\text{ is not feasible})\leq n / e$ by union bound.
>  1. We have that:
> 	 1. For the expectation, it holds that:$$\mathbb{E}[c(J)]\leq 2 \ln n\cdot \mathbb{E}\left[ \sum_{i=1}^{m}y_{i}c(S_{i}) \right] =2\ln n\cdot c(\text{OPT}_{\text{LP}})$$
> 	 2. **Claim 1**: $\mathbb{P}\left( \sum_{S_{i} \ni e_{j}}^{}y_{i}=0 \right)\leq (e^{-1})^{2 \ln n}=\frac{1}{n^{2}}$.
> 	  2. **Claim 2**: $\mathbb{P}\left( \exists j\in [n]:\sum_{S_{i} \ni e_{j}}^{}y_{i}=0  \right)\leq \frac{1}{n}$ by union bound.
> 	  3. **Claim 3**: $\mathbb{P}(c(J)\geq 4\ln n \cdot c(\text{OPT}_{\text{LP}}))\leq \frac{1}{2}$.
> 	
> 	Therefore, $\mathbb{P}(J \text{ is not feasible }\land c(J)\geq 4\ln n \cdot c(\text{OPT}_{LP}))\leq \frac{1}{n}+\frac{1}{2}\leq \frac{2}{3}$. 

^20f82b

---