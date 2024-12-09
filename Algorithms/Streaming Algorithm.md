#Definition #Algorithms 

> [!definition]
> In a ***streaming algorithm***, the input is a stream $S:=(a_{1},\dots,a_{m})$ where $a_{i}\in\{0,\dots,n-1\}$ and $a_{i}$ arrives at the $i$-th step. At each step, our algorithm performs some computation and discards the item $a_{i}$.

^b3edf5

- **Related definition**: A ***$k$-th moment*** of a stream $S$ is: $\sum_{j=1}^{n}\left| \{ i\in [m]:a_{i}=j \} \right|^k$. ^5e97b2
	- By defining $0^0:=1$, the $0$-th moment is the number of distinct elements in $S$.
	- the first moment is the length of the stream.

---
##### Properties

> [!lemma] Theorem 1 (Mean Trick)
> Let $\mathcal{A}$ be an streaming algorithm estimating $x$ and let $\mathcal{B}$ be the algorithm that runs $\mathcal{A}$ $k$ times and takes the mean, then: 
> 1. $\mathbb{P}(\left| \mathcal{B}(S)-x \right|\geq \varepsilon x)\leq \text{Var}(\mathcal{A}(S)) /k\varepsilon^2x^2$
> 2. $\mathcal{B}$ has space complexity $k$ times that of $\mathcal{A}$.


^38b8d5

> [!proof]-
> We have that: $$\begin{align} \mathbb{P}(\left| \mathcal{B}(S)-x \right|\geq \varepsilon x)\leq \frac{\text{Var}(\mathcal{B}(S))}{\varepsilon^2x^2}=\frac{\text{Var}(\mathcal{A}(S))}{k\varepsilon^2x^2}\end{align}$$

^eb91b6

---

> [!lemma] Theorem 2 (Median Trick)
> Let $\mathcal{A}$ be an streaming algorithm estimating $x$ with: $$\mathbb{P}(\left| \mathcal{A}(S)-x \right| \leq  \varepsilon x)\geq q> \frac{1}{2}$$ and let $\mathcal{B}$ be the algorithm that runs $\mathcal{A}$ $t$ times and takes the median, then: 
> 1. $\mathbb{P}(\left| \mathcal{B}(S)-x \right|>\varepsilon x)\leq\exp \left( -\frac{\left( 1-\frac{1}{2q} \right)^{2}tq}{2} \right)$
> 2. For any $\delta>0$, if $t\geq\frac{2\ln(1/\delta)}{q\left( 1-\frac{1}{2q} \right)^{2}}$, then $\mathbb{P}(\left| \mathcal{B}(S)-x \right|\geq \varepsilon x)\leq\delta$.


^c2b6ca

> [!proof]-
> Let $I_{i}$ denote the indicator variable that the $i$-th run of $\mathcal{A}$ succeeds. Let $p:=\mathbb{P}(\left| \mathcal{A}(S) -x \right|\leq\varepsilon x )>1 /2$. Then, $\mathbb{E}\left[ \sum_{i=1}^{t}I_{i} \right]=tp$ and: $$\begin{align}\mathbb{P}(\left| \mathcal{B}(S) -x \right|>\varepsilon x )&=\mathbb{P}\left( \sum_{i=1}^{t}I_{i}< \frac{t}{2} \right)=\mathbb{P}\left( \sum_{i=1}^{t}I_{i}<\left( \frac{1}{2p} \right)tp\right) \\&\leq \exp \left( -\frac{\left( 1-\frac{1}{2p} \right)^{2}tp}{2} \right)  \end{align}$$

^8eb98b

---

