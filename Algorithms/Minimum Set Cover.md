#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}=\{ S_{1},\dots,S_{m} \}\subseteq 2^{[n]}$ with a cost function $c:\mathcal{S}\to \mathbb{R}_{>0}$. 
> 1. The ***minimum set cover problem*** aims to find:$$\underset{ J\subseteq[m],\bigcup_{j\in J}^{}S_{j}=[n] }{ \arg\min }\sum_{j\in J}^{}c(S_{j})$$

^2ed1e3

- **Remark**: We can represent the problem into a bipartite graph where on the left we have the sets $S_{1},\dots,S_{m}$ and $\mathcal{U}$ on the right, indicating the element relation.  ^0eb03c
---
> [!lemma] Theorem 1 (Greedy Algorithm)
> Consider the following algorithm: 
> ```pseudo
> \begin{algorithm}\caption{Greedy($I$)}
> \begin{algorithmic} 
> \State $J\gets \varnothing$
> \State $V \gets \varnothing$
> \While{$V\neq[n]$}
> \State $j\gets \arg\min_{{i\in [m] \backslash J}}c(S_{i}) / \left| S_{i} \backslash V \right|$
> \State $J\gets J\cup \{j  \}$
> \State $V\gets V\cup \{ S_{j} \}$
\EndWhile
\end{algorithmic}
\end{algorithm}
> ```
> 
> The algorithm gives a $H_{n}$-approximation for $H_{n}:=\sum_{i\in [n]}^{}1 / i\sim\ln n$.

^eb92be

