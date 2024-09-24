#Markov #Definition 

> [!definition]
> Let $\mathcal{S}$ be an at most countable state space. A ***Markov chain*** is a family of $\mathcal{S}$-valued random variables $(X_{n})_{n\geq 0}$ s.t.:
> 1. for all $n\geq 0$ and $(i_{0},\dots,i_{n},j)\in \mathcal{S}^{n+2}$, $$\mathbb{P}(X_{n+1}=j|X_{0}=i_{0},\dots,X_{n}=i_{n})=P_{i_{n},j}$$where $P\in [0,1]^{\mathcal{S}\times \mathcal{S}}$ s.t. $\sum_{j\in \mathcal{S}}^{}P_{ij}=1$ for all $i\in \mathcal{S}$. 
- **Related definition**: $\mathcal{S}$ is called a ***transition probability matrix***.
- **Related definition**: Similarly, it could be defined as: $\mathbb{P}(X_{n+1}=j|X_{0},\dots,X_{n})=P_{X_{n},j}$
---
##### Properties
> [!lemma] Proposition 1 (Existence of Markov Chains)
> Let $P\in [0,1]^{\mathcal{S\times S}}$ be a transition probability matrix and let $\mu$ be a [[Signed Measure|probability measure]] on $\mathcal{S}$. Then, 
> 1. there exists a Markov chain $(X_{n})_{n\geq 0}$ on some probability space with transition matrix $P$ and initial distribution $\mu$, i.e. $\mathbb{P}(X_{0}=i)=\mu_{i}$.