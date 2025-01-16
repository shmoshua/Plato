#Definition #PAI 

> [!definition]
> Let $p$ be a [[Distribution|probability distribution]] ***Markov Chain Monte Carlo (MCMC)*** refers to a class of algorithms for sampling from $p$, where direct sampling is computationally challenging. 

^265dad

---
##### Properties
> [!lemma] Theorem 1 (Metropolis-Hastings)
> For a sample space $\mathcal{S}$, consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{Metropolis-Hastings($\rho,q:\mathcal{S}\to \mathbb{R}, R:\mathcal{S}\times \mathcal{S}\to \mathbb{R}$)}
> \begin{algorithmic}
> \State $x_{0}\gets$ sampled by $\rho$.
> \For{$t\geq 0$}
> \State $x'\gets R(X'|X=x_{t})$
> \State $X_{t+1}\gets x'$ with probability $\alpha(x'|x):=\min\left\{  1, \frac{q(x')R(x|x')}{q(x)R(x'|x)}  \right\}$ and otherwise $x$.
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. $(X_{t})_{t\geq 0}$ is a Markov chain.
> 1. the stationary distribution of the Markov chain $(X_{t})_{t\geq 0}$ is given by $q(x) / \|q\|_{1}=:p(x)$.  

^487412

> [!proof]-
> Let $S$ be the transition function. Then, 
> 1. We have that: $$S(x'|x)=\begin{cases}\alpha(x'|x) R(x'|x)&x\neq x'\\R(x|x)+\sum_{x''\neq x}^{}(1-\alpha(x'|x))R(x''|x)&x=x'\end{cases}$$Then, $$\sum_{x'\in \mathcal{S}}^{}S(x'|x)=\sum_{x'\in \mathcal{S}}^{}R(x'|x)=1$$
> 
> 1. It suffices to show that the MC meets the detailed balanced equation w.r.t. $q$. Assume that $x\neq x'$. Then: $$q(x)S(x'|x)=q(x)\alpha(x'|x)R(x'|x)$$
> 	1. if $\alpha(x'|x)=\frac{q(x')R(x|x')}{q(x)R(x'|x)}$, then $\alpha(x|x')=1$. Hence, $$q(x)S(x'|x)=q(x)\alpha(x'|x)R(x'|x)=q(x')R(x|x')=q(x')S(x'|x)$$
> 	2. if $\alpha(x'|x)=1$, then $q(x)R(x'|x)\leq q(x')R(x|x')$ and $\alpha(x|x')=\frac{q(x)R(x'|x)}{q(x')R(x|x')}$. Hence, $$q(x')S(x|x')=q(x')\alpha(x|x')R(x|x')=q(x)R(x'|x)=q(x)S(x'|x)$$
> 	
> 	And if $x=x'$, it trivially holds. 

^658ceb

- **Remark**: If $p$ is a [[Gibbs distribution]] with $p(x)=\frac{1}{Z}\exp(-f(x))$, then:$$\alpha(x'|x)=\min \left\{  1,\frac{R(x|x')}{R(x|x')}\exp(f(x)-f(x'))  \right\}$$ ^137832

---
> [!lemma] Theorem 2 (Gibbs-Sampling)
> ```pseudo
> \begin{algorithm} \caption{Gibbs-Sampling}
> \begin{algorithmic}
> \State initialize $x\in \mathbb{R}^n$
> \For{$t=1,\dots,T$}
> \State pick a variable $i\in[n]$ uniformly at random.
> \State set $x_{-i}:=(x_{1},\dots,\widehat{x_{i}},\dots,x_{n})$
> \State update $x_{i}$ by sampling according to $p(x_{i}|x_{-i})$. 
>
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> Then, 
> 1. Gibbs-Sampling is a Metropolis-Hastings algorithm with $$R(x'|x)=\begin{cases}p(x'_{i}|x'_{-i})&x'\text{ differs from }x\text{ only in entry }i\\0&\text{otherwise}\end{cases}$$and $\alpha(x'|x)=1$. In particular, the stationary distribution of $(X_{i})_{\geq 0}$ is given by $p(x)$.

^1e7ebe

> [!proof]-
> We have that:
> 1. Let $x',x\in \mathcal{S}$ s.t. they differ only at $i$-th coordinate, then: $p(x)=p(x_{i}|x_{-i})p(x_{-i})$ and: $$\frac{q(x')R(x|x')}{q(x)R(x'|x)}=\frac{p(x')p(x_{i}|x_{-i})}{p(x)p(x'_{i}|x'_{-i})}=\frac{p(x'_{-i})}{p(x_{-i})}=1$$

^cc3fbd

---
##### Examples 
> [!h] Example 1 (Gaussian Proposals)
> Assume that $R(x'|x):=\mathcal{N}(x';x,\tau I)$ for all $x,x'\in \mathcal{S}$. Then, $$\frac{R(x|x')}{R(x'|x)}=\exp \left( -\frac{\|x'-x\|^2}{2\tau}+\frac{\|x'-x\|^2}{2\tau} \right)=1 $$Hence, 
> 1. $\alpha(x'|x)=\min\{ 1,\exp(f(x)-f(x')) \}$

^28271d
