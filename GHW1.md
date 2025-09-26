### 1. Well-Spaced Subsets
1. (5min) Assume there is a well-spaced subset $S\subseteq V$ s.t. $\left| S \right|=k+1$ wlog. Note that for any $v\in S$, $N(v)\subseteq V \backslash S$ and $N(v)\cap N(w)=\varnothing$ for all $v,w\in S$. However, there are $3k-1$ vertices and $3k+3$ neighbors. Hence, there exists at least one vertex that is common by pigeonhole, contradiction.
2. Greedy algorithm. 
   ```pseudo
	\begin{algorithm}\caption{Greedy($I$)}
	\begin{algorithmic} 
	\State $S,B\gets \varnothing$
	\State $W,V \gets V(G)$
	\While{$V\neq\varnothing$}
	\State $u\gets\arg\min_{v\in W}|(D_1(v)\cup D_2(v))\backslash B|$
	\State $S\gets S\cup \{u\}$
	\State $V\gets V\backslash B_2(u)$
	\State $B\gets B\cup B_2(u)$
	\State $W\gets D_1(B)\backslash B$
	\EndWhile
	\end{algorithmic}
	\end{algorithm}
	```


   
	
   Let a vertex be **marked**
3. At each step, we add a vertex $v$ s.t. 
4. 
5. Add a vertex $v$ s.t. $N(v)\cap N(S)=\varnothing$ to $S$ until impossible. Let $v_{1},\dots,v_{p}$ be the vertices added in order. Then, $S$ is a well-spaced subset. 
	
	
   
   Now, for every $v\in V$, there exists $w\in S$ s.t. $d_{G}(v,w)\leq 2$. Let $f(v)$ be the one closest to $v$. However, for any $w\in S$, it can have at most $1+3+6=10$ vertices in its radius 2. Therefore, $$10p\geq 4k$$ and $p\geq \frac{2}{5}k$


o 

Let X be some finite set and F ⊆ 2 X be a family of polynomially (in |X |) many subsets of X . Every subset S ∈ F has at most k elements and has a positive reward rS. We consider the problem of finding a collection of disjoint subsets maximizing the total reward.