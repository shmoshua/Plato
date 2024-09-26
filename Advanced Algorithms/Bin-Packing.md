#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to(0,1]$. 
> 1. The ***bin-packing problem*** aims to find the minimal number $k$ of bins of size 1 s.t. every item can be put into some bin, i.e. $$\text{OPT}(I)\in\underset{ B=\{ b_{1},\dots,b_{k} \},s(b_{i})\leq 1,\bigsqcup_{i}^{}b_{i}=\mathcal{S} }{ \arg\min }\left| B \right| $$
- **Related definition**: we extend $s$ to $s:\mathcal{P}(\mathcal{S})\to (0,n],X\mapsto \sum_{i\in X}^{}s_{i}$. 
- **Remark**: $k_{\text{OPT}}\geq s(\mathcal{S})=:S$.
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

 > [!proof]-
 > We have that:
 > 1. **Claim 1**: for $\mathcal{B}:=\text{FirstFit}(I)$, there exists at most one bin $B\in \mathcal{B}$ with $s(B)\leq 1/ 2$.  
 >    Assume otherwise, i.e. there exists $B_{i},B_{j}\in \mathcal{B}$ with $i<j$ s.t. $s(B_{i}),s(B_{j})\leq \frac{1}{2}$. Then, the algorithm could have put all the items in $B_{i}$ and not create $B_{j}$ which is a contradiction.
 > 
 > Assume that $\mathcal{B}:=\text{FirstFit}(I)$ where $\left| \mathcal{B} \right|=k$. Then, by Claim 1, $$k_{\text{OPT}}\ge s(\mathcal{S})>\frac{k-1}{2}$$ Therefore, $k\leq 2\cdot k_{\text{OPT}}$.

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

- **Remark**: It is $\mathcal{NP}$-hard to get a better factor than $3 / 2$.
---
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

> [!proof]+
> Let $M:=\left\lceil \frac{1}{\varepsilon}\right\rceil$. Then, each bin has at most $M$ items.
