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

> [!proof]+
> Without loss of generality, we may assume that $f(\varnothing)=0$. Now, we define the gain function as: $$\varphi:\mathcal{U}\times \mathcal{P}(\mathcal{U})\to \mathbb{R}_{\geq 0},\quad (u,S)\mapsto f(S\cup \{ u \})-f(S)$$Now, let $u_{i}$ denote the element chosen at step $i$ by Greedy algorithm. Furthermore, let $T^k$ denote the optimum set with size $k$ and let $S^k:=\{ u_{1},\dots,u_{k} \}$. Then, 
> 1. **Claim 1: $f(A\cup B)\leq f(A)+\sum_{i\in B \backslash A}^{}\varphi_{i}(A)$**
>    We show this over induction over $\left| B  \backslash A\right|$. If $\left| B  \backslash A\right|=1$, then $$f(A)+f(A\cup \{ i \})-f(A)=f(A\cup \{ i \})=f(A\cup B)$$
>    For $\left| B  \backslash A \right|>1$ let $i\in B \backslash A$. Then, we have that: $$\begin{align}f(A\cup B)=f(A\cup B\backslash\{ i \}\cup \{ i \})&\leq f(A\cup B \backslash\{ i \})+\underbrace{ \varphi_{i}(A \cup B \backslash\{ i \}) }_{ \leq\varphi_{i}(A) }\\&\leq f(A)+\sum_{j\in B \backslash A, j\neq i}^{}\varphi_{j}(A)+\varphi_{i}(A)\end{align}$$which proves the claim.
>    
>  Therefore, $$f(T^k)\leq f(T^k\cup S^k)\leq f(S^k)+\sum_{j\in T^k \backslash S^k}^{}\varphi_{j}(S^k)\leq f(S^k)+k\varphi_{u_{k+1}}(S^k)$$as $\varphi_{u_{k+1}}(S^k)=f(S^{k+1})-f(S^k)$, we get that $f(T^k)-f(S^k)\leq kf(S^{k+1})-kf(S^k)$.$$f(T^k)-f(S^k)\leq kf(T^{k+1})-kf(S^k)$$
> 

1. $f(T^{k+1})\geq f(S^{k+1})\geq f(S^k)$, $f(T^{k+1})\geq f(T^k)\geq f(S^k)$
 
1. For $k$, there is always an optimum with $k$ elements. 
2. Let $\varphi:\mathcal{U}\times \mathcal{P}(\mathcal{U})\to \mathbb{R}_{\geq 0},(u,S)\mapsto f(S\cup \{ u \})-f(S)$.
3. Let also $u_{i}$ denote the element chosen at step $i$ by Greedy.
4. $f(S_{\text{OPT}}^{k+1})\geq f(S^{k+1})\geq f(S^k)$ and $f(S^{k+1}_{\text{OPT}})\geq f(S^k_{\text{OPT}})\geq f(S^k)$
5. Let $S^k_{\text{OPT}}$ be the optimum set with size $k$, $S^k$ be the set after $k$-th for loop. Let also $\varphi$
	$$f(S^k_{\text{OPT}})\leq f(S_{\text{OPT}}^k \cup S^k)\leq f(S^k) +\sum_{j\in S_{\text{OPT}}^k \backslash S^k}^{}\underbrace{ \varphi_{j}(S^k) }_{  \varphi_{u_{k+1}}(S^k)}\leq f(S^k)+k\cdot \varphi_{u_{k+1}}(S^k)$$Therefore, $$\begin{align}{f(S^k_{\text{OPT}})-f(S^k)}&\leq k\cdot \varphi_{u_{k+1}}(S^k)\\&=k(f(S^{k+1})-f(S^k))\\&=k(f(S^{k+1})-f(S^k_{\text{OPT}}))+k(f(S^k_{\text{OPT}})-f(S^k))\\&\leq\end{align}$$and $\frac{k-1}{k}(f(S^k_{\text{OPT}})-f(S^k))\geq f(S^k_{\text{OPT}})-f(S^{k+1})$. Therefore, 
	