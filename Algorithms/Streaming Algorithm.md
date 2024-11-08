#Definition #Algorithms 

> [!definition]
> In a ***streaming algorithm***, the input is a stream $S:=(a_{1},\dots,a_{m})$ where $a_{i}\in\{0,\dots,n-1\}$ and $a_{i}$ arrives at the $i$-th step. At each step, our algorithm performs some computation and discards the item $a_{i}$.

- **Related definition**: A ***$k$-th moment*** of a stream $S$ is: $\sum_{j=1}^{n}\left| \{ i\in [m]:a_{i}=j \} \right|^k$.
	- By defining $0^0:=1$, the $0$-th moment is the number of distinct elements in $S$.
	- the first moment is the length of the stream.

---
##### Properties

###### Estimating the 1st Moment
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
>    4. For $\ell>0$, $\mathbb{P}(\left| 2^{X_{m}}-1-m \right|\geq\ell m)\leq \frac{1}{2\ell^{2}}$.
>    5. $\text{Morris}$ uses $\text{O}(\log \log m)$ bits. 

> [!proof]-
> We have that:
> 1. By induction on $m$, we will show that $\mathbb{E}[2^{X_{m}}]=m+1$. 
> 	1. for $m=1$, $\mathbb{P}(X_{1}=1)=1$. Hence, $\mathbb{E}[2^{X_{1}}]=2.$
> 	2. for $m\geq 1$, we have that: $$\begin{align}\mathbb{E}[2^{X_{m}}]&=\sum_{j=1}^{m-1}\mathbb{E}[2^{X_{m}}|X_{m-1}=j]\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{j+1}\cdot 2^{-j}+2^j\cdot (1-2^{-j}))\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^j+1)\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{X_{m-1}}]+\sum_{j=1}^{m-1}\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{X_{m-1}}]+1\end{align}$$which proves the statement.
> 2. By induction on $m$, we have that:
> 	1. for $m=1$, $\mathbb{P}(X_{1}=1)=1$ and $\mathbb{E}[2^{2X_{1}}]=2^2=\frac{3}{2}+\frac{3}{2}+1$.
> 	2. for $m\geq 1$, we have that: $$\begin{align}\mathbb{E}[2^{2X_{m}}]&=\sum_{j=1}^{m-1}\mathbb{E}[2^{2X_{m}}|X_{m-1}=j]\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{2j+2}\cdot 2^{-j}+2^{2j}(1-2^{-j}))\mathbb{P}(X_{m-1}=j)\\&=\sum_{j=1}^{m-1}(2^{2j}+3\cdot 2^{j})\mathbb{P}(X_{m-1}=j)\\&=\mathbb{E}[2^{2X_{m-1}}]+3\cdot \mathbb{E}[2^{X_{m-1}}]\\&=\frac{3}{2}(m-1)^{2}+\frac{3}{2}(m-1)+1+3m\\&=\frac{3}{2}m^{2}+\frac{3}{2}m+1\end{align}$$
> 3. We have that: $$\begin{align}\text{Var}(2^{X_{m}}-1)&=\mathbb{E}[2^{2X_{m}}-2(m+1)2^{X_{m}}+(m+1)^{2}]\\&=\frac{3}{2}m^{2}+\frac{3}{2}m+1-(m+1)^{2}\\&=\frac{m^{2}}{2}-\frac{m}{2}\end{align}$$
> 4. By Chebyshev, we have:$$\mathbb{P}(\left| 2^{X_{m}}-1-m \right|\geq \ell m)\leq \frac{1}{2\ell^{2}}$$
> 5. Notice that we have $X\in O(\log\log m)$.
---
> [!lemma] Theorem 2 (Morris Counter+)
> Consider the algorithm: 
>    ```pseudo
>    \begin{algorithm} \caption{Morris+($S=(a_{1},\dots,a_{m}),\varepsilon$)} 
>    \begin{algorithmic}
>    \State $k\gets \left\lceil 2/\varepsilon ^{2}\right\rceil$
>    \For{$i\in[k]$}
>    \State $Y_{i}\gets $\Call{Morris}{$S$}\EndFor
>    \Return $\overline{Y}:=\frac{1}{k}\sum_{i=1}^{k}Y_{i}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    For any stream $S$ and $\varepsilon>0$, 
>    1. $\text{Morris+}$ uses space $\text{O}(\varepsilon^{-2}\log \log m)$ and $$\mathbb{P}(\left| \text{Morris+}(S) -m \right|>\varepsilon m )\leq \frac{1}{4}$$

> [!proof]-
> We have that: $$\begin{align} \mathbb{P}\left(\left| \overline{Y} -1-m\right| >\ell m\right)&\leq \frac{\text{Var}(\overline{Y})}{\ell^{2}m^{2}}\\&\le \frac{1}{2k\ell^{2}}\end{align}$$Therefore, by choosing $\ell=\sqrt{ 2 / k }\geq \varepsilon$, we have: $$\mathbb{P}(\left| \overline{Y}-(m+1) \right|> \varepsilon m)\leq 1/4$$
---
> [!lemma] Theorem 3 (Morris Counter++)
> Consider the algorithm: 
>    ```pseudo
>    \begin{algorithm} \caption{Morris++($S=(a_{1},\dots,a_{m}),\varepsilon,\delta$)} 
>    \begin{algorithmic}
>    \State $t\gets \left\lceil 24\log (1 / \delta)\right\rceil$
>    \For{$i\in[t]$}
>    \State $Z_{i}\gets $\Call{Morris+}{$S,\varepsilon$}
>    \EndFor
>    \Return median among all $Z_{i}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    For any stream $S$ and $\varepsilon,\delta>0$, 
>    1. $\text{Morris+}$ uses space $\text{O}(\varepsilon^{-2}\log \log m\log(1 / \delta))$ and $$\mathbb{P}(\left| \text{Morris++}(S) -m \right|>\varepsilon m )\leq \delta$$

