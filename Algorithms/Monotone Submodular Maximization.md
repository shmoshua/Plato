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
>    Then, $\text{Greedy}$ outputs a $\left( 1-\frac{1}{e} \right)$-approximation to monotone submodular maximization in $O(nk)$.

> [!proof]-
> Without loss of generality, we may assume that $f(\varnothing)=0$. Now, we define the gain function as: $$\varphi:\mathcal{U}\times \mathcal{P}(\mathcal{U})\to \mathbb{R}_{\geq 0},\quad (u,S)\mapsto f(S\cup \{ u \})-f(S)$$Now, let $u_{i}$ denote the element chosen at step $i$ by Greedy algorithm. Furthermore, let $T$ denote the optimum set with size $k$ and let $S^\ell:=\{ u_{1},\dots,u_{\ell} \}$ for $\ell=0,\dots,k$. Then, 
> 1. **Claim 1: $f(A\cup B)\leq f(A)+\sum_{i\in B \backslash A}^{}\varphi_{i}(A)$**
>    We show this over induction over $\left| B  \backslash A\right|$. If $\left| B  \backslash A\right|=1$, then $$f(A)+f(A\cup \{ i \})-f(A)=f(A\cup \{ i \})=f(A\cup B)$$
>    For $\left| B  \backslash A \right|>1$ let $i\in B \backslash A$. Then, we have that: $$\begin{align}f(A\cup B)=f(A\cup B\backslash\{ i \}\cup \{ i \})&\leq f(A\cup B \backslash\{ i \})+\underbrace{ \varphi_{i}(A \cup B \backslash\{ i \}) }_{ \leq\varphi_{i}(A) }\\&\leq f(A)+\sum_{j\in B \backslash A, j\neq i}^{}\varphi_{j}(A)+\varphi_{i}(A)\end{align}$$which proves the claim.
>    
>  Therefore, $$f(T)\leq f(T\cup S^\ell)\leq f(S^\ell)+\sum_{j\in T \backslash S^\ell}^{}\underbrace{ \varphi_{j}(S^\ell) }_{ \leq\varphi_{u_{\ell+1}}(S^\ell) }\leq kf(S^{\ell+1})-(k-1)f(S^\ell),\quad \forall \ell=0,\dots,k-1$$ 
>  
>  Then, $k(f(T)-f(S^{\ell+1}))\leq (k-1)(f(T)-f(S^\ell))$. Therefore, $$\frac{f(S^k)}{f(T)}=1-\frac{f(T)-f(S^k)}{f(T)-f(S^0)}\geq1-\left( \frac{k-1}{k} \right)^k \geq 1-\frac{1}{e}$$
> 
---