#Series #Algorithms 

#### Problem 1

1. Let $z\in \text{argmin}_{x\in X\cup Y}h_{j}(x)$. As there are no collisions in the hash function $h_{j}$, we have that $z$ is unique. Then, 
   1. if $z\in X\cap Y$. Then, $g_{j}(X)=z=g_{j}(Y)$. Further, $\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$. Hence, we have: $$\mathbb{P}(z\in X\cap Y\land g_{j}(X)\equiv_{2}g_{j}(Y))=\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$$
   2. if $z\notin X\cap Y$, then the probability that $g_{j}(X)\equiv_{2}g_{j}(Y)$ is the probability that the two minima of hash values having the same parity. Then,  $$\begin{align}\mathbb{P}(g_j(X)\equiv_{2}g_{j}(Y)\land z\notin X \cap Y)&=\frac{1}{2}(1-\text{Sim}(X,Y))\end{align}$$

	Hence, $$\mathbb{P}(g_{j}(X)\equiv_{2}g_{j}(Y))=\text{Sim}(X,Y)+\frac{1}{2}\left( 1-\text{Sim}(X,Y) \right)=\frac{1+\text{Sim}(X,Y)}{2} $$

2. Let $i\in[\sqrt{ n }]$. Then, $$\mathbb{P}(f_{i}(X)=f_{i}(Y))=\prod_{j=1}^{\ell}\mathbb{P}(g_{i,j}(X)=g_{i,j}(Y))=\frac{\left( 1+\text{Sim}(X,Y) \right) ^\ell}{2^\ell}$$Hence, $$\begin{align}\mathbb{P}(\forall i:f_{i}(X)\neq f_{i}(Y))&=\prod_{i=1}^{\sqrt{ n }}\mathbb{P}(f_{i}(X)\neq f_{i}(Y))\\&=\left( 1-\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^\ell  \right)^{\sqrt{ n }}\\&\leq \left( 1-0.95^{\frac{1}{2}\log_{1 / 0,95}(n)} \right)^{\sqrt{ n }} \\&= \left( 1-(1/0.95)^{-\frac{1}{2}\log_{1 / 0,95}(n)} \right)^{\sqrt{ n }} \\&=\left( 1-\frac{1}{\sqrt{ n }} \right)^{\sqrt{ n }}\\&\leq e^{-1}\end{align} $$Therefore, with at least $1-e^{-1}$ probability, there exists $i$ with $f_{i}(X)=f_{i}(Y)$. In this case we have that $\text{Sim}(X,Z)\geq \text{Sim}(X,Y)$ as the algorithm takes the song with the maximum similarity to $X$.
3. Fix a recorded song $X$. For a song $Z\in 2^{[U]}$, let $T_{Z}$ be the indicator variable denoting if there exists $i$ s.t. $f_{i}(X)=f_{i}(Z)$. Define $T:=\sum_{Z\in S}^{}T_{Z}$. Let $Y\in S$ be the recorded song of $X$. Then,  
	
---
We have that: $$\mathbb{P}(f_{i}(X)=f_{i}(Z))=\left( \frac{1+\text{Sim}(X,Z)}{2} \right)^{\ell}\leq 0.9^{\ell} \leq 0.9^{\log_{1 / 0.9} n}\leq \frac{1}{n}$$
where the last inequality follows from $\log_{1 / 0.9}{1 / 0.95}\leq \frac{1}{2}$, we have that $\ell=\frac{\log_{1 / 0.9}n}{2\log_{1 / 0.9} 1 / 0.95}\geq \log_{1 / 0.9} n$.

Therefore, $$\mathbb{P}(\exists i:f_{i}(X)=f_{i}(Z))\leq \sqrt{ n }\cdot \frac{1}{n}=\frac{1}{\sqrt{ n }}$$and we have that: $$\mathbb{E}[T]\leq 1+\frac{n-1}{\sqrt{ n }}\leq \sqrt{ n }+1$$This proves the statement.

---
#### Problem 2
---
#### Problem 3
Let $G$ denote the multigraph. Let $C$ denote the size of the largest connected component of $G$. 

