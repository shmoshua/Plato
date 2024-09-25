#Definition #Markov 

> [!definition]
> Let $(B_{i})_{i=1}^\infty$ be a family of mutually independent $\text{Ber}\left( \frac{1}{2} \right)$ random variables. 
> 1. The ***random walk*** on $\mathbb{Z}$ is defined as: $$X_{n}:=\sum_{i=1}^{n}B_{i},\quad X_{0}:=0$$
> 2. The ***random walk*** on $\mathbb{Z}^d$ is defined as above where $(B_{i})$ are infinitely many mutually independent $N_{d}$-valued uniform random variables where $N_{d}$ denotes the set of nearest neighbors of $0\in \mathbb{Z}^d$.

^0af11e

---
##### Properties
> [!lemma] Proposition 1
> A random walk on $\mathbb{Z}^d$ is a Markov process with transition probability

^6363a1

> [!proof]-
> Let $n\geq 0$ and $(i_{0},\dots,i_{n},j)\in \mathcal{S}^{n+2}$. Then, $$\begin{align}\mathbb{P}(X_{n+1}=j|X_{0}=i_{0},\dots,X_{n}=i_{n})&=\begin{cases} \frac{1}{2d}&\text{if }j-i_{n}\in N_{d}\\0&\text{otherwise}\end{cases}\end{align}$$

^82c078
