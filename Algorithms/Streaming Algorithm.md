#Definition #Algorithms 

> [!definition]
> In a ***streaming algorithm***, the input is a stream $S:=(a_{1},\dots,a_{m})$ where $a_{i}\in\{0,\dots,n-1\}$ and $a_{i}$ arrives at the $i$-th step. At each step, our algorithm performs some computation and discards the item $a_{i}$.

^b3edf5

- **Related definition**: A ***$k$-th moment*** of a stream $S$ is: $\sum_{j=1}^{n}\left| \{ i\in [m]:a_{i}=j \} \right|^k$. ^5e97b2
	- By defining $0^0:=1$, the $0$-th moment is the number of distinct elements in $S$.
	- the first moment is the length of the stream.
- **Related definition**: A ***undirected graph stream*** is given by $S:=(a_{1},\dots,a_{m})$ with $a_i:= \braket{ e_{i} , \pm }\in {n \choose 2}\times\{+,-\}$ for all $i\in[m]$ where $\braket{ e , + }$ means edge addition and $\braket{ e , - }$ means edge deletion.
- **Related definition**: A graph stream $S=(a_{1},\dots,a_{m})$ is ***well-behaved*** if for all $i\in[m]$, if $a_{i}=\braket{ e_{i} , - }$ then there exists $j<i$ with $a_{j}=\braket{ e_{i} , + }$. 

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
>    Let $i\in[n]$ appeared in $\mathcal{B}$ if there exists $a_{j}=i$ s.t. $\mathcal{B}\gets \mathcal{B}\cup \{ (g(a_{j}),\text{Zeroes}(h(a_{j}))) \}$ was executed. Let $S\subseteq[n]$ be the set of elements that appeared in $\mathcal{B}$. Let $C'=576$ and $C\geq 9C'^{2}$.
>    1. $\mathbb{P}(\exists i\neq j\in[n]:i,j\in S\land g(i)=g(j))\leq \frac{1}{6}$
>    2. $\text{FM}+$ has space complexity $\text{O}(\log n+\varepsilon^{-2}(\log \log n+\log(1 / \varepsilon)))$  and$$\mathbb{P}(\left| \text{FM+}(S)-D \right|\geq \varepsilon D)\leq \frac{1}{3}$$

^273243

> [!proof]-
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
> 2. Assume that there exist no collisions in $g$ from all elements added to $\mathcal{B}$. Denote this event as $E$. Let $Y_{j,r}$ denote the indicator variable that $\text{Zeroes}(h(j))\geq r$. Further, $Y_{r}:=\sum_{j\in J}^{}X_{j,r}$ Then, similarly, as Theorem 3, 
> 	1. $\mathbb{E}[Y_{r}]=\frac{D}{2^r}$ and
> 	2. $\text{Var}(Y_{r})\leq \frac{D}{2^r}$.
> 	
> 	Now, let $\tau$ be the unique integer s.t. $12\varepsilon^{-2}\leq \frac{D}{2^\tau}\leq 24\varepsilon^{-2}$. Then, $\left| \mathcal{B} \right|=Y_{X}$. Hence, $$\begin{align}\mathbb{P}(\left| Y_{X}2^X-D \right| \geq \varepsilon D)&=\mathbb{P}\left( \left| Y_{X}-\frac{D}{2^X} \right| \geq \frac{\varepsilon D}{2^X} \right)\\&=\sum_{r=0}^{\log n}\mathbb{P}\left( \left| Y_{r}-\frac{D}{2^r} \right| \geq \frac{\varepsilon D}{2^r} ,X=r\right)\\&\leq\sum_{r=0}^{\tau-1}\mathbb{P}\left( \left| Y_{r}-\frac{D}{2^r} \right| \geq \frac{\varepsilon D}{2^r}\right)+\sum_{r=\tau}^{\log n}\mathbb{P}(X=r) \end{align}$$For the latter term, notice that if $X\geq \tau$, then the while loop was triggered when $X=\tau-1$. Hence, $Y_{\tau-1}\geq C' / \varepsilon^{2}$. Therefore, by Markov:$$\sum_{r=\tau}^{\log n}\mathbb{P}(X=\tau)\leq \mathbb{P}(X\geq \tau)\leq\mathbb{P}(Y_{\tau-1}>C'/\varepsilon^{2})\leq \frac{D\varepsilon^2}{2^{\tau-1}C'}\leq \frac{48}{C'}=\frac{1}{12}$$for $C'=576$.
> 	
> 	For the first term, $$\begin{align}\sum_{r=0}^{\tau-1}\mathbb{P}\left( \left| Y_{r}-\frac{D}{2^r} \right| \geq \frac{\varepsilon D}{2^r}\right)&\leq \sum_{r=0}^{\tau-1}\frac{\text{Var}(Y_{r})2^{2r}}{\varepsilon^{2}D^{2}}\leq \sum_{r=0}^{\tau-1}\frac{2^r}{\varepsilon^{2}D}\leq \frac{2^\tau}{\varepsilon^{2}D}\leq \frac{1}{12}\end{align}$$Therefore, $\mathbb{P}(\left| Y_{X}2^X-D \right| \geq \varepsilon D)\leq 1 /6$.
> 	
> 	Finally, we have that: $$\mathbb{P}(\left| Y_{X}2^X-D \right| \geq \varepsilon D)\leq\mathbb{P}(\left| Y_{X}2^X-D \right| \geq \varepsilon D|E)+\mathbb{P}(\overline{E})\leq \frac{1}{3}$$
> 	The space complexity is given as follows. Saving the hash functions can be done in $\text{O}(\log n+\log b)$. Further, each $(g(a_{i}),\text{Zeroes}(h(a_{i})))$ can be saved in $\text{O}(\log b+\log\log n)$ bits where $\text{O}(\log b)=\text{O}(\log \log n+\log (1 /\varepsilon))$. We can conclude by saying that we save at most $\text{O}(\varepsilon^{-2})$ of them. 