1. **Claim: $C\leq \log_{2}n$ with probability at least $1-\frac{1}{n}$.**
   For $k\in [n]$, let $S\subseteq V$ with $\left| S \right|=k$ where $k< m /2$. Then, $$\mathbb{P}(S\text{ is connected})\leq\mathbb{P}(e(G[S])\geq k-1)\leq \sum_{I\subseteq[m]:\left| I \right| =k-1}^{}\left( \frac{k}{n} \right)^{2(k-1)}\leq {m \choose k-1}\left( \frac{k}{n} \right)^{2(k-1)} $$
   
   Hence, we have that: $$\begin{align}\mathbb{P}(C\geq k)&\leq\sum_{S\subseteq V:|S|=k}^{}\mathbb{P}(S\text{ is connected})\\&\leq{n \choose k}{m \choose k-1}\left( \frac{k}{n} \right)^{2(k-1)}\\&\leq{n \choose k}{m \choose k}\left( \frac{k}{n} \right)^{2k}\\&\leq\left( \frac{ne}{k} \right)^k\left( \frac{n}{2ek} \right)^k\left( \frac{k}{n} \right)^{2k}\\&=\frac{1}{2^k}   \end{align}$$Further, $\mathbb{P}(C\leq \log n)\geq 1-\mathbb{P}(C \geq \log n)\geq 1-\frac{1}{n}$.

 $$\mathbb{P}(e(G[S])\geq k+1)\leq {m \choose k+1}\left( \frac{k}{n} \right) ^{2(k+1)}$$Hence, $$\mathbb{P}(\exists  |S|=k: e(G[S])\geq k+1)\leq{n \choose k}{m \choose k+1}\left( \frac{k}{n} \right) ^{2(k+1)}\leq \frac{1}{2^{k+1}}$$and $$\mathbb{P}(\exists S:e(G[S])> \left| S \right| )\leq \sum_{k=1}^{\log n} \frac{1}{2^{k+1}}=\frac{1}{2}\left(1-\frac{1}{n}  \right) $$
 Hence, $$\begin{align}\mathbb{P}(S\text{ connected}, e(G[S])> k)&=\end{align}$$

$$\mathbb{P}(S\text{ is connected})=\sum_{T\text{ MST on }S}^{}\mathbb{P}(T\subseteq E)=\sum_{T\text{ MST on }S}^{}{m \choose k-1} \frac{1}{n^{2(k-1)}}\leq k^{k-2}$$$$\begin{align}\mathbb{P}(S\text{ is connected and }e(G[S])>|S|)&=\sum_{T\text{ MST on }S}^{}\mathbb{P}(T\subseteq E)\\&=\sum_{T\text{ MST on }S}^{}{m \choose k+1} \frac{1}{n^{2(k-1)}}{k+1 \choose 2}\left( \frac{k}{n} \right) ^4\\&\leq \frac{k^{k+4}}{n^{2(k+1)}}{m \choose k+1} \end{align}$$Hence, $$\begin{align}\mathbb{P}(\exists S\text{ is connected and }e(G[S])> k)&\leq \left( \frac{en}{k+1} \right) ^{k+1}\left( \frac{n}{2e(k+1)} \right)^{k+1}\frac{k^{k+4}}{n^{2(k+1)}}\\&\leq \frac{k^{k+4}}{2^{k+1}(k+1)^{2(k+1)}}\\& \leq \frac{1}{2^{k+1}(k+1)^{k-2}}\end{align}$$Hence, $$$$

$$\mathbb{P}(C \geq k)\leq{n \choose k}{m \choose k} \frac{k^{k}}{n^{2k}}\leq \left( \frac{ne}{k} \right) ^k \left( \frac{n}{2ek} \right) ^k\left( \frac{k}{n^2} \right) ^{k}=\frac{1}{(2k)^k}$$
$e^{k\log 2k}=(2k)^k=n$ then $k\log 2k=\log n$
This time $C$ be the smallest connected with an edge. 

 
1. **Claim 2:**
   $$\begin{align}\mathbb{P}(\exists S\subseteq V:|S|=k\land S\text{ is connected}\land e(G[S])\geq k)&\leq\mathbb{P}(\exists S\subseteq V:|S|=k\land S\text{ is connected}\land e(G[S])\geq k)\end{align}$$ 
