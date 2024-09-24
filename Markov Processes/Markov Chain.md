#Markov #Definition 

> [!definition]
> Let $\mathcal{S}$ be an at most countable state space. A ***Markov chain*** is a family of $\mathcal{S}$-valued random variables $(X_{n})_{n\geq 0}$ s.t.:
> 1. for all $n\geq 0$ and $(i_{0},\dots,i_{n},j)\in \mathcal{S}^{n+2}$, $$\mathbb{P}(X_{n+1}=j|X_{0}=i_{0},\dots,X_{n}=i_{n})=P_{i_{n},j}$$where $P\in [0,1]^{\mathcal{S}\times \mathcal{S}}$ s.t. $\sum_{j\in \mathcal{S}}^{}P_{ij}=1$ for all $i\in \mathcal{S}$. 

^a66180

- **Related definition**: $\mathcal{S}$ is called a ***transition probability matrix***. ^46a7c5
- **Related definition**: Similarly, it could be defined as: $\mathbb{P}(X_{n+1}=j|X_{0},\dots,X_{n})=P_{X_{n},j}$ ^fd0c4e
---
##### Properties
> [!lemma] Proposition 1 (Existence of Markov Chains)
> Let $P\in [0,1]^{\mathcal{S\times S}}$ be a transition probability matrix and let $\mu$ be a [[Signed Measure|probability measure]] on $\mathcal{S}$. Then, 
> 1. there exists a Markov chain $(X_{n})_{n\geq 0}$ on some probability space with transition matrix $P$ and initial distribution $\mu$, i.e. $\mathbb{P}(X_{0}=i)=\mu_{i}$.

^d921a8

> [!proof]-
> Wlog we may assume that $\mathcal{S}= [n]$ or $\mathbb{Z}_{\geq 1}$. We now define the step function $\beta:\mathcal{S}\times (\{ 0 \}\cup\mathcal{S})\to[0,1]$ where $\beta(i,0)=0$ and $\beta(i,j)=\sum_{k=1}^{j}P_{ik}$. Now, define $F:\mathcal{S}\times[0,1)\to \mathcal{S}$ s.t. $F(i,u)=j$ if $\beta(i,j-1)\leq u <\beta(i,j)$. In addition, set $\alpha:\{ 0 \}\cup \mathcal{S}\to[0,1]$ where $\alpha(0)=0$ and $\alpha(j)=\sum_{k=1}^{j}\mu_{k}$. Similarly, we define $f:[0,1)\to \mathcal{S}$ where $f(u)=j$ if $\alpha(j-1)\leq u<\alpha(j)$. 
> 
> Finally, let $\{ U_{n} \}_{n\geq 0}$ be a sequence of mutually independent uniformly random variables on $[0,1)$. Then, we set: $$X_{n}:=\begin{cases}f(U_{0})&n=0\\F(X_{n-1},U_{n})&n\geq 1\end{cases}$$Fix $(i_{0},\dots,i_{n})\in \mathcal{S}^{n+1}$. Observe that we have: $$\begin{align}\mathbb{P}(X_{0}=i_{0},\dots,X_{n}=i_{n})&=\mathbb{P}(U_{0}\in [\alpha_{i_{0}-1},\alpha_{i_{0}})\land U_{k}\in [\beta_{i_{k-1},i_{k}-1},\beta_{i_{k-1},i_{k}}), \forall k\in [n])\\&=\mu_{i_{0}}\cdot P_{i_{0} i_{1}}\dots P_{i_{n-1},i_{n}}\\&=\mathbb{P}(X_{0}=i_{0},\dots,X_{n-1}=i_{n-1})\cdot P_{i_{n-1}i_{n}}\end{align}$$This shows that $(X_{n})_{n\geq 0}$ is a Markov chain.

^8dc0d8
