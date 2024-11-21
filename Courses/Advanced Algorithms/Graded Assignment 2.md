#Series #Algorithms 

#### Problem 1

1. Let $z\in \text{argmin}_{x\in X\cup Y}h_{j}(x)$. As there are no collisions in the hash function $h_{j}$, we have that $z$ is unique. Then, 
   1. if $z\in X\cap Y$. Then, $g_{j}(X)=h_{j}(z)=g_{j}(Y)$ and consequently $g_{j}(X)\equiv_{2}g_{j}(Y)$. Further,
	   $$\mathbb{P}(z\in X\cap Y)=\sum_{\ell\in X\cap Y}^{}\mathbb{P}(z=\ell)$$Let $A:=\{ a_{1},\dots,a_{\left| X\cup Y \right|} \}\subseteq [2(nU)^{100}]$ be ordered in an increasing order. Further, the consider the enumeration $X\cup Y=\{ x_{1},\dots,x_{\left| X\cup Y \right|} \}$.Then, for any permutation  $\sigma\in S_{\left| X\cup Y \right|}$, from the full independence of $h_{j}$, $$\mathbb{P}(h_{j}(x_{1})=a_{\sigma(1)},\dots,h_{j}(x_{\left| X\cup Y \right| })=a_{\sigma(\left| X\cup Y \right| )})=\left( \frac{1}{2(nU)^{100}} \right)^{\left| X\cup Y \right| }$$Therefore, the probability is constant over all permutations and we have via counting argument that: 
	   
	   $$\begin{align}\mathbb{P}(z=\ell\cap h_{j}(X\cup Y)=A)&=\mathbb{P}(z=\ell |h_{j}(X\cup Y)=A)\mathbb{P}(h_{j}(X\cup Y)=A)\\&=\frac{1}{\left| X \cup Y \right| }\mathbb{P}(h_{j}(X\cup Y)=A)\end{align}$$Summing over all possible $A$, $\mathbb{P}(z=\ell)=\frac{1}{\left| X\cup Y \right| }$ and we have that: $$\mathbb{P}(z\in X\cap Y)=\sum_{\ell\in X\cap Y}^{}\mathbb{P}(z=\ell)=\text{Sim}(X,Y)$$
   2. 
   3. $\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$. Hence, we have: $$\mathbb{P}(z\in X\cap Y\land g_{j}(X)\equiv_{2}g_{j}(Y))=\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$$
   4. if $z\notin X\cap Y$, then the probability that $g_{j}(X)\equiv_{2}g_{j}(Y)$ is the probability that the two minima of hash values having the same parity. $$\mathbb{P}(g_{1}(X)\equiv_{2}g_{j}(Y)|z\notin X \cap Y)$$
      
      Then,  $$\begin{align}\mathbb{P}(g_j(X)\equiv_{2}g_{j}(Y)\land z\notin X \cap Y)&=\frac{1}{2}(1-\text{Sim}(X,Y))\end{align}$$

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

Let $C$ be the smallest size $S$ s.t. $e(G[S])\geq k$ 