> [!proof]-
> Let $I_{i}$ denote the indicator variable that the $i$-th run of $\text{Morris+}(S,\varepsilon)$ succeeds. Let $p:=\mathbb{P}(\left| \text{Morris+}(S) -m \right|\leq\varepsilon m )\geq \frac{3}{4}$. Then, $\mathbb{E}\left[ \sum_{i=1}^{t}I_{i} \right]\leq t /4$. $$\begin{align}\mathbb{P}(\left| \text{Morris++}(S) -m \right|>\varepsilon m )&=\mathbb{P}\left( \sum_{i=1}^{t}I_{i}< \frac{t}{2} \right)\\&=\mathbb{P}\left( \sum_{i=1}^{t}I_{i}<\left( \frac{1}{2p} \right)tp\right) \\&\leq \exp \left( -\frac{\left( 1-\frac{1}{2p} \right)^{2}tp}{2} \right) \\&\leq \exp \left( -\frac{t}{24} \right)\\&\leq \delta  \end{align}$$
---
###### Estimating the 0-th moment

> [!lemma] Theorem 3 (FM)
> Consider the algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{FM($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    \State $h:[n]\to[n]\gets$ uniform, 2-wise independent random hash function sampled from $\mathcal{G}_{2,n,n}$.
>    \State $X\gets 0$
>    \For{$a_{i}\in S$}
>    \State $X\gets \max\{ X,\text{Zeros}(h(a_{i})) \}$
>    \EndFor
>    \Return $2^{X+1 /2}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Using mean and the median trick, 

> [!proof]+

---
###### Finding the Majority Element
> [!lemma] Theorem 4
> Consider the algorithm:
>  ```pseudo
>    \begin{algorithm} \caption{A($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    
>    \State $x\gets a_{0}$
>    \State $\text{count}\gets 0$
>    \For{$a_{i}\in S$}
>    \If{$x=a_{i}$}
>    \State $\text{count}\gets \text{count}+1$
>    \Else
>    \State $\text{count}\gets \text{count}-1$
>    \EndIf
>    \If{$\text{count}=0$}
>    \State $x\gets a_{i}$
>    \EndIf
>    \EndFor
>    \Return $x$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    If there exists an element $j$ s.t. $\left| \{ i\in[m]:a_{i}=j \} \right|> \frac{m}{ 2}$, then:
>    1. the algorithm returns $j$ in space $\text{O}(\log n+\log m)$.

> [!proof]+
> Let $x$ be the output of the algorithm. 

---
##### Graph Streaming Algorithms
###### Graph Connectivity

> [!lemma] Lemma 1 (Single Cut Edge)
> Let $\text{id}(v)$ denote the bit-representation of $v\in V:=[n]$. Then,
>  ```pseudo
>    \begin{algorithm} \caption{SingleCut($S=(a_{1},\dots,a_{m}),A$)} 
>    \begin{algorithmic}
>    \State $X_{v}\gets 0$ for all $v\in V$
>    \For {$\left\langle e_{i},\pm\right\rangle\in S$}
>    \State $\text{id}(e_{i})\gets \langle{ \text{id}(u) , \text{id}(v) \rangle}$ for $e_{i}=\{ u,v \}$ and $u< v$
>    \State $X_u\gets X_{u}\oplus \text{id}(e_{i})$
>    \State $X_v\gets X_{v}\oplus \text{id}(e_{i})$
>    \EndFor
>    \State $X\gets \bigoplus_{v\in A} X_{v}$
>    \Return edge $e$ with $\text{id}(e)=X$. 
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> For any stream $S:=(a_{1},\dots,a_{m})$ with $a_i:= \braket{ e_{i} , \pm }\in {n \choose 2}\times\{+,-\}$ for all $i\in[m]$ and a set $A\subseteq V$, if $(A,V \backslash A)=\{ e \}$ then $\text{SingleCut}(S,A)$ returns $e$ using $\text{O}(n\log n)$ bits of memory.

> [!proof]-
> Let $e^{*}$ be the one cut edge. We have that: $$X=\bigoplus_{v\in A}X_{v}=\bigoplus_{v\in A}\bigoplus_{e\ni v}\text{id}(e) =\bigoplus_{e\in E} \text{id}(e)\cdot \mathbb{1}_{\{ |e\cap A|=1 \}}  =\text{id}(e^{*}) $$
> Further, for each $v\in V$, we keep track of $2\log n$ bits. Hence, we use $\text{O}(n\log n)$ space.
---
> [!lemma] Lemma 2 (k-Edge Cut)
> ```pseudo
>    \begin{algorithm} \caption{$k$-Cut($S=(a_{1},\dots,a_{m}),A,\widehat{k}$)} 
>    \begin{algorithmic}
>    \State $X_{v}\gets 0$ for all $v\in V$
>    \State $h\gets\mathcal{H}_{2,{n\choose 2},\widehat{k}}$, a $2$-wise independent hash function.
>    \For {$\left\langle e_{i},\pm\right\rangle\in S$}
>    \If{$h(e_{i})\neq 0$}
>    \Continue
>    \EndIf
>    \State $\text{id}(e_{i})\gets \langle{ \text{id}(u) , \text{id}(v) \rangle}$ for $e_{i}=\{ u,v \}$ and $u< v$
>    \State $X_u\gets X_{u}\oplus \text{id}(e_{i})$
>    \State $X_v\gets X_{v}\oplus \text{id}(e_{i})$
>    \EndFor
>    \State $X\gets \bigoplus_{v\in A} X_{v}$
>    \Return edge $e$ with $\text{id}(e)=X$. 
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> For any stream $S:=(a_{1},\dots,a_{m})$ with $a_i:= \braket{ e_{i} , \pm }\in {n \choose 2}\times\{+,-\}$ for all $i\in[m]$ and a set $A\subseteq V$, 
> 1. if $|(A,V \backslash A)|=k$ where $\frac{11}{12}\widehat{k}\leq k\leq \widehat{k}$, then $\text{SingleCut}(S,A)$ returns $e\in(A , V \backslash A)$ with constant probability using $\text{O}(n\log n)$ bits of memory.

> [!proof]+
> We have that: $$X=\bigoplus_{e\in (A,V \backslash A)} \text{id}(e)\cdot  \mathbb{1}_{\{ h(e)=0 \}}$$Now, let $Y_{e}=\mathbb{1}_{\{ h(e)=0 \}}$ and $Y:=\sum_{e\in (A, V\backslash A)}^{}Y_{e}$. Then, $$\mathbb{E}[Y]=\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(h(e)=0)=\frac{k}{\widehat{k}}\in\left[ \frac{11}{12},1 \right]$$Further, $$\begin{align}\text{Var}(Y)=\mathbb{E}[Y^{2}]-\mathbb{E}[Y]^{2}&\leq  \sum_{e,e'\in (A, V \backslash A)}^{}\mathbb{E}\left[Y_{e}Y_{e'} \right] -\mathbb{E}[Y^{2}]\\&\leq \sum_{e\neq e'}^{} \frac{1}{\widehat{k}^{2}}+\sum_{e}^{} \mathbb{E}[Y_{e}^{2}]-\mathbb{E}[Y^{2}]\\&= { k \choose 2} \frac{1}{\widehat{k}^{2}}\\&\leq \frac{1}{2}\left(  \right) \end{align}$$
