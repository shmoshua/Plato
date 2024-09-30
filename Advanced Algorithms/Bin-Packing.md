#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to(0,1]$. 
> 1. The ***bin-packing problem*** aims to find the minimal number $k$ of bins of size 1 s.t. every item can be put into some bin, i.e. $$\text{OPT}(I)\in\underset{ B=\{ b_{1},\dots,b_{k} \},s(b_{i})\leq 1,\bigsqcup_{i}^{}b_{i}=\mathcal{S} }{ \arg\min }\left| B \right| $$

^06f901

- **Related definition**: we extend $s$ to $s:\mathcal{P}(\mathcal{S})\to (0,n],X\mapsto \sum_{i\in X}^{}s_{i}$.  ^d65196
- **Remark**: $k_{\text{OPT}}\geq s(\mathcal{S})=:S$. ^a84502
---
##### Properties
> [!lemma] Theorem 1 (First-Fit)
> 
>    ```pseudo
>    \begin{algorithm} \caption{FirstFit($\mathcal{S},s$)} 
>    \begin{algorithmic}
>    \State $\mathcal{B}\to \empty$
>    \For{$i\in [n]$}
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
> We have that 
> 1. $\text{FirstFit}$ is a $2$-[[approximation algorithm]].

^769d08

 > [!proof]-
 > We have that:
 > 1. **Claim 1**: for $\mathcal{B}:=\text{FirstFit}(I)$, there exists at most one bin $B\in \mathcal{B}$ with $s(B)\leq 1/ 2$.  
 >    Assume otherwise, i.e. there exists $B_{i},B_{j}\in \mathcal{B}$ with $i<j$ s.t. $s(B_{i}),s(B_{j})\leq \frac{1}{2}$. Then, the algorithm could have put all the items in $B_{i}$ and not create $B_{j}$ which is a contradiction.
 > 
 > Assume that $\mathcal{B}:=\text{FirstFit}(I)$ where $\left| \mathcal{B} \right|=k$. Then, by Claim 1, $$k_{\text{OPT}}\ge s(\mathcal{S})>\frac{k-1}{2}$$ Therefore, $k\leq 2\cdot k_{\text{OPT}}$.

^db3116

---
> [!lemma] Theorem 2 (Sorted-First-Fit, SFF)
>    ```pseudo
>    \begin{algorithm} \caption{SortedFirstFit($\mathcal{S},s$)} 
>    \begin{algorithmic}
>    \State Sort items in $\mathcal S$ by $s$ in decreasing order
>    \State \Call{FirstFit}{$\mathcal S,s$}
>    
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> We have that:
> 1. SFF is a $3 /2$-approximation algorithm.

^c04d44

> [!proof]-
> Modulo reindexing, we may assume that $s_{1}\geq s_{2}\geq\dots\geq s_{n}$ is decreasing. Assume that $\text{SortedFirstFit}$ needs $k$ bins $B_{1},\dots,B_{k}$. Further, let $r$ be the number of items that are larger than $s_{i}>\frac{1}{2}$. Then, observe that all such items need to be in separate bins. 
> 
> 1. **Case 1: $n_{1}\geq \frac{2}{ 3} k$** 
>    Then, $k_{\text{OPT}}\geq n_{1}\geq \frac{2}{3}k$ and $k\leq \frac{3}{2}k_{\text{OPT}}$.
>  2. **Case 2: $n_{1}< \frac{2}{3}k$**
>     Let's denote the first $k_{1}:=\left\lceil  \frac{2k}{3} \right\rceil-1$ bins early and the other $k_{2}:=k-k_{1}$ bins late. Then, $s_{1},\dots,s_{r}$ fit into early bins so all items in the late bins have size at most $\leq \frac{1}{2}$. In particular, every late bin should contain at least two items, except maybe the last bin. 
>     
>     Therefore, there exists at least $2(k_{2}-1)+1=2k-2\left\lceil  \frac{2k}{3} \right\rceil+1>k_{1}-1$ items in the late bins. 
>     
>    Then, in the output of SFF, we have $n_{1}$ bins that are more full than 1/2 and 

^3e5c2c

- **Remark**: It is $\mathcal{NP}$-hard to get a better factor than $3 / 2$.
---
##### FPTAS

^a03360

