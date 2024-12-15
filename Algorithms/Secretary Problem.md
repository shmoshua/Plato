#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=\{ a_{1},\dots,a_{n} \}$ be totally ordered with $a_{i}\leq a_{i+1}$. 
---
##### Properties
> [!lemma] Theorem 1
> Consider the following algorithm
> ```pseudo
> \begin{algorithm} \caption{Secretary($a_{1},\dots,a_{n},k$)}
> \begin{algorithmic} 
> \State Pass the first $k$ elements.
> \State Pick first element greater than all of the $k$ first elements.
> \end{algorithmic}
> \end{algorithm}
> ```
> The algorithm picks the best element with probability at least $(1-o(1)) \frac{k}{n}\ln \frac{n}{k}$, if $k=\omega(1)$.

> [!proof]+
> We have that: $$\mathbb{P}(\text{win})=\sum_{i=k+1}^{n}\mathbb{P}(a_{i}\text{ is the best element},\mathcal{A}=a_{i})$$