###### Estimating the 1st Moment
> [!lemma] Theorem 1 (Morris Counter)
> Consider the algorithm: 
>    ```pseudo
>    \begin{algorithm} \caption{Morris($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    \State $X\gets 0$
>    \For{$a_{i}\in S$}
>    \State $r\gets 0$
>    \For{$j\in X$}
>    \State $b\gets\{0,1\}$ uniform random bit
>    \If{$b=1$}
>    \Break
\EndIf
>   
>    \State $r\gets r+1$
>    \EndFor
>    \If{$r=X$}
>    \State $X\gets X+1$ 
>    \EndIf
>    \EndFor
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

^9a34f6

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
> 5. Notice that we have $X\in O(\log m)$ w.h.p and we need $O(\log X)$ bits for the algorithm.

^1f7d2d

- **Corollary**: We have that: ^39fa84
	1. By using the mean trick with $k=\left\lceil 2 / \varepsilon^2\right\rceil$, $\mathbb{P}(\left| \mathcal{B}(S)-m \right|\geq \varepsilon m)\leq 1 /2k\varepsilon^2<1/4$ in space complexity $\text{O}(\varepsilon^{-2}\log \log m)$
	2. By further using the median trick with $t=\left\lceil 24\ln(1 / \delta)\right\rceil$, $\mathbb{P}(\left| \mathcal{B}(S)-m \right|\geq \varepsilon m)\leq \delta$ in space complexity $\text{O}(\varepsilon^{-2}\log \log m\log(1 / \delta))$.
---
###### Estimating the 0-th moment

> [!lemma] Theorem 3 (FM, Flajolet, Martin)
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
>    where $\text{Zeroes}(x)=\max\{r\in \mathbb{Z}_{\geq 0}:2^r|x\}$.  Let $D$ be the number of distinct elements in the stream.
>    1. $\text{FM}$ uses $\text{O}(\log n)$ space and $\mathbb{P}(D / 3\leq \text{FM}(S)\leq 3D)\geq 1-\frac{2\sqrt{ 2 }}{3}$.

^399e1c

> [!proof]-
> Let $J\subseteq[n]$ be the set of all distinct elements in the stream. Then, for each $j\in [n]$ and $r\in \mathbb{Z}_{\geq 0}$, let $X_{j,r}$ be the indicator variable denoting $\text{Zeroes}(h(j))\geq r$. Let $X_{r}:=\sum_{j\in J}^{}X_{j,r}$. We have:
> 1. $\mathbb{E}[X_{r}]=\sum_{j\in J}^{}\mathbb{E}[X_{j,r}]=\sum_{j\in J}^{} \frac{1}{2^r}=\frac{D}{2^r}$
> 2. $\text{Var}(X_{r})=\sum_{j\in J}\mathbb{E}[X_{j,r}^{2}]-\mathbb{E}[X_{j,r}]^{2}\leq \sum_{j\in J}^{}\mathbb{E}[X_{j,r}^{2}]=\sum_{j\in J}^{}\mathbb{E}[X_{j,r}]=\frac{D}{2^r}$
> 
> Now, let $\tau_{\text{high}}:=\min\{ t\in \mathbb{Z}:2^{t+1/2}>3D \}$ and $\tau_{\text{low}}:=\max\{ t\in \mathbb{Z}:2^{t+1 /2}<D /3 \}$ 
> 1. If $X\geq \tau_{\text{high}}$ then there exists $j\in J$ with $\text{Zeroes}(h(a_{i}))\geq \tau_{\text{high}}$, i.e. $X_{\tau_{\text{high}}}\geq 1$. Therefore, we have that: $$\begin{align}\mathbb{P}(X\geq \tau_{\text{high}} )\leq \mathbb{P}(X_{\tau_{\text{high}}}\geq 1)\leq \mathbb{E}[X_{\tau_{\text{high}}}]=\frac{D}{2^{\tau_{\text{high}}}}<\frac{\sqrt{ 2 }}{3}\end{align}$$
> 2. If $X\leq \tau_{\text{low}}$, then $X_{\tau_{\text{low}}+1}=0$. Therefore, by [[Expected Value|Proposition 1.3]] $$\mathbb{P}(X\leq \tau_{\text{low}})\leq \mathbb{P}(X_{\tau_{\text{low}}+1}=0)\leq \frac{\text{Var}(X_{\tau_{\text{low}}+1})}{\mathbb{E}[X_{\tau_{\text{low}}+1}]^{2}}\leq \frac{2^{\tau_{\text{low}}+1}}{D}<\frac{\sqrt{ 2 }}{3}$$
>    
> By union bound, we have that: $$\mathbb{P}(D / 3\leq \text{FM}(S)\leq 3D)\geq 1-\frac{2\sqrt{ 2 }}{3}$$

^894eb0
- **Corollary**: We have that: ^001d15
	- By using the mean trick with $k=50$, we get that $\mathbb{P}(X\leq \tau_{\text{low}})< \frac{1}{50}$. Hence, $\mathbb{P}(D / 3\leq \mathcal{B}(S)\leq 3D)\geq \frac{51}{100}$.
	- By using the median trick with $t:=\text{O}(\log(1 / \delta))$, we get that $\mathbb{P}(D / 3\leq \mathcal{B}(S)\leq 3D)\geq 1-\delta$ in space $\text{O}(\log n \log(1 / \delta))$.
---
> [!lemma] Theorem 4 (FM+,BJKST)
> Consider the algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{FM+($a_{1},\dots,a_{m},C,C'$)} 
>    \begin{algorithmic}
>    \State $h:[n]\to[n]\gets$ uniform, 2-wise independent random hash function.
>    \State $g:[n]\to[b]\gets$ uniform, 2-wise independent random hash function where $b=C\varepsilon^{-4}\log^2n$.
>    \State $\mathcal{B}\gets \varnothing$
>    \State $X\gets 0$
>    \For{$a_{i}\in S$}
>    \If{$\text{Zeros}(h(a_{i}))\geq X$}
>    \State $\mathcal{B}\gets\mathcal{B}\cup \{ (g(a_{i}),\text{Zeroes}(h(a_{i}))) \}$
>    \While{$\left| \mathcal{B} \right|\geq C'\varepsilon^{-2}$}
>    \State $X\gets X+1$
>    \State Remove from $\mathcal{B}$ all elements $(\alpha,\beta)$ with $\beta<X$.
\EndWhile
\EndIf
>    \EndFor
>    \Return $\left| \mathcal{B} \right|\cdot2^{X}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Let $i\in[n]$ appeared in $\mathcal{B}$ if there exists $a_{j}=i$ s.t. $\mathcal{B}\gets \mathcal{B}\cup \{ (g(a_{j}),\text{Zeroes}(h(a_{j}))) \}$ was executed. Let $S\subseteq[n]$ be the set of elements that appeared in $\mathcal{B}$.
>    1. $\mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j))\leq \frac{1}{6}$

> [!proof]+
> We have that:
> 1. We first have the following claims:
> 	1. **Claim 1**: If $g(i)\neq g(j)$ for any distinct $i,j\in S$, then $\left| S \right|\leq C'(\log n+2) / \varepsilon^{2}$.
> 		Under this assumption for any $j\in [n]$ if $j$ has not appeared in $\mathcal{B}$ then $j$ increases $\mathcal{B}$ by 1. In particular, between two increments of $X$, we can add at most $C'/\varepsilon^{2}$ new elements to $\mathcal{B}$. 
> 		
> 		Moreover, as $X-1\leq \text{Zeroes}(h(a_{i}))$ for some $a_{i}$ at the end and as $$\text{Zeroes}(h(a_{i}))\leq \left\lceil \log n\right\rceil\leq \log n+1$$we have that $X\leq \log n+2$ and there are at most $(\log n+2)$ increments. Therefore, $\left| S \right|\leq C'(\log n+2) / \varepsilon^{2}$.
> 	1. **Claim 2**: If $C\geq 27C'^{2}$ and $\left| S \right|\leq C'(\log n+2) / \varepsilon^{2}$, then we have that:$\mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j))\leq \frac{1}{6}$
> 	   
> 	   Let $X_{i,j}$ be the indicator variable denoting that $g(i)=g(j)$. Then, $$\begin{align}\mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j))\leq{\left| S \right|  \choose 2} \frac{1}{b}\leq \frac{C'^{2}(\log n+2)^{2}}{2C\log^2 n}\leq \frac{1}{6}\end{align}$$
> 	
> 	Therefore, now fix an input $a_{1},\dots,a_{m}$. Let $\mathcal{A}$ be a run of $\text{FM}+$ where we replace $\mathcal{B}\gets \mathcal{B}\cup\{ (g(a_{j}),\text{Zeroes}(h(a_{j}))) \}$ with $\mathcal{B}\gets \mathcal{B}\cup\{ (a_{j},\text{Zeroes}(h(a_{j}))) \}$. Let $S'$ be the sets of elements added to $\mathcal{B}$ in $\mathcal{A}$. Then, by Claim 1, $\left| S' \right|\leq C'(\log n+2) / \varepsilon^{2}$. 
> 	
> 	Now, coming back to $\text{FM}+$, let $E$ denote the event that there exists distinct $i,j\in S'$ with $g(i)=g(j)$. Then, $$\begin{align}\mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j))&\leq \underbrace{ \mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j)|\overline{E}) }_{ =0 }+\mathbb{P}(E)\\&=\mathbb{P}(E)\leq \frac{1}{6}\end{align}$$
> 2. Let $X_{j,r}$ denote the indicator variable that $\text{Zeroes}(h(j))\geq r$. Further, $X_{r}:=\sum_{j\in J}^{}X_{j,r}$ Then, similarly, as Theorem 3, 
> 	1. $\mathbb{E}[X_{r}]=\frac{D}{2^r}$ and
> 	2. $\text{Var}(X_{r})\leq \frac{D}{2^r}$.
> 
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
> 1. if $|(A,V \backslash A)|=k$ where $\frac{1}{12}\widehat{k}\leq k\leq \widehat{k}$, then $\text{SingleCut}(S,A)$ returns $e\in(A , V \backslash A)$ with constant probability using $\text{O}(n\log n)$ bits of memory.

> [!proof]+
> We have that: $$X=\bigoplus_{e\in (A,V \backslash A)} \text{id}(e)\cdot  \mathbb{1}_{\{ h(e)=0 \}}$$Now, let $Y_{e}=\mathbb{1}_{\{ h(e)=0 \}}$ and $Y:=\sum_{e\in (A, V\backslash A)}^{}Y_{e}$. Then, $$\mathbb{E}[Y]=\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(h(e)=0)=\frac{k}{\widehat{k}}\in\left[ \frac{11}{12},1 \right]$$Further, $$\begin{align}\text{Var}(Y)=\mathbb{E}[Y^{2}]-\mathbb{E}[Y]^{2}&\leq  \sum_{e,e'\in (A, V \backslash A)}^{}\mathbb{E}\left[Y_{e}Y_{e'} \right] -\mathbb{E}[Y^{2}]\\&\leq \sum_{e\neq e'}^{} \frac{1}{\widehat{k}^{2}}+\sum_{e}^{} \mathbb{E}[Y_{e}^{2}]-\mathbb{E}[Y^{2}]\\&= { k \choose 2} \frac{1}{\widehat{k}^{2}}\\&\leq \frac{1}{2}\left(  \right) \end{align}$$
