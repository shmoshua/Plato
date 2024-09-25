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

