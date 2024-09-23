#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to(0,1]$. 
> 1. The ***bin-packing problem*** aims to find the minimal number $k$ of bins of size 1 s.t. every item can be put into some bin, i.e. $$\text{OPT}(I)\in\underset{ B=\{ b_{1},\dots,b_{k} \},s(b_{i})\leq 1,\bigsqcup_{i}^{}b_{i}=\mathcal{S} }{ \arg\min }\left| B \right| $$
- **Related definition**: we extend $s$ to $s:\mathcal{P}(\mathcal{S})\to (0,n],X\mapsto \sum_{i\in X}^{}s_{i}$. 
- **Remark**: $k_{\text{OPT}}\geq s(\mathcal{S})=:S$.
---
##### Properties
> [!lemma] Theorem 1 (First-Fit, Greedy)
> The First-Fit algorithm works as follows:$$\begin{align}\\ 
&\textbf{Algorithm } \text{FirstFit}(\mathcal{S})\\ 
&B\to \varnothing\\
&\textbf{for } i\in [n] \textbf{ do:} \\
& \textbf{If } \text{} \textbf{ then:}
\end{align}$$is a $2$-approximation algorithm.

 > [!proof]+
 > We have that:
 > 1. **Claim 1**: for $\text{FirstFit}(I)$, there exists at most one bin $B$ with $s(B)\leq 1/ 2$.  
 >    Assume otherwise. 

---
> [!lemma] Theorem 2 (Sorted-First-Fit, SFF)
> We sort the items by size and apply First-Fit.
> 1. SFF is a $3 /2$-approximation algorithm.

> [!proof]+
> Modulo reindexing, we may assume that $s_{1}\geq s_{2}\geq\dots\geq s_{n}$ is decreasing. Assume that $\text{SortedFirstFit}$ needs $k$ bins $B_{1},\dots,B_{k}$. Further, let $r$ be the number of items that are larger than $s_{i}>\frac{1}{2}$. Then, observe that all such items need to be in separate bins. 
> 
> 1. **Case 1: $n_{1}\geq \frac{2}{ 3} k$** 
>    Then, $k_{\text{OPT}}\geq n_{1}\geq \frac{2}{3}k$ and $k\leq \frac{3}{2}k_{\text{OPT}}$.
>  2. **Case 2: $n_{1}< \frac{2}{3}k$**
>     Let's denote the first $k_{1}:=\left\lceil  \frac{2k}{3} \right\rceil-1$ bins early and the other $k_{2}:=k-k_{1}$ bins late. Then, $s_{1},\dots,s_{r}$ fit into early bins so all items in the late bins have at 
>    Then, in the output of SFF, we have $n_{1}$ bins that are more full than 1/2 and 

- **Remark**: It is $\mathcal{NP}$-hard to get a better factor than $3 / 2$.