^4ea1a3

- **Corollary**: For any $\delta>0$, using the median trick with $t=\left\lceil 48\ln (1 / \delta)\right\rceil$,  we have that $\mathbb{P}(\left| \text{FM+}(S)-D \right|\geq \varepsilon D)\leq \delta$ with space  $\text{O}((\log n+\varepsilon^{-2}(\log \log n+\log(1 / \varepsilon)))\log (1 / \delta))$. ^a9914b
---
###### Estimating the 2nd moment

> [!lemma] Theorem 5 (AMS)
> Consider the algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{AMS($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    \State $h:[n]\to \{ -1,+1 \}\gets$ uniform, 4-wise independent random hash function.
>    \State $Z\gets 0$
>    \For{$a_{i}\in S$}
>    \State $Z\gets Z +h(a_{i})$
>    \EndFor
>    \Return $Z^{2}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Let $f_{j}$ denote the frequency of $j\in[n]$ in $S$, i.e. $f_{j}:=\left| \{ i\in[m]:a_{i}=j \} \right|$ and $F_{2}:=\sum_{j\in[n]}^{}f_{j}^{2}$ be the second moment. Then, 
>    1. $\mathbb{E}[Z^{2}]=\sum_{j\in[n]}^{}f^{2}_{j}=F_{2}$
>    2. $\text{Var}(Z^{2})\leq 2(\mathbb{E}[Z^{2}])^{2}$
>    3. $\mathbb{P}(\left| Z^{2}-F_{2} \right|\geq \ell F_{2})\leq \frac{2}{\ell^{2}}$ for any $\ell>0$.
>    4. $\text{AMS}$ has space complexity $\text{O}(\log n)$

^f94d70

> [!proof]-
> We have that: 
> 1. We have that $Z=\sum_{j\in[n]}^{}h_{j}f_{j}$. Hence, $$\begin{align}\mathbb{E}[Z^{2}]&=\mathbb{E}\left[ \sum_{i,j\in [n]}^{}h_{i}h_{j}f_{i}f_{j} \right]=\sum_{j\in[n]}^{}\mathbb{E}[\underbrace{ h_{j}^{2} }_{ =1 }]f_{j}^{2}=\sum_{j\in [n]}^{}f_{j}^{2}\end{align}$$where for $i\neq j$ we have pairwise independence and $\mathbb{E}[h_{i}h_{j}]=\mathbb{E}[h_{i}]\mathbb{E}[h_{j}]=0$.
> 2. We have: $$\begin{align}\mathbb{E}[Z^4]&=\sum_{i,j,k,\ell\in [n]}^{}\mathbb{E}[h_{i}h_{j}h_{k}h_{\ell}]f_{i}f_{j}f_{k}f_{\ell}=\sum_{i\in[n]}^{}\mathbb{E}[h_{i}^4]f_{i}^4+6\sum_{i<j\in[n]}^{}\mathbb{E}[h_{i}^{2}h_{j}^{2}]f_{i}^{2}f_{j}^{2}\\&=\sum_{i\in[n]}^{}f_{i}^4+6\sum_{i<j\in[n]}^{}f_{i}^{2}f_{j}^{2}\end{align}$$Therefore,$$\begin{align}\text{Var}(Z^{2})&=\mathbb{E}[Z^4]-\mathbb{E}[Z^{2}]^2=\sum_{i\in[n]}^{}f_{i}^4+6\sum_{i<j\in[n]}^{}f_{i}^{2}f_{j}^{2}-\sum_{i\in[n]}^{}f_{i}^4-2\sum_{i<j\in[n]}^{}f^2_{i}f^2_{j}\\&=4\sum_{i<j\in[n]}^{}f_{i}^{2}f_{j}^{2}\leq 2\left( \sum_{j\in[n]}^{}f_{j}^{2} \right) ^2=2(\mathbb{E}[Z^{2}])^{2}\end{align}$$
> 3. We have that for any $\ell>0$ by [[Expected Value|Chebyshev]]:$$\begin{align}\mathbb{P}(\left| Z^{2}-F_{2} \right|\geq \ell F_{2})\leq \frac{\text{Var}(Z^{2})}{\ell^{2}F_{2}^{2}}=\frac{2}{\ell^{2}} \end{align}$$
> 4. We only need $\text{O}(\log n)$ to save $h$. Further, $\left| Z \right|\leq n$ and $Z\leq n^{2}$. Hence we need $\text{O}(\log n)$ bits in total.

^f15f0b

- **Corollary**: We have that:  ^90acce
	1. By using the mean trick with $k=\left\lceil 8 / \varepsilon^2\right\rceil$, $\mathbb{P}(\left| \mathcal{B}(S)-m \right|\geq \varepsilon m)\leq 1/4$ in space complexity $\text{O}(\varepsilon^{-2}\log n)$
	2. By further using the median trick with $t=\left\lceil 24\ln(1 / \delta)\right\rceil$, $\mathbb{P}(\left| \mathcal{B}(S)-m \right|\geq \varepsilon m)\leq \delta$ in space complexity $\text{O}(\varepsilon^{-2}\log n\log(1 / \delta))$.
---

###### Finding the Majority Element
> [!lemma] Theorem 4
> Consider the algorithm:
>  ```pseudo
>    \begin{algorithm} \caption{Majority($S=(a_{1},\dots,a_{m})$)} 
>    \begin{algorithmic}
>    
>    \State $x\gets a_{1}$
>    \State $\text{count}\gets 1$
>    \For{$a_{i}\in S \backslash \{ a_{1} \}$}
>    \If{$x=a_{i}$}
>    \State $\text{count}\gets \text{count}+1$
>    \Else
>    \State $\text{count}\gets \text{count}-1$
>    \EndIf
>    \If{$\text{count}=0$}
>    \State $x\gets a_{i}$
>    \State $\text{count}\gets 1$
>    \EndIf
>    \EndFor
>    \Return $x$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    If there exists an element $j$ s.t. $\left| \{ i\in[m]:a_{i}=j \} \right|> \frac{m}{ 2}$, then:
>    1. the algorithm returns $j$ in space $\text{O}(\log n+\log m)$.

^bcd0f5

> [!proof]-
> Let $x$ be the output of the algorithm. 
> 1. Firstly, it is quite clear that the algorithm uses $O(\log n+\log m)$ space. Therefore, it suffices to show the correctness.
>    
>    Let $n_{i}:=\left| \{ 1\leq i'\leq i:a_{i'}=j \} \right|$ and $x_{i},\text{count}_{i}$ are the values right after processing $a_{i}$. Then,
>    
>    1. **Claim 1**: For all $i\in[m]$, if $n_{i}>i/2$, then $x_{i}=j$ and $\text{count}_{i}\geq 2n_{i}-i$. If $n_{i}\leq i / 2$, then either $x_{i}=j$ or $\text{count}_{i}\leq i - 2n_{i}+1$.
>       
> 	    We have the following cases:
> 		1. $n_{i}> i / 2$ and $a_{i+1}=j$. Then, $n_{i+1}=n_{i}+1> \frac{i}{2}+1\geq \frac{i+1}{2}$ and $x_{i+1}=j$. Further, $$\text{count}_{i+1}\geq \text{count}_{i}+1\geq 2n_{i}-i+1=2(n_{i}+1)-(i+1)$$
> 		2. $n_{i}> i /2$ and $a_{i+1}\neq j$. Then, $2n_{i}-i-1\geq 0$. If this is greater than $0$, then we are done. Otherwise, we have that $n_{i+1}\leq (i+1) / 2$ and $$\text{count}_{i+1}=1\leq i+1-2n_{i+1}+1$$
> 		3. $n_{i}\leq i /2$ and $a_{i+1}=j$. If $2n_{i+1}> i+1$, then as $n_{i}\leq i / 2$, we have that $n_{i}= i /2$. Hence, we have that $x_{i}=j$ or $\text{count}_{i}\leq 1$. If $x_{i}=j$, then we have that $x_{i+1}=j$ and $\text{count}_{i+1}\geq 1$. If $\text{count}_{i}\leq 1$ with $x_{i}\neq j$, then $x_{i+1}=j$ with $\text{count}_{i+1}\geq 1$.
> 		   
> 		   If $2n_{i+1}\leq i+1$, then $n_{i+1}\leq (i+1) / 2$. If $x_{i+1}\neq j$, then $$\text{count}_{i+1}=\text{count}_{i}-1\leq i-2n_{i}=(i+1)-2(n_{i}+1)+1$$
> 		4. $n_{i}\leq i / 2$ and $a_{i+1} \neq j$. Then, $n_{i+1}\leq (i+1) /2$ and if we don't have $x_{i+1}=j$, if $x_{i}=j$, then $\text{count}_{i+1}=1$. If $x_{i}\neq j$, then:  $$\text{count}_{i+1}\leq \text{count}_{i}+1\leq (i+1)-2n_{i}+1$$
> 	
> 	Therefore, for $m$, as we have that $n_{m}> m /2$, $x=j$.   

^4dfe0d

---
> [!lemma] Theorem 5
> Any deterministic streaming algorithm deciding whether a majority element exists or not requires at least $\Omega(n)$ space.

^989ebb

> [!proof]-
> Let $A$ be a deterministic algorithm that uses at most $n / 2$ bits. We will show that there exists an input for which $A$ fails. 
> 
> Consider ${\mathcal{S}}:={[n] \choose n /2}$. Then, we have that: $$\left| \mathcal{S} \right| ={n \choose n /2}> 2^{n / 2}$$Hence, there exists $S,T\in \mathcal{S}$ distinct s.t. $A$ has the same configuration for. However, there exists $x\in S$ s.t. $x\notin T$. By adding $x$ $n /2$ times, we have that in one input, we have a majority element and in the other we don't. However, $A$ outputs the same result for both the cases. 
> 
> Therefore, any deterministic streaming algorithm that decides whether a majority element exists requires at least $\Omega(n)$ space.

^bd84b0

---
##### Graph Streaming Algorithms
###### Graph Connectivity

> [!lemma] Lemma 1 (Single Cut Edge)
> Let $\text{id}(v)$ denote the bit-representation of $v\in V:=[n]$. Then,
>  ```pseudo
>    \begin{algorithm} \caption{SingleCut($S=(a_{1},\dots,a_{m}),A$)} 
>    \begin{algorithmic}
>    \State $\text{XOR}_{v}\gets 0$ for all $v\in V$
>    \For {$\left\langle e_{i},\pm\right\rangle\in S$}
>    \State $\text{id}(e_{i})\gets \langle{ \text{id}(u) , \text{id}(v) \rangle}$ for $e_{i}=\{ u,v \}$ and $u< v$
>    \State $\text{XOR}_u\gets \text{XOR}_{u}\oplus \text{id}(e_{i})$
>    \State $\text{XOR}_v\gets \text{XOR}_{v}\oplus \text{id}(e_{i})$
>    \EndFor
>    \State $\text{XOR}_{A}\gets \bigoplus_{v\in A} \text{XOR}_{v}$
>    \Return edge $e$ with $\text{id}(e)=\text{XOR}_{A}$. 
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> For any well-behaved graph stream $S:=(a_{1},\dots,a_{m})$ and $A\subseteq V$,
> 1. if $(A,V \backslash A)=\{ e ^{*}\}$ then $\text{SingleCut}(S,A)$ returns $e^{*}$ using $\text{O}(n\log n)$ bits of memory.

^f050f5

> [!proof]-
> Let $e^{*}$ be the one cut edge. We have that: $$\text{XOR}_{A}=\bigoplus_{v\in A}\text{XOR}_{v}=\bigoplus_{v\in A}\bigoplus _{e\in E}\text{id}(e)\mathbb{1}_{v\in e}=\bigoplus _{e\in E}\text{id}(e)\mathbb{1}_{\left| e\cap A \right| =1}=\text{id}(e^{*}) $$
> Further, for each $v\in V$, we keep track of $2\log n$ bits. Hence, we use $\text{O}(n\log n)$ space.

^4ba20e

---
> [!lemma] Lemma 2 (k-Edge Cut)
> ```pseudo
>    \begin{algorithm} \caption{$k$-Cut($S=(a_{1},\dots,a_{m}),A,\widehat{k},g$)} 
>    \begin{algorithmic}
>    \State $h:{n \choose 2}\to [2\widehat{k}]\gets$ a uniform, $2$-wise independent hash function.
>    \State $\text{XOR}_{v}\gets 0$ for all $v\in V$
>    \For {$\left\langle e_{i},\pm\right\rangle\in S$}
>    \If{$h(e_{i})\neq 0$}
>    \Continue
>    \EndIf
>    
>    \State $\text{XOR}_{u}\gets\text{XOR}_{u}\oplus g(e_{i})$
>    \State $\text{XOR}_{v}\gets \text{XOR}_{v}\oplus g(e_{i})$
>    \EndFor
>    \State $\text{XOR}_{A}\gets \bigoplus_{v\in A} \text{XOR}_{v}$
>    \Return edge $e$ with $g(e)=\text{XOR}_{A}$ and `Failure' if not.
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>  For any well-behaved graph stream $S:=(a_{1},\dots,a_{m})$ and $A\subseteq V$,
> 1. if $g(e)=\braket{ \text{id}(u) , \text{id}(v) }$ for $e=\{ u,v \}$ with $u<v$ and $|(A,V \backslash A)|=k$ where $\frac{2}{3}\widehat{k}\leq k\leq \widehat{k}$, then $k\text{-Cut}$ uses $\text{O}(n\log n)$ bits of memory and:$$\mathbb{P}(k\text{-Cut}(S,A)\in (A, V \backslash A))\geq \frac{1}{12}$$
> 2. if $g:{n \choose 2}\to [n^{4\ell}]$ be a uniform, $\ell$-independent hash function where $\ell$ is the smallest even number greater than $20 \log n+1$, then $k\text{-Cut}$ uses $\text{O}(n\log^{2} n)$ bits of memory and $\mathbb{P}(k\text{-Cut}(S,A)\in (A, V \backslash A))$ w.h.p.

^0918e4


> [!proof]-
> We have that: 
> 1. Firstly, with $g=\text{id}$, $$\text{XOR}_{A}=\bigoplus_{v\in A}\text{XOR}_{v}=\bigoplus_{v\in A}\bigoplus_{e\in S}\text{id}(e)\mathbb{1}_{h(e)=0}\mathbb{1}_{v\in e}  =\bigoplus_{e\in S}\text{id}(e)\mathbb{1}_{h(e)=0}\mathbb{1}_{e\in (A , V \backslash A)}= \bigoplus_{e\in (A , V \backslash A)}\text{id}(e)\mathbb{1}_{h(e)=0}  $$
> 	Now, let $Y_{e}=\mathbb{1}_{\{ h(e)=0 \}}$ and $Y:=\sum_{e\in (A, V\backslash A)}^{}Y_{e}$. Then, $\begin{align}\mathbb{P}(k\text{-Cut}(S,A)\notin (A, V \backslash A))\leq \mathbb{P}(Y\neq1)&\end{align}$ where: $$\begin{align}\mathbb{P}(Y=1)&=\mathbb{P}(\exists  e\in (A, V \backslash A): Y_{e}=1\land \forall e\neq e'\in (A, V \backslash A). Y_{e'}=0)\\&=\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(Y_{e}=1\land \forall e\neq e'\in (A, V \backslash A). Y_{e'}=0)\\&=\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(Y_{e}=1)\mathbb{P}(\forall e\neq e'\in (A, V \backslash A). Y_{e'}=0|Y_{e}=1)\\&=\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(Y_{e}=1)(1-\mathbb{P}(\exists e'\neq e\in (A, V \backslash A). Y_{e'}=1|Y_{e}=1))\\&\geq\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(Y_{e}=1)\left( 1-\sum_{e'\neq e\in (A, V \backslash A)}^{}\mathbb{P}( Y_{e'}=1|Y_{e}=1) \right)\\&\geq\sum_{e\in (A , V \backslash A)}^{}\mathbb{P}(Y_{e}=1)\left( 1-\sum_{e'\neq e\in (A, V \backslash A)}^{}\mathbb{P}( Y_{e'}=1) \right)\\&\geq  \frac{k}{2\widehat{k}}\left( 1-\frac{k-1}{2\widehat{k}} \right)\\&\geq \frac{k}{2\widehat{k}}-\left( \frac{k}{2\widehat{k}} \right)^2\geq \frac{1}{12}\end{align}$$
> 	For memory, notice that $\frac{2}{3}\widehat{k}\leq k\leq n^2$ hence $\widehat{k}\in O(n^{2})$. Therefore, saving $h$ requires only $O(\log n)$. As we keep $O(\log n)$ bits for each node $v\in V$, we have $O(n\log n)$. 
> 2. We have that: $$\begin{align}\mathbb{P}\left[\exists k\leq \ell, e_{1},\dots,e_{k}\in {n \choose 2}:\bigoplus_{i\in[k]}g(e_{i})=0\right]&\leq \sum_{1\leq k\leq \ell}\sum_{e_{1},\dots,e_{k}\in {n \choose 2}}^{}\mathbb{P}\left(\bigoplus_{i\in[k]}g(e_{i})=0 \right)\\&= \sum_{1\leq k\leq \ell}{{n \choose 2} \choose k} \frac{1}{n^{4\ell}}\\&\leq \left( \frac{en^{2}}{\ell} \right) \frac{^{\ell}1}{n^{4\ell}}< \frac{1}{n^{2\ell}}< n^{-40}\end{align}$$Furthermore, let $X:=\sum_{e\in (A, V \backslash A)}^{}Y_{e}$. Then, $$\mathbb{P}(X> \ell)\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| > \left( \frac{\ell}{\mathbb{E}[X]}-1 \right)\mathbb{E}[X] \right)\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| >\frac{2\ell-1}{\sqrt{ 3 }}\sqrt{ \mathbb{E}[X] }\right)$$Therefore, by [[Moment|Theorem 2]], $$\mathbb{P}(X > \ell)\leq O\left( \left( \frac{\ell \sqrt{ 3 }}{2(2\ell-1)} \right)^\ell \right)\leq O\left(2^{-\ell}\right)=O(2^{-20\log n})=O(n^{-20})$$Hence by bruteforcing all $g(e)$ for $e\in {n \choose 2}$ and checking with $\text{XOR}_{A}$, we have that:

