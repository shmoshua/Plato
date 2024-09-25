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
>    \State $\mathcal{B}\to \empty$
>    \For{$i\in [k]$}
>    \State
>    \If{$s_i\le 1-s(B)$ for some $B\in \mathcal{B}$}
>    \State Pick the first such $B$
>    \State $B\gets B\cup\{i\}$
>    \Else
>    \State $B'\gets \{i\}$
>    \State $\mathcal{B}\gets\mathcal{B}\cup\{B'\}$
>    \EndIf
>    \EndFor
>    \Return $\mathcal {B}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```