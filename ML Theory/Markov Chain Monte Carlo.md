#Definition #PAI 

> [!definition]
> Let $p$ be a [[Distribution|probability distribution]] ***Markov Chain Monte Carlo (MCMC)*** refers to a class of algorithms for sampling from $p$, where direct sampling is computationally challenging. 

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
> \State $X_{t+1}\gets x'$ with probability $\alpha:=\min\left\{  1, \frac{q(x')R(x|x')}{q(x)R(x'|x)}  \right\}$ and otherwise $x$.
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. $(X_{t})_{t\geq 0}$ is a Markov chain.
> 1. the stationary distribution of the Markov chain $(X_{t})_{t\geq 0}$ is given by $q(x) / \|q\|_{1}$.  

> [!proof]+
> We have that:
> 1. Notice that: $$\begin{align}\sum_{x'\in \mathcal{S}}^{}\mathbb{P}(X_{t+1}=x'|X_{t}=x)=\mathbb{P}(X_{t+1}=x|X_{t}=x)+\sum_{x'\neq x}\min\left\{  1,\frac{q(x')R(x|x')}{q(x)R(x'|x)}  \right\}\end{align}$$