1. Claim: If for every subset $S\subseteq V$, we have that $e(G[S])\leq \left| S \right|$, then there exists an orientation with out-degree at most 1. 
	
	Suppose otherwise, i.e. for any orientation there exists a vertex with out-degree $\geq 2$. Let $\sigma$ be an orientation s.t. $\sum_{v:d_{+}(v)\geq 2}^{}d_{+}(v)$ is minimum. Let $u\in V$ s.t. $d_{+}(u)\geq 2$. Further, let $S:=\{ v\in V:v\text{ is reachable from }u \}$. 
	
	Then, we show that for any $v\in S$ s.t. $v\neq u$, we have that $d_{+}(v)\geq 1$. Suppose $d_{+}(v)=0$. Then, we can create another orientation where we reverse all edges on the $u$-$v$-path. Let $d'_{+}$ denote the new out-degrees. We have that $d'_{+}(u)=d_{+}(u)-1$, but $d'_{+}(v)=d_{+}(v)+1$ which is a contradiction. 
	
	Therefore, we conclude by showing that $e(G[S])\geq \left| S \right|+1$.


Hence, let $X_{i}$ be the indicator variable denoting if $i$-th edge is in $G[S]$. we have that: $$\mathbb{P}(e(G[S])\geq k+1)=\sum_{\ell=k+1}^{m}{m \choose \ell} \frac{k^{2p}}{n^{2p}}\cdot \left( 1-\frac{k^2}{n^2} \right)^{m-p} $$
$$\begin{align}\mathbb{P}(e(G[S])\leq k)&=\sum_{\ell=0}^{k}{m \choose \ell} \frac{k^{2\ell}}{n^{2\ell}}\cdot \left( 1-\frac{k^2}{n^2} \right)^{m-\ell} \\&\geq \sum_{\ell=0}^{k}\frac{m^{\ell}}{\ell^{\ell}}\left( \frac{k}{n} \right) ^{2\ell}e^{^{-2k^2(m-\ell)/n^2}}\end{align}$$ $$\mathbb{P}(e(G[S])=q)={m \choose q} \frac{k^2q}{n^2q}\left( 1-\frac{k^2}{n^2} \right)^{m-q}\leq $$


Let $e_{i}$ denote the $i$-th edge chosen. For any $\{ u,v \}\subseteq {V \choose 2}$, we have that $$\mathbb{P}(e_{i}=\{ u,v \})=\frac{2}{n^{2}}$$

$$\mathbb{P}(\{ u,v \}\in E)=\mathbb{P}(\exists i: e_{i}=\{ u,v \})\leq \frac{2m}{n ^{2}}\leq \frac{1}{ne^{2}}$$
We have that:
1. hihi
2. $$\mathbb{P}(\exists (u,v)\text{-path of length }d)\leq{n-2 \choose d-1} \left( \frac{1}{ne^2} \right)^d=\frac{n^{d-1}}{n^d e^{2d}}=\frac{1}{ne^{2d}} $$
3. We define the algorithm as follows:


```pseudo
\begin{algorithm} \caption{ComputeOrientation()} 
\begin{algorithmic}
\State $D\gets \varnothing$
\State $d_v\gets 0$ for all $v\in V$
\For {$i\in [m]$}
\State $u\gets$ sampled from $V$ uniformly.
\State $v\gets$ sampled from $V$ uniformly.
\If{$d_u=0$}
\State $D\gets D\cup\{u\to v\}$
\State $d_u\gets d_u+1$
\ElIf{$d_v=0$}
\State $D\gets D\cup\{v\to u\}$
\State $d_v\gets d_v+1$
\Else
\EndIf


\EndFor
\end{algorithmic}
\end{algorithm}
```


```pseudo
\begin{algorithm} \caption{UpdateOrientation()} 
\begin{algorithmic}
\State $D\gets \varnothing$
\State $d_v\gets 0$ for all $v\in V$
\For {$i\in [m]$}
\State $u\gets$ sampled from $V$ uniformly.
\State $v\gets$ sampled from $V$ uniformly.
\If{$d_u=0$}
\State $D\gets D\cup\{u\to v\}$
\State $d_u\gets d_u+1$
\ElIf{$d_v=0$}
\State $D\gets D\cup\{v\to u\}$
\State $d_v\gets d_v+1$
\Else
\EndIf


\EndFor
\end{algorithmic}
\end{algorithm}
```


Let $G$ have out-degree at most $1$. 