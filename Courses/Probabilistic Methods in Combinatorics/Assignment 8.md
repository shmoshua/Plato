#Series #ProbabilisticMethods 

##### Problem 1
Color each cell independently randomly and uniformly. Let $S$ be a sequence of operations of row/column color switches. Notice that:
1. the order of the switch does not matter. 
1. if we switch the same row/column twice, we return back to the same.

Therefore, we may wlog consider $S\in\{ 0,1 \}^{2n}$ where $S_{i}=1$ if and only if $i$-th row/column is switched. Let $X_{1},\dots,X_{n^{2}}\in \{ +1,-1 \}$ where $X_{i}=1$ if and only if $i$-th cell is red in the initial configuration. Now, $Y^S_{i}\in \{ +1,-1 \}$ depending on the outcome after $X_{i}$. Let $Y^S:=\sum_{i}^{}Y^S_{i}$. Then, for a fixed $S$, $$\mathbb{P}\left( \text{\#red cells }> \frac{n^{2}}{2}+\sqrt{ \frac{\ln 2}{n} }n^2 \right)=\mathbb{P}\left( Y^S> 2\sqrt{ \frac{\ln 2}{n} }n^{2} \right)< \exp \left( -2 n\ln 2 \right) =2^{-2n}$$Hence, $$\mathbb{P}\left( \exists S:\#\text{red cells}>\frac{n^{2}}{2}+\sqrt{ \frac{\ln 2}{n} }n^2  \right) <1$$


---
##### Problem 2
We have that:
1. We will show that w.h.p. $\alpha(G)\leq 10 \log_{2}n$. Let $k=\left\lceil10 \log_{2}n\right\rceil$. Then, $$\begin{align}\mathbb{P}\left(\exists S\in {V \choose k}:S\text{ is independent}\right) &\leq{n \choose k} \frac{1}{2^{k \choose 2}}\leq \frac{e^kn^k}{k^k}2^{-k(k-1) /2}=\left( \frac{e n}{k 2^{-(k-1)/2}} \right)^k\\&=\left( \frac{\sqrt{ 2 }e n}{k 2^{k/2}} \right)^k\leq\left( \frac{\sqrt{ 2 }e}{10  n^4\log_{2}n} \right)^k=o(1)\end{align} $$Hence, we have that w.h.p $\chi(G)\geq n / \alpha(G)\geq n/10 \log_{2} n$.
2. Let $S$ be a set of $m\geq 100\ln n$ vertices. Then, $$\mathbb{P}\left( \left| E(G[S]) \right|> \frac{2}{3}{m \choose 2} \right)\leq \exp \left( -\frac{m(m-1)}{36} \right) $$Now, let $T\subseteq S$ be a randomly chosen subset of $\ell$ vertices. Then, $$\mathbb{E}[e(T)]=\sum_{e\in E(S)}^{}\mathbb{P}(e\in E(T))=\frac{e(S){m-2 \choose \ell-2}}{m \choose \ell}=e(S) \frac{{\ell \choose 2}}{m \choose 2}$$Therefore, if we set $\ell=\left\lceil 100 \ln n\right\rceil$, there exists $T\subseteq S$ with $e(T)\geq e(S){\ell \choose 2}/{m \choose 2}> \frac{2}{3}{\ell \choose 2}$ if $e(S)> \frac{2}{3}{m \choose 2}$. Hence, by union bound our probability is at most: $${n \choose \ell}\exp \left( -\frac{\ell(\ell-1)}{36} \right)\leq \left( \frac{en}{\ell e^{-(\ell-1) / 36}} \right)^\ell\leq  $$