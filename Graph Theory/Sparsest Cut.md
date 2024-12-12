#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. The ***sparsest cut*** problem is given as: $$S^{*}\in \underset{ S\subseteq V }{ \text{argmin} } \frac{e(S,V \backslash S)  }{\left| S \right| \cdot \left| V \backslash S \right| }$$

^02a58c

- **Remark**: For any $S\subseteq V$, we define $\mathcal{L}(S):=e(S, V \backslash S) / \left| S \right|\left| V \backslash S \right|$.  ^9966da
---
##### Properties
> [!lemma] Theorem (LP)
> Consider the following LP: $$\begin{array}{rll} \min& \sum_{\{ u,v \}\in E}^{}d_{uv}\\\text{subject to}& d_{u,v}\geq 0,\quad d_{uv}=d_{vu}&\forall u,v\in V\\&d_{u,v}\leq d_{v,w}+d_{w,v}&\forall u,v,w\in V\\&\sum_{u,v}^{}d_{uv}=1\end{array}$$
> Let $d^{*}$ be the LP minimum. 

^292a9d

> [!proof]-
> Firstly, notice that $d^{*}$ is a pseudo-metric. Hence, there exists a metric embedding $\phi:V\to \mathbb{R}^k$ for $k\in \text{O}(\log n)$ s.t. $\frac{d(u,v)}{\log n}\leq \|\phi(u)-\phi(v)\|_{1}\leq d(u,v)$ for all $u,v\in V$.
> 
> Let $\phi:=(\phi_{1},\dots,\phi_{k})$ and $j:=\arg\min_{i\in[k]} \frac{\sum_{\{ u,v \}\in E}\left| \phi_{i}(u)-\phi_{i}(v) \right|}{\sum_{u,v\in V}^{}\left| \phi_{i}(u)-\phi_{i}(v) \right|}$. Let $a=\min_{v}\phi_{j}(v)$ and $b=\max_{v}\phi_{j}(v)$. Then, let $\tau \sim \text{Uniform}([a,b])$ and we define: $$S_{\tau}:=\{ v\in V:\phi_{j}(v)\leq \tau \}$$Then, for any $u,v\in V$: $$\left| \chi_{S_{\tau}}(u)- \chi_{S_{\tau}}(v) \right|=\begin{cases}1& \min\{ \phi_{j}(u),\phi_{j}(v) \}\leq \tau< \max\{ \phi_{j}(u),\phi_{j}(v) \}\\0&\text{otherwise}\end{cases}$$Therefore, $\mathbb{E}[\left| \chi_{S_{\tau}}(u)- \chi_{S_{\tau}}(v) \right|]=\left| \phi_{j}(u)-\phi_{j}(v) \right|/(b-a)$. Hence, by Lemma 1: $$\begin{align}\frac{\sum_{\{ u,v \}\in E }\|\phi(u)-\phi(v)\|_{1}}{\sum_{u,v\in V }\|\phi(u)-\phi(v)\|_{1}}\geq\frac{\sum_{\{ u,v \}\in E }|\phi_{j}(u)-\phi_{j}(v)|}{\sum_{u,v\in V }|\phi_{j}(u)-\phi_{j}(v)|}=\frac{\sum_{\{ u,v \}\in E }\mathbb{E}[\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| ]}{\sum_{u,v\in V }\mathbb{E}[\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| ]}\end{align}$$ Let $v_{1},\dots,v_{n}$ be the vertices ordered in $\phi_{j}$. Then, 
> $$\begin{align}\sum_{\{ u,v \}\in E}^{}\mathbb{E}\left[ \left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right|  \right]&=\mathbb{E}\left[ \sum_{\{ u,v \}\in E}^{}\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right|  \right]\\&=\sum_{i=1}^{n-1}\frac{\left| \phi_{j}(v_{i+1})-\phi_{j}(v_{i}) \right|}{(b-a)} \left( \sum_{\{ u,v \}\in E}^{}\left| \chi_{S_{\phi_{j}(v_{i})}}(u)-\chi_{S_{\phi_{j}(v_{i})}}(v) \right|  \right)\end{align}$$Hence, by Lemma 1, we have that: $$\begin{align}\frac{\sum_{\{ u,v \}\in E }\|\phi(u)-\phi(v)\|_{1}}{\sum_{u,v\in V }\|\phi(u)-\phi(v)\|_{1}}\geq\frac{\sum_{\{ u,v \}\in E }\mathbb{E}[\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| ]}{\sum_{u,v\in V }\mathbb{E}[\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| ]}\geq\min_{\tau\in[a,b]}\frac{\sum_{\{ u,v \}\in E }\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| }{\sum_{u,v\in V }\left| \chi_{S_{\tau}}(u)-\chi_{S_{\tau}}(v) \right| }\end{align}$$Therefore, we have that: $$\begin{align}\frac{\left| E(S_{\tau}, V \backslash S_{\tau}) \right| }{\left| S_{\tau} \right| \left| V \backslash S_{\tau} \right| }&=\end{align}$$

^9d40c1

---


> [!lemma] Lemma 1
> Let $a_{1},\dots,a_{k},b_{1},\dots,b_{k}\geq 0$ for which $\sum_{i=1}^{k}b_{i}\neq 0$. Then, $$\frac{\sum_{i=1}^{k}a_{i}}{\sum_{i=1}^{k}b_{i}}\geq \min_{i\in[k]} \frac{a_{i}}{b_{i}}$$

> [!proof]-
> Let $k=2$. Then, let $p:=\min\left\{  \frac{a}{b}, \frac{c}{d}  \right\}$
> $$\frac{a+c}{b+d}=\frac{\frac{a}{b}+\frac{c}{d}\cdot \frac{d}{b}}{1+\frac{d}{b}}\geq p$$This proves the statement as it holds with $k=1$.  