> [!lemma] Proposition 3
> With the assumptions that:
> 1. All items have size at least $\varepsilon$ for some $\varepsilon>0$.
> 2. There are only $k$ possible sizes.
> ```pseudo
>    \begin{algorithm} \caption{ExactBinPacking($I,\varepsilon,k$)} 
>    \begin{algorithmic}
>    \State Enumerate all possible bin configuration.
>    \Return the best bin configuration.
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    solves bin packing in $O(n^R)$ time where $R$ is a constant.

^62d5f8

> [!proof]-
> Going through all possible bin configuration with the given $n$ items is upper bounded by going through all possible configurations of $n$ bins, choosing from arbitrarily many items of $k$ fixed sizes.  Let $M:=\left\lceil \frac{1}{\varepsilon}\right\rceil$. Then, each bin has at most $M$ items. By the second assumption, we have at most $R:={M+k \choose M}$ configurations in a bin. By choosing $n$ bins from these $R$ bins, we have at most $${n+R \choose n}={n+R\choose R}\leq(n+R)^R=O(n^R) $$

^5e1d26

---
> [!lemma] Proposition 4
> With the assumption that:
> 1. All items have size at least $\varepsilon$ for some $\varepsilon>0$,
> ```pseudo
>    \begin{algorithm} \caption{PTAS-BinPacking($I,\varepsilon$)} 
>    \begin{algorithmic}
>    \State $k\gets \left\lceil 1/\varepsilon^{2}\right\rceil$
>    \State $Q\gets \left\lfloor n\varepsilon^{2}\right\rfloor$
>    \State Partition $n$ items into $k$ non-overlapping groups $G_{1},\dots,G_{k}$, each with $\leq Q$ items. 
>    \For{$i\in [k]$}
>    \State $i_{\text{max}}\gets \max_{u\in G_{i}}s(u)$
>    \For{$u\in G_{i}$}
>    \State $s(u)\gets i_{\max}$\EndFor
>    \EndFor
>    \State Denote the modified instance as $\varepsilon$.
>    \Return \Call{ExactBinPacking}{$J,\varepsilon,k$}
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    is a [[PTAS]] for bin packing. In particular, it is an $(1+\varepsilon)$-approximation algorithm.

^cb3b26

> [!proof]-
> By the assumption, we have that $\left| \text{OPT}(I) \right|\geq s(I)\geq n\varepsilon$. Then, $Q=\left\lfloor n\varepsilon^{2}\right\rfloor\leq \varepsilon \cdot \left| \text{OPT}(I) \right|$.
> 1. **Claim 1: $\left| \text{OPT}(I) \right|\leq \left| \text{OPT}(J) \right|\leq \left| \text{OPT}(I) \right|+Q-1$**
>    The first inequality is trivial, as rounding up only increases the number of bins. For the second inequality, denote the items in $I$ in decreasing order by $s_{1}\geq\dots\geq s_{n}$. 
>    
>    We will pack $J$ by taking the $Q-1$ largest items in $J$ and pack each of them in its own bin. Denote the instance of the remaining $n-Q+1$ items by $J'$. Then, $J'$ can be as most as hard as $I$. Assume that all items in $J$ and $J'$ are also sorted in descending order and consider the $j$-th item in $J'$ for $j\in [n-Q+1]$, which is the $j+Q-1$-th item in $J$. This is obtained by the $j+Q-1$-th item rounding up. The rounding procedure replaced the size $s_{j+Q-1}$ by another size in the same group, so it could increase the item by at most $Q-1$ ‘positions’ to size $s_{j}$. Hence, we have shown that the $j$-th item in $J'$ is at most as large as the $j$-th item in $I$. Therefore, $\left| \text{OPT}(J') \right|\leq \left| \text{OPT}(I) \right|$. Therefore, $$\left| \text{OPT}(J) \right| \leq \left| \text{OPT}(J') \right| +Q-1\leq \left| \text{OPT}(I) \right| +Q-1$$
>  
>  Then, $$\left| \text{PTAS-BinPacking}(I) \right| =\left| \text{OPT}(J) \right|\leq (1+\varepsilon)\left| \text{OPT}(I) \right| $$

^697fb8

---
> [!lemma] Theorem 5 (FPTAS)
>  ```pseudo
>    \begin{algorithm} \caption{FPTAS-BinPacking($I,\varepsilon$)} 
>    \begin{algorithmic}
>    \State $\varepsilon\gets \min\left\{  \frac{1}{2}, \frac{\varepsilon}{2}  \right\}$
>    \State $X\gets \{ u\in \mathcal{S}:s_{u}< \varepsilon' \}$
>    \State $P\gets$ \Call{PTAS-BinPacking}{$\mathcal{S  }\backslash X,\varepsilon'$}
>    \State $P'\gets$Call \Call{FirstFit}{$X$} on $P$ and add items in $X$ to $P$.
>    \Return $P'$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    uses $\leq(1+\varepsilon)\left| \text{OPT}(I) \right|+1$ bins.

^58af47

> [!proof]+
> 

^4776b1
