#Definition #Algorithms 

> [!definition]
> A ***uniform, $k$-wise independent family of hash functions***  is a distribution $\mathcal{H}_{k,U,m}$ on $[m]^U$ s.t. for $h\sim \mathcal{H}_{k,U,m}$,
> 1. for all $x\in \{ 0,\dots,U \},i\in\{ 0,\dots,m \}$, $\mathbb{P}(h(x)=i)=\frac{1}{m}$
> 2. for any $x_{1},\dots,x_{n}\in \{ 0,\dots,U \}$, $h(x_{1}),\dots,h(x_{n}):\Omega\to[m]$ are [[Independence|$k$-wise independent]] [[Random Variable|random variables]].