^533710

- **Corollary**: By running $k\text{-Cut}$ with all possible estimates $\widehat{k}\in\left\{  \left( \frac{2}{3} \right)^jn^{2}  \right\}_{j\in}$ we cover all possible $k$. This should give us an $\text{O}(n\log^3n)$ algorithm that works w.h.p. ^7ce55e
---
> [!lemma] Theorem 3 (Maximal Forest)
> Consider the algorithm:
> ```pseudo
>    \begin{algorithm} \caption{MaximalForest($G$)} 
>    \begin{algorithmic}
>    \State $F\gets (V,\varnothing)$
>    \For{$t\in[\left\lceil \log n\right\rceil]$}
>    \State Let $A_{1},\dots,A_{k}$ be the connected components of $F$.
>    \For{each $A_{i}$}
>    \If {$E(A_{i},V \backslash A_{i})\neq \varnothing$ }
>    \State Find an edge $e\in E(A_{i},V \backslash A_{i})$ using $k$-Cut and add it to $F$.
>    \EndIf
\EndFor
> \While{there is a cycle $C$ in $F$}
> \State Delete an arbitrary edge $e\in C$ from $F$.
\EndWhile
\EndFor
> \Return $F$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Then, $\text{MaximalForest}(G)$ returns a maximal forest.

^88bddb

> [!proof]-
> Assume that $G$ is connected. Then, for any other iteration of the for loop, let $A_{1},\dots,A_{k}$ be the connected components. After the iteration the number of connected components is at most $\frac{k}{2}$. Then, the algorithm terminates in $\log n$ iterations and as we delete all cycles, we have a forest at the end. 

^50642b

- **Corollary**: With Theorem 2, there is a streaming algorithm that computes the maximal forest with space complexity $\text{O}(n\log ^4 n)$ with high probability. ^511eae
---
##### Finding MST
> [!lemma] Theorem 1 (2-Approximation)
> 