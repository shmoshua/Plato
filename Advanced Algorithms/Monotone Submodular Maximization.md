#Definition #Algorithms 

> [!definition]
> Let $\mathcal{U}=[n]$ and $f:\mathcal{P}(\mathcal{U})\to \mathbb{R}^+$ where $f$ is:
> 1. **monotone**: $f(S)\leq f(T)$ for all $S\subseteq T$ and
> 2. **submodular**: $f(S\cup \{ i \})-f(S)\geq f(T\cup \{ i \})-f(T)$ for all $S\subseteq T$ and $i\in [n]$

---
##### Properties
> [!lemma] Theorem 1 (Greedy Algorithm)
>    ```pseudo
>    \begin{algorithm} \caption{Greedy($\mathcal{U},f,k$)} 
>    \begin{algorithmic}
>    \State $S\gets \empty$
>    \For{$i\in [k]$}
>    \State Pick $j\in \arg\max_{u\in \mathcal{U} \backslash S}f(S\cup \{ u \})$
>    \State $S\gets S\cup \{ j \}$
>    \EndFor
>    \Return $\mathcal {B}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```

1. For $k$, there is always an optimum with $k$ elements. 
2. Let $\varphi:\mathcal{U}\times \mathcal{P}(\mathcal{U})\to \mathbb{R}_{\geq 0},(u,S)\mapsto f(S\cup \{ u \})-f(S)$.
3. Let also $u_{i}$ denote the element chosen at step $i$ by Greedy.
4. Let $S^k_{\text{OPT}}$ be the optimum set with size $k$, $S^k$ be the set after $k$-th for loop. Let also $\varphi$
	$$f(S^k_{\text{OPT}})\leq f(S_{\text{OPT}}^k \cup S^k)\leq f(S^k) +\sum_{j\in S_{\text{OPT}}^k \backslash S^k}^{}\underbrace{ \varphi_{j}(S^k) }_{  \varphi_{u_{k+1}}(S^k)}\leq f(S^k)+k\cdot \varphi_{u_{k+1}}(S^k)$$Therefore, $${f(S^k_{\text{OPT}})-f(S^k)}\leq k\cdot \varphi_{u_{k+1}}(S^k)=kf(S^{k+1})-kf(S^k)$$Hence, $f(S_{\text{OPT}})\leq \ell f(S^{\ell+1})-(\ell-1)f(S^\ell)$ for all $\ell\geq k$. Therefore, $$\begin{align}\frac{f(S^k)}{f(S^{\text{OPT}})}&\geq \frac{f(S^k)}{k f(S^{k+1})-(k-1)f(S^{k})}\\&=1- \frac{f(S^{k+1})-f(S^k)}{ f(S^{k+1})-\frac{k-1}{k}f(S^{k})}\end{align}$$
	
	
	Also, $$f(S^k)=\sum_{i=1}^{k}\varphi_{u_{i}}(S^{i-1})\geq \max_{u\in \mathcal{U}}f(u)+\sum_{i=2}^{k}\frac{f(S^{i-1}_{\text{OPT}})-f(S^{i-1})}{i-1}$$