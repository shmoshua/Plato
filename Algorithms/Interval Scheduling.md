#Definition #Algorithms 

> [!definition]
> Let $\{ a_{i},b_{i} \}_{i\in[N]}\subseteq \mathbb{R}$ be $N$ intervals s.t. $a_{i}\leq b_{i}$. The ***interval scheduling problem*** is given by: $$\max\{ |S|: S\subseteq[N], \forall i,j\in S: b_{i}\leq a_{j} \lor b_{j}\leq a_{i}\}$$
---
##### Properties
> [!lemma] Theorem 1 (Greedy)
> Consider the algorithm:
> ```pseudo
> \begin{algorithm} \caption{Greedy($I$)}
> \begin{algorithmic}
> \State $S\gets 0$
> \State $\ell \gets \min a_{i}$
> \State Sort $b_{1},\dots,b_{N}$ s.t. $b_{i}\leq b_{i+1}$.
> \For{$i\in[N]$}
> \If{$a_{i}\ge \ell$}
> \State $S\gets S+1$
> \State $\ell\gets b_{i}$
> \EndIf
> \EndFor
> \Return $S$
> \end{algorithmic}
> \end{algorithm}
> ```
> This algorithm solves the interval scheduling problem in $\text{O}(N\log N)$. 

> [!proof]-
> Let $i_{1},\dots,i_{n}$ be the indices of the jobs chosen by the algorithm and let $j_{1},\dots,j_{m}$ be the indices of the optimal solution sorted by $b$. 
> 
> We claim that for all $k\leq n$, $b_{i_{k}}\leq b_{j_{k}}$. If $k=1$, the claim holds. For $k>1$, assume that $b_{i_{k}}> b_{j_{k}}$. Then, by the algorithm $j_{k}< i_{k}$  and it must happen that $a_{j_{k}}<b_{i_{k-1}}\leq b_{j_{k-1}}$ which is a contradiction to the validity of the optimal solution. 
> 
> Now, assume that $n<m$. Then, have that $b_{i_{n}}\leq b_{j_{n}}\leq a_{j_{n+1}}$ which is a contradiction as by the algorithm we have that $a_{j_{n+1}}< b_{i_{n}}$. 
> 
> The runtime is just sorting the points $\text{O}(N\log N)$.

---
