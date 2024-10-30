#Definition #Algorithms 

> [!definition]
> In a ***streaming algorithm***, the input is a stream $S:=(a_{1},\dots,a_{m})$ where $a_{i}\in\{0,\dots,n-1\}$ and $a_{i}$ arrives at the $i$-th step. At each step, our algorithm performs some computation and discards the item $a_{i}$.

- **Related definition**: A ***$k$-th moment*** of a stream $S$ is: $\sum_{j=1}^{n}\left| \{ i\in [m]:a_{i}=j \} \right|^k$.
	- By defining $0^0:=1$, the $0$-th moment is the number of distinct elements in $S$.
	- the first moment is the length of the stream.

---
##### Properties
> [!lemma] Theorem 1 (Morris Counter)
> Consider the algorithm: 
>    ```pseudo
>    \begin{algorithm} \caption{Morris($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    \State $X\gets 0$
>    \For{$a_{i}\in S$}
>    \State $r\gets\{0,\dots,2^X-1\}$ uniformly randomly.
>    \State $X\gets X+\delta_{0,r}$ \EndFor
>	\Return $2^X-1$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Let $X_{m}$ be the value of $X$ after exactly $m$ items arrive. Then,
>    1. $\mathbb{E}[2^{X_{m}}-1]=m$
>    2. $\mathbb{E}[2^{2X_{m}}]=\frac{3}{2}m^{2}+\frac{3}{2}m+1$
>    3. $\text{Var}(2^{X_{m}}-1)=\mathbb{E}[(2^{X_{m}}-1-m)^{2}]\leq \frac{m^2}{2}$

> [!proof]+
> We have that:
> 1. By induction on $m$, we will show that $\mathbb{E}[2^{X_{m}}]=m+1$. 
> 	1. for $m=1$, $\mathbb{P}(X_{1}=1)=1$. Hence, $\mathbb{E}[2^{X_{1}}]=2.$
> 	2. for $m\geq 1$, we have that: $$\begin{align}\mathbb{E}[2^{X_{m}}]&=\sum_{j=1}^{m-1}\mathbb{E}[2^{X_{m}}|X_{m-1}=j]\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{j+1}\cdot 2^{-j}+2^j\cdot (1-2^{-j}))\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^j+1)\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{X_{m-1}}]+\sum_{j=1}^{m-1}\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{X_{m-1}}]+1\end{align}$$which proves the statement.
> 2. By induction on $m$, we have that:
> 	1. for $m=1$, $\mathbb{P}(X_{1}=1)=1$ and $\mathbb{E}[2^{2X_{1}}]=2^2=\frac{3}{2}+\frac{3}{2}+1$.
> 	2. for $m\geq 1$, we have that: $$\begin{align}\mathbb{E}[2^{2X_{m}}]&=\sum_{j=1}^{m-1}\mathbb{E}[2^{2X_{m}}|X_{m-1}=j]\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{2j+2}\cdot 2^{-j}+2^{2j}(1-2^{-j}))\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{2j}+3\cdot 2^{j})\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{2X_{m-1}}]+3\cdot \mathbb{E}[2^{X_{m-1}}]\\&=\frac{3}{2}(m-1)^{2}+\frac{3}{2}(m-1)+1+3m\\&=\frac{3}{2}m^{2}+\frac{3}{2}m+1\end{align}$$
> 3. We have that: $$\begin{align}\text{Var}(2^{X_{m}}-1)&=\mathbb{E}[2^{2X_{m}}-2(m+1)2^{X_{m}}+(m+1)^{2}]\\&=\frac{3}{2}m^{2}+\frac{3}{2}m+1-2(m+1)\end{align}$$