> [!proof]-
> Let $\text{OPT}\subseteq [m]$ be the optimal solution where $O_{1},\dots,O_{r}$ denotes the sets $S_{i}$ in the chosen order. Further let $\text{ppi}(S_{i}):=c(S_{i}) / \left| S_{i} \right|$. Then,
> 1. **Claim 1: $\text{ppi}(O_{1})\leq \text{cost}(\text{OPT}) / n$.**
> 	Assume otherwise. Then, for any set $S_{i}$, $\text{ppi}(S_{i})> \text{cost}(\text{OPT}) / n$. Let $\mathcal{V_{i}}\subseteq \text{OPT}$ be the subsets that contain $i$ (which is non-empty by assumption), then: $$\text{cost}(\text{OPT})=\sum_{i\in[n]}^{}\sum_{S\in \mathcal{V}_{i}}^{}\frac{c(S)}{\left| S \right| } >\sum_{i\in[n]}^{}\sum_{S\in \mathcal{V}_{i}}^{}\frac{\text{cost}(\text{OPT})}{n} \geq \text{cost}(\text{OPT})$$which is a contradiction.
>2. **Claim 2: Greedy picks a solution with cost $\leq H_{n}\cdot \text{cost}(\text{OPT})$**.
> 	  1. If $n=1$, the claim holds.
> 	  2. If $n>1$, then let the greedy algorithm pick a set $S_{i}$ of size $k$. Then, $$\begin{align}\text{cost}(\text{Greedy})&=\left| O_{1} \right| \cdot  \text{ppi}(O_{1})+\text{cost}(\text{Greedy}')\\&\leq k\cdot \frac{\text{cost}(\text{OPT})}{n}+\text{cost}(\text{Greedy}')\\&\leq \frac{k}{n}\text{cost}(\text{OPT})+H_{n-k}\cdot  \underbrace{ \text{cost}(\text{OPT}(P')) }_{ \leq \text{cost}(\text{OPT}) }\\&\leq\text{cost}(\text{OPT})\left( k / n+H_{n-k} \right) \\&\leq \text{cost}(\text{OPT})\cdot H_{n}\end{align}$$

^d320dd

- **Remark** (Steurer): It is $\mathcal{NP}$-hard to find a $(1-\varepsilon)\cdot H_{n}$-approximation for any constant $\varepsilon>0$.  ^4d9187

---
> [!lemma] Theorem 2 (Linear Programming)
> Let $\{ x_{i} \}_{i\in [m]}$ be the optimal solution of the problem: $$\begin{align}\text{min}\quad &\sum_{i\in [m]}^{}x_{i}\cdot c(S_{i})\\\text{subject to}\quad &\sum_{S_{i}:e_{j}\in S_{i}}^{}x_{i}\geq 1&&\forall j\in [n]\\&0\leq x_{i}\leq 1&&\forall i\in[m]\end{align}$$Let 
> 1. $y_{i} \sim \text{Ber}(x_{i})$ and $J:=\{ i\in[m]: y_{i}=1 \}$. It holds that: 
> 	1. $\mathbb{E}[c(J)]=c(\text{OPT}_{\text{LP}})$ and 
> 	2. $\mathbb{P}(J\text{ is not feasible})\leq n / e$
> 2. $y_{i} \sim \text{Bin}(2 \ln n , x_{i})$ and $J:=\{ i\in [m]: y_{i}\geq 1 \}$. It holds that: 
> 	1. $\mathbb{E}[c(J)]\leq 2\ln n \cdot c(\text{OPT}_{\text{LP}})$ and 
> 	2. $\mathbb{P}(J\text{ is not feasible})\leq \frac{1}{n}$.
> 	3. $\mathbb{P}(J \text{ is feasible }\land c(J)\leq 4\ln n \cdot c(\text{OPT}_{LP}))\geq \frac{1}{4}$

^e18582

> [!proof]-
> We have that:
> 1. First, observe that $$\mathbb{E}[c(J)]=\mathbb{E}\left[ \sum_{i=1}^{m}y_{i}c(S_{i}) \right]=\sum_{i=1}^{m}c(S_{i})\cdot x_{i}=c(\text{OPT}_{\text{LP}})$$Then, 
> 	1. **Claim 1**: $\mathbb{P}\left( \sum_{S_{i}:e_{j}\in S_{i} }^{}y_{i}=0 \right)\leq e^{-1}$.
> 	   Observe that:
>     $$\begin{align}\mathbb{P}\left( \sum_{S_{i} \ni e_{j}}^{}y_{i}=0 \right)&=\mathbb{P}\left( y_{i}=0,\forall S_{i}\ni e_{j}\right)=\prod_{S_{i}\ni e_{j}}^{}(1-x_{i})\\&\leq \prod_{S_{i}\ni e_{j}}^{}\exp \left( -x_{i} \right)=\exp \left( -\sum_{S_{i}\ni e_{j}}^{}x_{i} \right)\leq e^{-1}\end{align}$$
>     
>     Therefore, $\mathbb{P}(J\text{ is not feasible})\leq n / e$ by union bound.
>  1. We have that:
> 	 1. For the expectation, it holds that:$$\mathbb{E}[c(J)]=\sum_{i=1}^{m}c(S_{i})\mathbb{P}(y_{i}\geq 1)\leq 2 \ln n\sum_{i=1}^{m}x_{i}c(S_{i})=2\ln n\cdot c(\text{OPT}_{\text{LP}})$$
> 	 2. **Claim 1**: $\mathbb{P}\left( \sum_{S_{i} \ni e_{j}}^{}y_{i}=0 \right)\leq (e^{-1})^{2 \ln n}=\frac{1}{n^{2}}$.
> 	  2. **Claim 2**: $\mathbb{P}\left( \exists j\in [n]:\sum_{S_{i} \ni e_{j}}^{}y_{i}=0  \right)\leq \frac{1}{n}$ by union bound.
> 	  3. **Claim 3**: $\mathbb{P}(c(J)\geq 4\ln n \cdot c(\text{OPT}_{\text{LP}}))\leq \frac{1}{2}$ as we have that by Markov, $$\mathbb{P}(c(J)\geq 4\ln n \cdot c(\text{OPT}_{\text{LP}}))\leq \mathbb{P}(c(J)\geq 2\mathbb{E}[c(J)])\leq \frac{1}{2}$$
> 	
> 	Therefore, $\mathbb{P}(J \text{ is not feasible }\land c(J)\geq 4\ln n \cdot c(\text{OPT}_{LP}))\leq \frac{1}{n}+\frac{1}{2}\leq \frac{3}{4}$. 

^20f82b

---
> [!lemma] Theorem 3 (Linear Programming)
> Let $\{ x_{t} \}_{t\in T}$ be the optimal solution of the problem: $$\begin{align}\text{min}\quad &\sum_{t\in T}^{}x_{t}\\\text{subject to}\quad &\sum_{t\in F_{i}}^{}x_{t}\geq 2&&\forall i\in [k]\\&0\leq x_{t}\leq 1&&\forall t\in T\end{align}$$Let 
> 1. $T':=\left\{  t\in T:x_{t}\geq \frac{1}{b-1}  \right\}$. 
> 2. $y_{i} \sim \text{Bin}(2 \ln n , x_{i})$ and $J:=\{ i\in [m]: y_{i}\geq 1 \}$. It holds that: 
> 	1. $\mathbb{E}[c(J)]\leq 2\ln n \cdot c(\text{OPT}_{\text{LP}})$ and 
> 	2. $\mathbb{P}(J\text{ is not feasible})\leq \frac{1}{n}$.
> 	3. $\mathbb{P}(J \text{ is feasible }\land c(J)\leq 4\ln n \cdot c(\text{OPT}_{LP}))\geq \frac{1}{4}$


> [!proof]-
> We have that:
> 1. First, observe that as $\sum_{t\in F_{i}}^{}x_{t}\geq 2$, there exists $t\in F_{i}$ with $x_{t}\geq \frac{2}{\left| F_{i} \right|}$
> 	
> 	Assume that there exists $i\in[k]$ with $\left| F_{i}\cap T' \right|\leq 1$. Then, we have that: $$2\leq\sum_{t\in F_{i}}^{}x_{t}< \frac{\left| F_{i} \right| -1}{b-1}+1\leq 2$$which is a contradiction. Hence, we have two TAs for each group. Further, $$\sum_{t\in T}^{}x_{t}\geq \left| T' \right| \frac{1}{b-1}$$which proves the statement.
> 2. Let $y_{t}\sim \text{Bin}(c\ln n, x_{t})$ and $z_{t}$ be the indicator variable that $y_{t}\geq 1$. Then, 
> 	$$\mathbb{E}[\left| T' \right| ]=\sum_{t\in T}^{}\mathbb{P}(y_{t}\geq 1)\leq \sum_{t\in T}^{}\mathbb{E}[y_{t}]=c\ln n\sum_{t\in T}^{}x_{t}\leq c\ln n\cdot \text{OPT}$$Further, for any $i\in[k]$, let $Z_{i}:=\sum_{t\in F_{i}}^{}z_{t}$. Then,
> 	$$\begin{align}\mathbb{P}(Z_{i}\leq 1)&\leq \sum_{S\in {F_{i} \choose \left| F_{i} \right|-1 }}^{}\prod_{t\in S}^{}\mathbb{P}(y_{t}=0)\leq \sum_{S\in {F_{i} \choose \left| F_{i} \right|-1 }}^{}\prod_{t\in S}^{}\mathbb{P}(y_{t}=0)\\&= \sum_{S\in {F_{i} \choose \left| F_{i} \right|-1 }}^{}\prod_{t\in S}^{}(1-x_{t})^{c\ln n}\leq  \sum_{S\in {F_{i} \choose \left| F_{i} \right|-1 }}^{}n^{-c\sum_{t\in S}^{}x_{t}}=\left| F_{i} \right| n^{-c}\leq n^{1-c}\end{align}$$Hence, $$\mathbb{P}(\exists i:Z_{i}\leq 1)\leq n^{2-c}\leq \frac{1}{2}$$for $c\geq 3$.
---
Let $X_{i}$ be the number of balls in $i$-th bin. Then, $\mathbb{E}[X_{i}]=1$ and:$$\mathbb{P}(X_{i}> c\log n)=\mathbb{P}(2^{X_{i}}\geq n^c)\leq $$

Let $X_{i,j}$ be the indicator variable that $j$-th ball goes to $i$-th bin. Further, let $Z_{i,j}=\sum_{\ell\leq j}^{}X_{i,\ell}$. Then, we claim that $\mathbb{E}[2^{Z_{i,j}}]=\left( \frac{n+1}{n} \right)^j$ by induction. 
1. If $j=1$, then $\mathbb{E}[2^{Z_{i,1}}]=\frac{2}{n}+\frac{n-1}{n}=\frac{n+1}{n}$.
2. If $j\geq 1$, then: $$\mathbb{E}[2^{Z_{i,j}}]=\frac{2\mathbb{E}[2^{Z_{i,j-1}}]}{n}+\frac{(n-1)\mathbb{E}[2^{Z_{i,j-1}}]}{n}=\left( \frac{n+1}{n} \right) ^{j}$$

Hence, $$\mathbb{P}(X_{i}> c\log n)=\mathbb{P}(2^{X_{i}}\geq n^c)\leq \frac{\left( \frac{n+1}{n} \right)^n}{n^c}\leq \frac{e}{n^c}$$Therefore, $$\mathbb{P}(\exists i:X_{i}> c\log n)\leq \frac{e}{n^{c-1}}$$

---
