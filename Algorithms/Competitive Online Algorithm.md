#Definition #Algorithms 

> [!definition]
> Let $c$ be a cost function. For an online algorithm $\mathcal{A}$ and $\text{OPT}$ the optimal offline algorithm, 
> 1. $\mathcal{A}$ is ***$\alpha$-competitive*** if for any input sequence $\sigma$, $$c_{\mathcal{A}}(\sigma)\leq \alpha \cdot  c_{\text{OPT}}(\sigma)$$

^9352d2
- **Related definition**: An adversary is ***oblivious*** if it knows the algorithm $\mathcal{A}$ but not the randomness used in $\mathcal{A}$.
- **Related definition**: An adversary is ***adaptive*** if at every step $t$, before it decides $\sigma_{t+1}$ it knows the randomness used in $\mathcal{A}$.
- **Related definition**: An adversary is ***fully adaptive*** if it knows all possible randomness that will be used by the algorithm $\mathcal{A}$ when running on the full input sequence $\sigma$.
---
