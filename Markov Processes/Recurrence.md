#Definition #Markov 

> [!definition]
> Let $(X_{n})_{n\geq0}$ be a [[Markov chain]] on states $\mathcal{S}$. Let $j\in \mathcal{S}$ and define $\{ \rho_{j}^{(t)} \}_{t\geq 0}$ given as:
> 1. $\rho_{j}^{(0)}=0$,
> 2. $\rho_{j}^{(t)}=\infty$ if $\rho_{j}^{(t-1)}=\infty$ and $\rho_{j}^{(t)}=\text{inf}\{ n>\rho_{j}^{(t-1)}:X_{n}=j \}$ otherwise
> 
> Then, $j$ is ***recurrent*** if $\mathbb{P}(\rho_{j}^{(1)}<\infty|X_{0}=j)=1$ and ***transient*** otherwise.