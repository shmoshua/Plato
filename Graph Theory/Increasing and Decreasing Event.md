#Definition #Combinatorics 

> [!definition]
> Let $\Omega:=\{ 0,1 \}^N$ with $\mathcal{A}:=2^\Omega$ and there exists $p_{1},\dots,p_{N}$ s.t. $\mathbb{P}(\omega)=\prod_{i:\omega_{i}=1}^{}p_{i}\prod_{j:\omega_{j}=0}(1-p_{j})$.
> 1. An event $A\subseteq \Omega$ is ***increasing*** if for every $x\leq y\in \Omega$,  if $x\in A$ then $y\in A$.
> 2. An event $A\subseteq \Omega$ is ***decreasing*** if for every $x\leq y\in \Omega$,  if $y\in A$ then $x\in A$.

^8f65f7

- **Remark**: If $A\subseteq\Omega$ is increasing, then $\Omega \backslash A$ is decreasing as for every $x\leq y$, if $y\notin A$ then $x\notin A$ ^138747
---
##### Properties
> [!lemma] Theorem 1 (Correlation Inequality)
> Let $A,B\subseteq \Omega$. 
> 1. If $A,B$ are both increasing or both decreasing, then: $\mathbb{P}(A\cap B)\geq \mathbb{P}(A)\mathbb{P}(B)$
> 2. If $A$ is increasing but $B$ decreasing or vice versa, then: $\mathbb{P}(A\cap B)\leq \mathbb{P}(A)\mathbb{P}(B)$

^ec589e


> [!proof]-
> We prove it by induction on $N$. 
> 1. If $N=1$, then there are three increasing events $\varnothing,\{ 0,1 \},\{ 1 \}$. Then, assume $A,B$ are both increasing. 
> 	1. If either $A,B$ is $\varnothing$, then $0=\mathbb{P}(A\cap B)\geq \mathbb{P}(A)\mathbb{P}(B)=0$.
> 	2. If either $\{ A,B \}$ is $\{ 0,1 \}$ (wlog $A$), then $\mathbb{P}(A\cap B)=\mathbb{P}(B)$.
> 	3. If $A=B=\{ 1 \}$, then $\mathbb{P}(A\cap B)=\mathbb{P}(A)\geq \mathbb{P}(A)^{2}=\mathbb{P}(A)\mathbb{P}(B)$.
> 2. If $N> 2$, let $A,B$ be both increasing. We define for $i=0,1$: $$A_{i}:=\{ x\in \{ 0,1 \}^{N-1}: (x,i)\in A \},\quad B_{i}:=\{ x\in \{ 0,1 \}^{N-1}: (x,i)\in B \}$$Then, $A_{i}$, $B_{i}$ is increasing as $A,B$ are both increasing. Further, $A_{0}\subseteq A_{1}$ as if $x\in A_{0}$, then $(x,0)\in A$ and $(x,1)\in A$. Hence, $x\in A_{1}$. Similarly $B_{0}\subseteq B_{1}$. 
> 	
> 	Let $a:=\mathbb{P}(A),a_{0}:=\mathbb{P}(A_{0}),a_{1}:=\mathbb{P}(A_{1}),b:=\mathbb{P}(B),b_{0}:=\mathbb{P}(B_{0}),b_{1}:=\mathbb{P}(B_{1})$. Then, $$a=\mathbb{P}(A)=\mathbb{P}(A_{0})(1-p_{N})+\mathbb{P}(A_{1})p_{N}=a_{0}(1-p_{N})+a_{1}p_{N}$$Therefore, $$\begin{align}\mathbb{P}(A\cap B)&=\mathbb{P}(A_{0}\cap B_{0})(1-p_{N})+\mathbb{P}(A_{1}\cap B_{1})p_{N}\geq a_{0}b_{0}(1-p_{N})+a_{1}b_{1}p_{N}\\\mathbb{P}(A)\mathbb{P}(B)&=(a_{0}(1-p_{N})+a_{1}p_{N})(b_{0}(1-p_{N})+b_{1}p_{N})\end{align}$$Hence, $$\begin{align}\mathbb{P}(A\cap B)-\mathbb{P}(A)\mathbb{P}(B)&=a_{0}b_{0}-a_{0}b_{0}p_{N}+a_{1}b_{1}p_{N}-a_{0}b_{0}(1-p_{N})^{2}\\&\quad \quad \quad \quad \quad -(a_{0}b_{1}+a_{1}b_{0})(1-p_{N})p_{N}-a_{1}b_{1}p_{N}^{2}\\&=a_{0}b_{0}(p_{N}-p_{N}^{2})+a_{1}b_{1}(p_{N}-p_{N}^{2})-(a_{0}b_{1}+a_{1}b_{0})(1-p_{N})p_{N}\\&=(a_{1}-a_{0})(b_{1}-b_{0})p_{N}(1-p_{N})\\&\geq 0\end{align}$$
> 
> If $A,B$ are both decreasing, then $\Omega \backslash A,\Omega \backslash B$ are both increasing and: $$\begin{align}\mathbb{P}(A\cap B)&=\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(A\cup B)\\&=\mathbb{P}(A)+\mathbb{P}(B)-1+\mathbb{P}(\Omega \backslash A\cap\Omega \backslash B)\\&\geq\mathbb{P}(A)+\mathbb{P}(B)-1+\mathbb{P}(\Omega \backslash A)\mathbb{P}(\Omega \backslash B)\\&=\mathbb{P}(A)\mathbb{P}(B)\end{align}$$

^541d26
