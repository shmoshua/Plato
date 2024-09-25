#Definition #Markov 

> [!definition]
> Let $(B_{i})_{i=1}^\infty$ be a family of mutually independent $\text{Ber}\left( \frac{1}{2} \right)$ random variables. 
> 1. The ***random walk*** on $\mathbb{Z}$ is defined as: $$X_{n}:=\sum_{i=1}^{n}B_{i},\quad X_{0}:=0$$
> 2. The ***random walk*** on $\mathbb{Z}^d$ is defined as above where $(B_{i})$ are infinitely many mutually independent $N_{d}$-valued uniform random variables where $N_{d}$ denotes the set of nearest neighbors of $0\in \mathbb{Z}^d$.

^0af11e

- **Related definition**: The ***time of first return*** to $0$ is a random variable $$\rho_{0}:=\inf\{n\geq 1:X_{n}=0 \in \mathbb{Z}^d\}$$ ^3b4697
- **Related definition**: The random walk is ***recurrent*** if $\mathbb{P}(\rho_{0}<\infty)=1$, ***transient*** if otherwise. ^15327c
---
##### Properties
> [!lemma] Proposition 1
> A random walk on $\mathbb{Z}^d$ is a Markov process with transition probability

^6363a1

> [!proof]-
> Let $n\geq 0$ and $(i_{0},\dots,i_{n},j)\in \mathcal{S}^{n+2}$. Then, $$\begin{align}\mathbb{P}(X_{n+1}=j|X_{0}=i_{0},\dots,X_{n}=i_{n})&=\begin{cases} \frac{1}{2d}&\text{if }j-i_{n}\in N_{d}\\0&\text{otherwise}\end{cases}\end{align}$$

^82c078

---
Let $\rho_{0}^{(n)}$ denote the time of $n$-th return to $0\in \mathbb{Z}^d$, i.e. formally, $\rho_{0}^{(1)}=\rho_{0}$, and if $\rho_{0}^{(n-1)}<\infty$, then $$\rho_{0}^{(n)}=\begin{cases}\inf\{ m>\rho_{0}^{(n-1)}: X_{m}=0\in \mathbb{Z}^d \}&\rho_{0}^{(n-1)}<+\infty\\ \infty&\rho_{0}^{(n-1)}=+\infty\end{cases}$$Then, $$\begin{align}\mathbb{P}(\rho_{0}^{(n+1)}<\infty)&=\sum_{m=1}^{\infty}\sum_{M=m+1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}=m\land M=\text{inf}\{ m'>m :X_{m'}=0\})\\&=\sum_{m=1}^{\infty}\sum_{M=m+1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}=m\land G(B_{m+1},\dots,B_{M})=1)\end{align}$$where $G:N_{d}^{M-m}\to \{ 0,1 \}$ with: $$G(\ell_{1},\dots,\ell_{M-m}):=\begin{cases}1&\text{if }\sum_{i=1}^{j}\ell_{i}\neq 0,\forall j<M-m\land \sum_{i=1}^{M-m}=0\\0&\text{otherwise}\end{cases}$$As the first event only depends on $B_{1},\dots,B_{m}$ and the rest uses $B_{m+1},\dots,B_{M}$, we have that: $$\begin{align}\mathbb{P}(\rho_{0}^{(n+1)}<\infty)&=\sum_{m=1}^{\infty}\sum_{M=m+1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}=m)\mathbb{P}( G(B_{m+1},\dots,B_{M})=1)\\&=\sum_{m=1}^{\infty}\sum_{M=m+1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}=m)\mathbb{P}( \rho_{0}^{(1)}=M-m)\\&=\sum_{m=1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}=m)\sum_{M=1}^{\infty}\mathbb{P}( \rho_{0}^{(1)}=M)\\&=\mathbb{P}(\rho_{0}^{(n)}<+\infty)\mathbb{P}(\rho_{0}^{(1)}<+\infty)\end{align}$$Therefore, $\mathbb{P}(\rho_{0}^{(n)}<\infty)=\mathbb{P}(\rho_{0}^{(1)}<\infty)^n$.

---
Let $T_{0}:=\sum_{i=0}^{\infty}\mathbb{1}_{\{ 0 \}}(X_{n})$. Then, $T_{0}\geq 1$ and $T_{0}>n\iff\rho_{0}^{(n)}<+\infty$. Thus, $$\mathbb{E}(T_{0})=\sum_{n=0}^{\infty}\mathbb{P}(T_{0}>n)=1+\sum_{n=1}^{\infty}\mathbb{P}(\rho_{0}^{(n)}<\infty)=1+\sum_{n=1}^{\infty}\mathbb{P}(\rho_{0}^{(1)}<\infty)^n$$  Therefore, $\mathbb{E}(T_{0})=\frac{1}{1-\mathbb{P}(\rho_{0}^{(1)}<\infty)}=\frac{1}{\mathbb{P}(\rho_{0}^{(1)}=\infty)}$
1. $\mathbb{P}(T_{0}<+\infty)>0$ then $\mathbb{P}(\rho_{0}^{(1)}<+\infty)<1$ and by the formula $\mathbb{E}(T_{0})<+\infty$.
2. $\mathbb{E}(T_{0})=\infty$ then $\mathbb{P}(T_{0}=\infty)=1$. 
---
> [!lemma] Theorem 
> The random walk on $\mathbb{Z}^d$ is recurrent if $d\leq 2$.

> [!proof]+
> We have that: $\mathbb{E}(T_{0})=\sum_{n=0}^{\infty}\mathbb{P}(X_{n}=0)$. Thus, $X_{n}$ is recurrent if and only if $\sum_{n=0}^{\infty}\mathbb{P}(X_{n}=0)=+\infty$. We have: $$\begin{align}\mathbb{P}(X_{2n}=k)&=\sum_{\ell\in \mathbb{Z}^d}^{}\mathbb{P}(X_{n}=\ell \land X_{2n}-X_{n}=k-\ell)\\&=\sum_{\ell\in \mathbb{Z}^d}^{}\mathbb{P}(X_{n}=\ell)\mathbb{P}( X_{2n}-X_{n}=k-\ell)\\&=\sum_{\ell\in \mathbb{Z}^d}^{}\mathbb{P}(X_{n}=\ell)\mathbb{P}( X_{n}=k-\ell)\\&\leq \left(\sum_{\ell\in \mathbb{Z}^d}^{} (\mathbb{P}(X_{n}=\ell))^2 \right)^{1/2}\left(\sum_{\ell\in \mathbb{Z}^d}^{} (\mathbb{P}(X_{n}=k-\ell))^2 \right)^{1/2} \end{align}$$