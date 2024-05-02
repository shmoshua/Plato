#Definition #FunctionalAnalysis 

> [!definition]
> Let $E$ be a $\mathbb{R}$-vector space. For $A\subseteq E$, the ***convex hull*** $\text{co}(A)$ is defined as the intersection of all [[Convex Set|convex]] subsets of $E$ containing $A$, i.e. $$\text{co}(A)=\bigcap_{A\subseteq C,C\text{ convex}}^{}C$$
---
##### Properties
> [!lemma] Lemma 1
> Let for any set $S$, $\mathbb{R}_{\geq 0}^{(A)}=\{ \lambda:A\to \mathbb{R}_{\geq 0}|\text{supp}(\lambda)\text{ is finite} \}$. Then,  $$\text{co}(A)=\left\{  \left.\sum_{a\in A}^{}\lambda(a)a \right| \lambda\in\mathbb{R}_{\geq 0}^{(A)},\sum_{a\in A}^{}\lambda(a)=1  \right\}$$

> [!proof]-
> $\supseteq$: holds by recursion. 
> 
> $\subseteq$: Firstly, indeed $A$ is contained in RHS. We will show that the RHS is convex. For $\lambda,\mu\in \mathbb{R}^{(A)}_{\leq0}$ s.t. $\sum_{a\in A}^{}\lambda(a)=\sum_{a\in A}^{}\mu(a)=1$. Then, for any $t\in[0,1]$: $$t\left( \sum_{a\in A}^{}\lambda(a) a\right)+(1-t)\left( \sum_{a\in A}^{}\mu(a)a \right) =\sum_{a\in A}^{}\underbrace{ (t\lambda(a)+(1-t)\mu(a)) }_{ =: \xi(a) }a $$Then, $\xi\in \mathbb{R}^{(A)}_{\leq 0}$ and $$\sum_{a\in A}^{}\xi(a)=\sum_{a\in A}^{}(t\lambda(a)+(1-t)\mu(a))=t\sum_{a\in A}^{}\lambda(a)+(1-t)\sum_{a\in A}^{}\mu(a)=t+(1-t)=1$$
> 
> This proves the statement. 
---
> 