1. **Claim: $C\leq \log_{2}n$ with probability at least $1-\frac{1}{n}$.**
   For $k\in [n]$, let $S\subseteq V$ with $\left| S \right|=k$ where $k< m /2$. Then, $$\mathbb{P}(S\text{ is connected})\leq\mathbb{P}(e(G[S])\geq k-1)\leq \sum_{I\subseteq[m]:\left| I \right| =k-1}^{}\left( \frac{k}{n} \right)^{2(k-1)}\leq {m \choose k-1}\left( \frac{k}{n} \right)^{2(k-1)} $$
   
   Hence, we have that: $$\begin{align}\mathbb{P}(C\geq k)&\leq\sum_{S\subseteq V:|S|=k}^{}\mathbb{P}(S\text{ is connected})\\&\leq{n \choose k}{m \choose k-1}\left( \frac{k}{n} \right)^{2(k-1)}\\&\leq{n \choose k}{m \choose k}\left( \frac{k}{n} \right)^{2k}\\&\leq\left( \frac{ne}{k} \right)^k\left( \frac{n}{2ek} \right)^k\left( \frac{k}{n} \right)^{2k}\\&=\frac{1}{2^k}   \end{align}$$Further, $\mathbb{P}(C\leq \log n)\geq 1-\mathbb{P}(C \geq \log n)\geq 1-\frac{1}{n}$.

 $$\mathbb{P}(e(G[S])\geq k+1)\leq {m \choose k+1}\left( \frac{k}{n} \right) ^{2(k+1)}$$Hence, $$\mathbb{P}(\exists  |S|=k: e(G[S])\geq k+1)\leq{n \choose k}{m \choose k+1}\left( \frac{k}{n} \right) ^{2(k+1)}\leq \frac{1}{2^{k+1}}$$and $$\mathbb{P}(\exists S:e(G[S])> \left| S \right| )\leq \sum_{k=1}^{\log n} \frac{1}{2^{k+1}}=\frac{1}{2}\left(1-\frac{1}{n}  \right) $$
 Hence, $$\begin{align}\mathbb{P}(S\text{ connected}, e(G[S])> k)&=\end{align}$$

$$\mathbb{P}(S\text{ is connected})=\sum_{T\text{ MST on }S}^{}\mathbb{P}(T\subseteq E)=\sum_{T\text{ MST on }S}^{}{m \choose k-1} \frac{1}{n^{2(k-1)}}\leq k^{k-2}$$$$\begin{align}\mathbb{P}(S\text{ is connected and }e(G[S])>|S|)&=\sum_{T\text{ MST on }S}^{}\mathbb{P}(T\subseteq E)\\&=\sum_{T\text{ MST on }S}^{}{m \choose k+1} \frac{1}{n^{2(k-1)}}{k+1 \choose 2}\left( \frac{k}{n} \right) ^4\\&\leq \frac{k^{k+4}}{n^{2(k+1)}}{m \choose k+1} \end{align}$$Hence, $$\begin{align}\mathbb{P}(\exists S\text{ is connected and }e(G[S])> k)&\leq \left( \frac{en}{k+1} \right) ^{k+1}\left( \frac{n}{2e(k+1)} \right)^{k+1}\frac{k^{k+4}}{n^{2(k+1)}}\\&\leq \frac{k^{k+4}}{2^{k+1}(k+1)^{2(k+1)}}\\& \leq \frac{1}{2^{k+1}(k+1)^{k-2}}\end{align}$$Hence, $$$$

