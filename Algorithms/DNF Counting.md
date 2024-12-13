#Definition #Algorithms 

> [!definition]
> Let $X=\bigvee_{i=1}^m\bigwedge_{j} F_{j}$ be a formula in [[Disjunctive Normal Form|disjunctive normal form (DNF)]]. 
> 1. The ***DNF counting problem*** aims to find the number $N_{\text{OPT}}$ of satisfying assignments.

^d2f429

- **Remark**: Sampling with random assignments depend heavily on the number of satisfying assignment (e.g. if $N_{\text{OPT}} / 2^n$ is very small)  ^684725
---
##### Properties
> [!lemma] Theorem 1 (Sampling)
> Let $X=\bigvee_{i=1}^mC_{i}$ and let $s:[m]\times \{ 0,1 \}^n\to \{ 0,1 \}$ denote the satisfiability matrix, i.e. $$s(i,j)=1\iff C_{i}\text{ is satisfiable with assignment }\alpha_{j}$$Then, 
>    ```pseudo
>    \begin{algorithm} \caption{DNF-Count($I$)} 
>    \begin{algorithmic}
>    \State $X\gets 0$
>    \State $M\gets \sum_{i=1}^{m}2^{n-\left| C_{i} \right|}$
>    \For {$t\in[k]$}
>    \State $C_{i}\gets$ Sample one of the $m$ clauses with probability $2^{n-\left| C_{i} \right|} / M$ for $i$.
>    \State $\alpha_{j}\gets$ Sample one of the $2^{n-\left| C_{i} \right|}$ satisfying assignments for $C_{i}$ uniformly at random. 
>    \State $\text{IsTopMost}\gets \text{true}$
>    \For{$\ell\in[j-1]$}
>    \If{$s(i,\ell)=1$}
>    \State $\text{IsTopMost}\gets \text{False}$
\EndIf
> \EndFor
> \If{$\text{IsTopMost}$}
> \State $X\gets X+1$
\EndIf
> \EndFor
> \Return $MX/k$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> We have that 
> 1. for $k=\frac{9m}{\varepsilon^{2}}$, $\text{DNF-Count}$ runs in $O\left( \frac{m^{2}n(m+n)}{\varepsilon^{2}} \right)$ and therefore is a [[FPRAS]].

^44eec7

> [!proof]-
> We have that: 
> 1. **Claim 1: $\text{DNF-Count}$ samples a '1' in $s$ uniformly randomly**.
>    Let $s(i,j)=1$. Then, $$\begin{align}\mathbb{P}(C_{i},\alpha_{j}\text{ are chosen})&=\mathbb{P}(C_{i}\text{ is chosen})\mathbb{P}(\alpha_{j}\text{ is chosen}|C_{i}\text{ is chosen})\\&=\frac{2^{n-\left| C_{i} \right| }}{M}\cdot \frac{1}{2^{n-\left| C_{i} \right| }}=\frac{1}{M}\end{align}$$
> 2. **Claim 2: $\mathbb{P}(\left| \text{DNF-Count}(I)-\text{SOL}(I) \right|\leq \varepsilon \cdot \text{SOL}(I))\geq \frac{3}{4}$**
>    We have that: $p:=\mathbb{P}(\text{isTopMost}=1)=\text{SOL}(I) / M$ by Claim 1. Therefore, $\mathbb{E}[X]=kp$. Hence, $$\begin{align}\mathbb{P}(\left| \text{DNF-Count}(I)-\text{SOL}(I) \right|\geq \varepsilon \cdot \text{SOL}(I))&=\mathbb{P}\left( \left| X-kp\right| \geq \varepsilon kp  \right) \\&\leq 2\exp\left( -\frac{\varepsilon^{2}kp}{3} \right)\\&= 2\exp\left( -\frac{3m\cdot  \text{SOL}(I)}{M} \right)\\&\leq 2\exp(-3)\\&\leq 1 /4\end{align}$$
> 
> Hence, there are $k\in O\left( \frac{m}{\varepsilon^{2}} \right)$ iterations in total. In each iteration, we spend $O(m+n)$ time sampling and $O(nm)$ for checking if that sample is topmost. Therefore, the runtime of the algorithm is: $$O\left( \frac{m^2n(m+n)}{\varepsilon^{2}} \right)$$
>   

^600789

---
##### Examples
> [!h] Example 1
> Let $G$ be a connected graph and $E'\subseteq E(G)$ where: $$\mathbb{P}(e\in E')=p, \quad \forall e\in E$$
> We would like to compute $P:=\mathbb{P}(G\backslash E'\text{ is disconnected})$.
> 1. $G \backslash E'$ is disconnected if and only if $E'$ contains a [[Cut (Graph)|cut set]].
> 2. $G \backslash E'$ is disconnected if and only if: $$\bigvee_{\text{cut set }C}\bigwedge_{e\in C}\neg e\text{ is satisfied}$$
> 3. If $p^s\geq \frac{1}{n^4}$, then we can use $O(n^4 \log(1 / \delta) / \varepsilon^{2})$ samples to approximate it. 
> 4. if $p^s\leq \frac{1}{n^4}$, we ignore the cuts of size $4s$. 
> 	$$\mathbb{P}(\exists \text{cut of size }\geq 4s\text{ is in }E')\leq \sum_{i=4s}^{\infty}\#\text{cuts of size }i\cdot  p^i=\sum_{i=4s}^{\infty}(n^{2 / s}\cdot  p)^i\leq \sum_{i=4s}^{\infty}p^{i/2}=(p^{1/2})^{4s}\cdot \Theta(1)\leq p ^{2s}\leq p\cdot \frac{1}{n^2}$$

^8222ce

> [!proof]+
> 