$$\mathbb{P}(C \geq k)\leq{n \choose k}{m \choose k} \frac{k^{k}}{n^{2k}}\leq \left( \frac{ne}{k} \right) ^k \left( \frac{n}{2ek} \right) ^k\left( \frac{k}{n^2} \right) ^{k}=\frac{1}{(2k)^k}$$
$e^{k\log 2k}=(2k)^k=n$ then $k\log 2k=\log n$
This time $C$ be the smallest connected with an edge. Then, $$\mathbb{P}(C \leq k)=$$ $$\sum_{k=\log n}^{\infty} \frac{1}{2^{k+1}}\leq \frac{1}{2^{\log n +1}}$$

 
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
\begin{algorithm} \caption{UpdateOrientation($G,u,v,\sigma$)} 
\begin{algorithmic}
\If {$d_\sigma^+(u)=0$}
\State $\sigma\gets \sigma\cup\{u\to v\}$
\ElIf{$d_\sigma^+(v)=0$}
\State $\sigma\gets \sigma\cup\{v\to u\}$
\Else
\State Find a reachable node $w$ from $u$ or $v$ w.r.t. $\sigma$ where $d^+_\sigma(w)=0$.
\If{$w$ is reachable from $u$}
\State Reverse the edges on the $u$-$w$-path in $\sigma$.
\State $\sigma\gets \sigma\cup\{u\to v\}$
\Else 
\State Reverse the edges on the $v$-$w$-path in $\sigma$.
\State $\sigma\gets \sigma\cup\{v\to u\}$
\EndIf
\EndIf
\Return $\sigma$
\end{algorithmic}
\end{algorithm}
```


Let $G$ have out-degree at most $1$. 

$$\begin{align}\mathbb{P}(\exists S\subseteq V:\left| S \right| =k,e(G[S])\geq 2k)&\leq{n \choose k}{m \choose 2k}\left( \frac{k}{n} \right)^{4k}\\&\leq \left( \frac{ne}{k} \right) ^k\left( {\frac{n}{4ek}} \right) ^{2k}{\frac{k^{4k}}{n^{4k}}}\\&\leq\left( \frac{k}{n} \right)^k\end{align} $$Then, $$\mathbb{P}(\exists S\subseteq V: e(G[S])\geq 2|S|)\leq \sum_{k=1}^{n / 4e^2}\left( \frac{k}{n} \right) ^k$$
We have: $$\begin{align}\mathbb{P}(\exists S\subseteq V:\left| S \right| =k,e(G[S])\geq k+1)&\leq{n \choose k}{m \choose k+1}\left( \frac{k}{n} \right)^{2(k+1)}\\&\leq \left( \frac{ne}{k} \right) ^k\left( \frac{k}{n} \right)^{2(k+1)} {m \choose k+1}\\&\leq \frac{e^kk^{k+2}}{n^{k+2}}\frac{m^{k+1}}{(k+1)!}\\&\leq \frac{e^kk^{k+2}}{n^{k+2}}\frac{n^{k+1}}{2^{k+1}e^{2(k+1)}(k+1)!}\\&\leq \frac{e^kk^{k+2}}{n^{k+2}}\frac{n^{k+1}e^k}{2^{k+1}e^{2(k+1)}(k+1)k^k}\\&\leq \frac{k}{2^{k+1}n}\end{align} $$We have that: $$\sum_{k=1}^{n} \frac{k}{2^{k+1}n}\leq \frac{1}{2n}\sum_{k=1}^{\infty} \frac{k}{2^k}=\frac{1}{n}$$where: $$\sum_{k=1}^{\infty} \frac{k}{2^k}=\sum_{k=1}^{\infty}\sum_{j=1}^{k} \frac{1}{2^k}=\sum_{j=1}^{\infty}\sum_{k=j}^{\infty} \frac{1}{2^k}=\sum_{j=1}^{\infty} \frac{1}{2^{j-1}}=2$$

$${m \choose k+1}\left( \frac{k}{n} \right) ^{2(k+1)}\leq \frac{m^{k+1}}{(k+1)!}\left( \frac{k}{n} \right)^{2(k+1)} \leq \frac{m}{k}\cdot \left( \frac{em}{k} \right)^k \left( \frac{k}{n} \right) ^{2(k+1)}\leq \frac{n}{2k}\cdot \left( \frac{n}{2ek} \right)^k \left( \frac{k}{n} \right) ^{2(k+1)}$$Then, 

---
### Problem 4

Assume that there exists a randomized streaming algorithm with space complexity $o(m)$ that solves the 3-coloring validation problem w.h.p. 

We reduce INDEX to 3-Coloring validation problem as follows. 
1. Alice has $x\in\{ 0,1 \}^n$ and Bob has $i\in[n]$. 
2. Alice constructs a graph $G:=(V,E)$ where:
	- $V:=[n]\cup \{ \text{zero},\text{one} \}$
	- $E:=\{ \{ \text{zero},i \}:x_{i}=0 \}\cup\{ \{ \text{one},i \}:x_{i}=1 \}$

---

Have to sample all edges w.h.p
<=> For each $e\in E$, there exists a triangle that contains $e$ given in distance $n$.
Sample one of them uniformly. 

Let $\mathcal{T}$ be the set of triangles with distance $\leq n$. $\mathcal T(e):=\{ T\in \mathcal{T} :e\in T\}$. Then, $1\leq\left| \mathcal{T}(e) \right|\leq n-2$ for all $e$. Further, $$p:=\left| \mathcal{T} \right| =\frac{1}{3}\sum_{e\in E}^{}\left| \mathcal{T}(e) \right| $$Hence, $m / 3\leq p\leq m(n-2) /3$
Let $F$ be the set of wrong edges and $\mathcal{S}$ be the set of triangles $A$ samples. THen, 

1. if $|F|\geq 1$, $$\mathbb{P}(\mathcal{A}\text{ is wrong})=\mathbb{P}\left( \forall T\in \mathcal{S}:  T\notin \bigcup_{e\in F}^{} \mathcal{T}(e) \right)=\left(\frac{ p-\left| \bigcup_{e\in F}^{}\mathcal{T}(e) \right| }{p} \right)^\ell \leq  $$
   
   $$\mathbb{P}(\mathcal{A}\text{ is wrong})=\mathbb{P}\left(\text{\#right triangles}\geq  k\right)= $$

2. if 
we have that $$\left| \bigcup_{e\in F}^{}\mathcal{T}(e) \right|=\sum_{e\in F}^{}\left|  \mathcal{T}(e)\right|  $$

If $c$ is not valid, let $\mathcal{T}$ be the set of wrong triangles with size $t$. 
$$\mathbb{P}(A\text{ is wrong})=\mathbb{P}(A\text{ didn't choose from }\mathcal{T})=\left( \frac{m-k}{m} \right) ^\ell$$


---
For each triangle,
```pseudo
\begin{algorithm} \caption{3ColorVerfication($S$)} 
\begin{algorithmic}
\State $U\gets {n \choose 3}$ //upper bound of the number of triangles
\State $h:[U]\to [U]\gets$ uniform, 2-wise independent random hash function 
\For{$e_i\in S$}
\State Find a
\EndFor
\Return $\sigma$
\end{algorithmic}
\end{algorithm}
```

---

$\text{XOR}_{v}:=\sum_{T\ni v}^{}\text{XOR}_{T}$



For each color $c$, $$\text{XOR}_{c}=\bigoplus_{x:c(x)=c} \text{XOR}_{x}=\bigoplus_{x:c(x)=c} \bigoplus_{T\ni x}  \text{XOR}_{T}$$

Red = 001 000

If $c$ is valid, then for every $T\in \mathcal{T}$, there exists exactly $x\in T$ with $c(x)=c$. Therefore, $$\text{XOR}_{c}=\bigoplus_{T\in \mathcal{T}}\bigoplus_{c\in T} \text{XOR}_{T}=  \bigoplus_{T\in \mathcal{T}}\text{XOR}_{T}$$ 
If $c$ is not valid, then there exists $T\in \mathcal{T}$ with no $c$ in it. Then, $$\text{XOR}_{c}=\bigoplus_{x:c(x)=c} $$ 

$n^{2}$. 

---
##### Problem 2

Assume that there exists a deterministic streaming algorithm $A$ in the setting that estimates the frequency of integers in an $N$-length stream of integers from $[n]$ up to an additive error of $\varepsilon N$ with space complexity $\text{o}(\log (n) / \varepsilon)$, where $N=\text{poly}(n)$.

Then, for $\varepsilon=1 / 2$, $A$ has a space complexity of $\text{o}(\log (n))$. This is a contradiction to the result from exercise 4 of problem set 6. 


For any item $i\in[n]$, $f_{i}\in$

---
Let $n$ and $\varepsilon$ be fixed and consider an arbitrary deterministic frequency estimation algorithm $A$ that uses at most $m:=\left\lfloor c \log(n) / \varepsilon\right\rfloor$ bits. Let $N:=\text{poly}(n)$. We claim that the additive error is larger than $\varepsilon N$.

For $k\in \mathbb{N}$, let $N_{k}:=\left\lceil \frac{k(n-1)}{(1-\varepsilon)}\right\rceil$. Then, consider: $$S_{i,k}:=\underbrace{ T,\dots,T }_{ k\text{ times} }, \underbrace{ i,\dots, i }_{ N_{k}-k(n-1)\text{ times} }$$
Then, there are 
Let $k:=\left\lfloor (1-\varepsilon)N /(n-1)\right\rfloor$ and consider a stream $T$ of length $(n-1)k$ where $\{ 0,\dots,n-2 \}$ appear $k$ times each. We now define a set of streams $S_{0},\dots,S_{n-1}$ where: $$S_{i}:=T,\underbrace{ i,...,i }_{ N-(n-1)k \text{ times}},\quad \forall i\in[n]$$

If $c\leq \varepsilon \log^{2}(n)$ then $2^m< n^{\log^2(n)}$ there are two states with the same state. Then, in one its $0$ in the other i

There are $n$ different states. 

Hence, for any $n$ we have that:  $$\frac{f_{n}}{\log (n) / \varepsilon}\geq \frac{1}{2\log (n)}$$



$c_{a}=c_{z}$ however $f_{a}=\frac{(1-\varepsilon )N}{n-1}+\varepsilon N$ times and in 2 $f_{z}=\varepsilon N$. If $A$ has additive error at most $\varepsilon N$, then $c_{a}\in[0,2\varepsilon N]$ however,  $$\frac{(1-\varepsilon)N}{n-1}+\varepsilon N-c_{a}\geq  \frac{(1-\varepsilon)N}{n-1}-\varepsilon N=N\left( \frac{1-\varepsilon-\varepsilon(n-1)}{n-1}\right) $$

Then, $a:\{ 0,1 \}^{m}\to \mathbb{N}^{n}$.

---
Consider the set of all permutations $S_{n}$. We have then, $$N:=n^3$$

Then,   


Consider the set of inputs $\mathcal{S}$ where

---
##### Problem 2
2a) we have that: $$\mathbb{E}[\sigma(j)Z]=\mathbb{E}\left[ \sum_{i\in[j]}^{}\sigma(j)\sigma(i)f_{i} \right]=\sum_{i\in[j]}^{}\mathbb{E}[\sigma(j)\sigma(i)]f_{i}=\mathbb{E}[\sigma(j)^{2}]f_{j}+\sum_{i\neq j}^{}\mathbb{E}[\sigma(j)]\mathbb{E}[\sigma(i)]f_{i}=f_{j}$$
2b) we have that: $$\begin{align}\text{Var}(\sigma(j)Z)&\leq\mathbb{E}[\sigma(j)^{2}Z^{2}]=\mathbb{E}[Z^{2}]=\left\| f \right\| _{2}^2\end{align}$$
3) We have that: $$\begin{align}\mathbb{E}[\sigma(j)Z_{h(j)}]&=\mathbb{E}\left[ \sum_{i\in[j]}^{}\sigma(j)\sigma(i) f_{i}\cdot \mathbb{1}_{h(i)=h(j)}\right] \\&=\sum_{i\in[j]}\mathbb{E}[\sigma(j)\sigma(i)\mathbb{1}_{h(i)=h(j)}]f_{i}\\&=\sum_{i\in[j]}\mathbb{E}[\sigma(j)\sigma(i)|h(i)=h(j)]\mathbb{P}(h(i)=h(j))f_{i}\\&=\mathbb{E}[\sigma(j)^{2}]f_{j}+\sum_{i\neq j}^{}\mathbb{E}[\sigma(i)\sigma(j)|h(i)=h(j)] \frac{f_{i}}{k}\\&=f_{j}+\sum_{i\neq j}^{}\mathbb{E}[\sigma(i)\sigma(j)|h(i)=h(j)] \frac{f_{i}}{k}\end{align}$$
where for $i\neq j$: $$\begin{align}\mathbb{E}[\sigma(i)\sigma(j)|h(i)=h(j)]&=\mathbb{P}(\sigma(i)=\sigma(j)|h(i)=h(j))-\mathbb{P}(\sigma(i)\neq\sigma(j)|h(i)=h(j))\\&=\end{align}$$

$$X\bot Y \implies \mathbb{E}[X \mathbb{1}_{Y=k}]=\mathbb{E}[X]\cdot \mathbb{P}(Y=k)$$

$$\mathbb{E}[X\cdot  \mathbb{1}_{Y=k}]=\mathbb{E}[X|Y=k]\cdot \mathbb{P}(Y=k)=$$
We have that: $$\begin{align}\text{Var}(\sigma(j)Z_{h(j)})\le \mathbb{E}[\sigma(j)^{2} Z_{h(j)}^{2}]-f_{j}^{2}&=\mathbb{E}[Z^{2}_{h(j)}]-f_{j}^{2}\\&=\mathbb{E}\left[ \sum_{i,i'\in[n]}^{}\sigma(i)\sigma(i')f_{i}f_{i'}\mathbb{1}_{h(i)=h(j)=h(i')} \right]-f_{j}^{2}\\&=\sum_{i,i'\in[n]}^{}\mathbb{E}\left[ \sigma(i)\sigma(i') \right] \mathbb{P}(h(i)=h(j)\land h(i')=h(j))f_{i}f_{i'}\\&=f_{j}^{2}+\frac{1}{k}\sum_{i\neq j}f_{i}^{2}-f_{j}^{2}\\&\le \frac{\|f\|^{2}_{2}}{k}\end{align}$$where for any $i,i'\in[n]$, $$\mathbb{P}(h(i)=h(j)\land h(i')=h(j))\le $$

---

```pseudo
\begin{algorithm} \caption{Estimate($S=\{a_1,...,a_m\}$)} 
\begin{algorithmic}
\State $k\gets $ a prime between $\lceil\varepsilon^{-2}\rceil\le k\le 2\lceil\varepsilon^{-2}\rceil$
\State $h:[n]\to [k]$ be a uniform pairwise independent hash function
\State $\sigma:[n]\to \{+1,-1\}\gets$ a uniform 4-wise independent hash function
\State $Z_0,....,Z_{k-1}\gets 0$
\For{$a_i\in S$}
\State $Z_{h(a_i)}\gets Z_{h(a_i)}+\sigma(a_i)$
\EndFor
\Return $\sigma(j)Z_{h(j)}$ for each $j\in[n]$.
\end{algorithmic}
\end{algorithm}
```

If $t\geq 24\log n$ then:

For any $j\in[n]$ we have: $$\mathbb{P}(\left| \sigma(j)Z_{h(j)}-f_{j} \right|> \varepsilon \|f\|_{2} )\leq \frac{\left\| f \right\| ^2_{2}}{k \varepsilon^{2}\|f\|^2_{2}}\leq \frac{1}{4}$$Then, by the median trick, we have: $$\mathbb{P}(\text{Fail predicting }f_{j})=\mathbb{P}\left( X\geq \frac{t}{2} \right)=\mathbb{P}\left( X\geq 2 \mathbb{E}[X]\right) \leq \exp \left( -\frac{t}{12} \right)\leq \frac{1}{n^{2}} $$, $$\mathbb{P}(\exists j\in[n]:\left| \sigma(j)Z_{h(j)}-f_{j} \right|> \varepsilon f_{j})\leq \left\| f \right\| ^2_{2}\sum_{j\in [n]}^{} \frac{1}{f^{2}_{j}}=\left( \sum_{j\in[n]}^{}f^2_{j} \right) \left( \sum_{j\in[n]}^{} \frac{1}{f^2_{j}} \right) $$$$\sum_{j\in[n]}^{} \frac{1}{1-(1-f^2_{j})}\leq \sum_{j\in[n]}^{}1+2(1-f^2_{j})=\sum_{j\in[n]}^{}(3-2f^2_{j})=3n-2\|f\|^2_{2}$$
$$\mathbb{P}(\forall j\in[n]:\left| \sigma(j)Z_{h(j)}-f_{j} \right|\leq \varepsilon \|f\|_{2} )\geq \left( 1- \right) $$

$$\text{O}(\log n+\log \varepsilon^{-2})$$

if $n\leq \frac{1}{\varepsilon^{2}}$ then 

---
##### 2.1
Let $\varepsilon(n)\in(n^{-0.99},1)$ be any function. Fix $n$ and consider an arbitrary frequency estimation algorithm that uses at most $m:=\left\lfloor c\log (n) / \varepsilon(n)\right\rfloor$ bits where $c< \varepsilon(n)(n-1)$. We claim that the additive error is larger than $\varepsilon N$. 

As $1-\varepsilon(n)> 0$, there exists $t\in \mathbb{N}$ s.t. $1-\varepsilon(n)>n^{-t}$. Let $N:=n^{t+1} /2$. Then, we get two size $\frac{n}{2}$ sets $A,B$ and consider $A,x,\dots,x$ and $B,x,\dots,x$.



Then, $n^{-t}$ times $A$ and $B$ and for $N-$
$$(1-\varepsilon)N > \frac{n}{2}$$


Let $S\subseteq[n]$ be a fixed subset with size $n/3$.  

Let $\mathcal{A}:=\{ A\dots A:A\in \mathcal{S} \}$ for $\frac{2}{n-1}$ times. Then, we need that: $$$$$$\varepsilon(n)\frac{kn}{3}\leq \frac{k}{2}$$and $k\left( \frac{n}{3}-\frac{1}{2} \right)\leq 0$

We have ${n \choose n / 2}\geq \frac{2^n}{n+1}\geq 2^{n-\log(n)-1}$. Or we have ${n \choose n / 2}\geq 2^{n / 2}$ and set

Let $c=\frac{n\varepsilon(n)}{2\log n}$ or $c$

Let $k=\left\lfloor(1-\varepsilon)n\right\rfloor$. Then, ${n \choose k}\geq \left( \frac{1}{1-\varepsilon} \right)^{(1-\varepsilon)n}\geq \left( \frac{1}{1-n^{-0.99}} \right)^{n}$

Let $k=\left\lfloor \varepsilon n\right\rfloor$. Then, ${n \choose k}\geq \left( \frac{1}{\varepsilon} \right)^{\varepsilon n}\geq$

$N=(1-\varepsilon)N+\varepsilon N$. 

$(1-\varepsilon)N=\frac{n}{2},N=\frac{n}{2(1-\varepsilon)}$$$1-\varepsilon\leq 1-n^{-0.99}\leq 1-\frac{1}{n}$$
$$\frac{n}{n-1}$$$\left( 1+\frac{2}{n-1} \right)^n\geq e^{n/n-1}\geq 2^{n/ n-1}$. Hence, let $c=\frac{n\cdot \varepsilon(n)}{(n-1)\log n}$

Let $k=\left\lfloor(1-\varepsilon)n\right\rfloor$. Then, $${n \choose k}\geq {\left( \frac{n}{k} \right)^{k}}\geq\left( \frac{1}{1-\varepsilon}\right)^{(1-\varepsilon)n-1} \geq \left( \frac{n}{n-1} \right) ^{(1-\varepsilon)n-1}$$if $$1\geq 2-2\varepsilon$$$$2\varepsilon\geq 1$$

If $\varepsilon\geq \frac{1}{2}$, then: $${n \choose k}\geq 2^{(1-\varepsilon)n-1}$$

$$\left( \frac{n}{k} \right)^k=2^{k(\log n-\log k)}=2^{}$$

Let $\left\lfloor(1-\varepsilon)N\right\rfloor=\frac{n}{2}$. Then, $(1-\varepsilon)N$ $$N=\frac{n}{2(1-\varepsilon)}$$Then, we have that: $$2^{n / 2}\geq 2^{}$$where $c<\frac{n\varepsilon(n)}{2\log n}$

$$\forall \varepsilon \forall A\in \text{Stream}:\left( \text{A good} \to A\notin o\left(\frac{\log n}{\varepsilon_{n}} \right)   \right)$$


$$\forall \varepsilon \forall A\in \text{Stream}:\left( \forall \delta \exists n_{0}\forall n\geq n_{0}:\text{SPACE}(A(n))<\frac{\delta \log n}{\varepsilon _{n}}\to \exists n \exists N\in \text{poly}(n)\exists j:\left| A(j)-f_{j} \right|> \varepsilon_{n}N  \right)$$

---

Let $\varepsilon(n)=1-2^{-n}$. We want to show that there exists a valid streaming algorithm in $\text{o}(\log n / \varepsilon_{n})$. Uses $m<\log \log n$ bits. Then there are at most $\log_{2}x$ different inputs. 


---
$N\in n^{O(1)}$
$t:\mathbb{N}\to \mathbb{N}$ s.t. $1-\varepsilon(n)\geq n^{-t(n)}$ for all $n$ Then, $N$


Let $\varepsilon(n)\in (n^{-0.99},1)$ be arbitrary and let $A$ be any deterministic streaming algorithm. For any $n$ we will show that if $A$ uses at most $m=\left\lfloor c \log(n) / \varepsilon(n)\right\rfloor$ bits for $c<\min\left\{ \frac{n\cdot \varepsilon(n)}{2\log(n)}, \frac{1}{2} \right\}$ then there exists an input for which it fails.

If $\varepsilon(n)\geq 1- \frac{1}{n}$, then  $A$ uses less than $\log(n) / 2\varepsilon(n)< \log(n)$ bits. Then, consider the $n$ streams of length 1.  Then, $$\left|  \right| $$

as $A$ is deterministic $n$

If $\varepsilon(n)\geq \frac{1}{2}$, then $A$ uses at most 

If $\varepsilon(n)\geq \frac{1}{2}$ then $A$ uses less than $\log(n)$ bits. 

Let $N$ and $M$ be the different lengths where $N>M$. Then, we need that $$N-M>\varepsilon(n)\cdot (N+M)$$$$N>\frac{\varepsilon}{1-\varepsilon} M$$

If $\varepsilon(n)\geq (1-\frac{1}{n})$ then $1-\varepsilon\leq \frac{1}{n}$ and 

$$\left\lfloor(1-\varepsilon)n\right\rfloor = 0 $$

$n$ $1$
$\frac{\log \log n}{n\log n}$ $n-1$

We have $<n$ outputs it can give. Let $a_{1},\dots,a_{n}$ be the outputs. 

i
j

Let $x,y\in \{ 0,1 \}^n$. Then, Alice creates a stream

We need that $$N\geq 1+\left\lfloor 2\varepsilon N\right\rfloor > 2\varepsilon N$$
$0> (2\varepsilon(n)-1)N$

$N\geq\varepsilon(n)(N+M)$ then $N>\frac{\varepsilon(n)}{(1-\varepsilon(n))}M$

let $\varepsilon(n)=\left( 1-2^{-n} \right)$. Then, if $N(n)$, we have that $(1-2^{-n})N(n)\geq$

Then, if $$\text{SPACE}(A(n))\cdot \frac{2^n-1}{2^n\log n}$$


Let $\varepsilon(n)=(1-2^{-n})$. Let $A$ be a streaming algorithm that outputs 1. Then, for any $n\geq$

If $\varepsilon(n)\geq 1-n^{-2}$, then: $$m\leq c\log n\cdot \frac{n^2}{n^2-1}$$Assume that $m\leq \frac{\log n}{n}$. Then, $n^{1/n}< 2$ different configurations. Then, let: $$1$$ and $$\frac{\varepsilon(n)}{1-\varepsilon(n)}\leq \frac{\varepsilon(n)}{}$$

$1-\varepsilon(n)\leq n^{-2}$ and $1-\varepsilon(n)\geq n^{-t(n)}$ then: $$n^{-t(n)}$$

$$\frac{cn^2\log n}{n^2-1}<$$

$$\frac{\frac{\log n}{n}}{\frac{n^{2}\log n}{n^{2}-1}}=\frac{n^{2}-1}{n^{3}}=\frac{1}{n}-\frac{1}{n^{2}}$$$$\left(\log n \right) $$

when is $n^{x}<2$ then $x=\log_{n}2 = \frac{1}{\log n}$. 

