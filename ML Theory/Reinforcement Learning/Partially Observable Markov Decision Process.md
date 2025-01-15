#Definition #RL 

> [!definition]
> A ***partially observable Markov decision process (POMDP)*** is a tuple $(\mathcal{X},\mathcal{A},P,r,\mu,\mathcal{Y},o)$ where:
> 1. $(\mathcal{X},\mathcal{A},P,r,\mu)$ is a [[Markov Decision Process]].
> 2. $\mathcal{Y}$ is a set of ***observations***
> 3. the ***observation probabilities*** $o:\mathcal{X}\to M^1(\mathcal{Y})$

^a48413

---
##### Properties
> [!lemma]  Theorem 1
> Let $M$ be a POMDP. Then, consider:
> 1. $\mathcal{B}:=M^1(\mathcal{X})$,
> 2. $\tau:\mathcal{B}\times \mathcal{A}\to M^1(\mathcal{B})$ given by: $$\tau(b'|b,a):=\sum_{y\in \mathcal{Y}}^{}\delta_{b',b,a,y}\sum_{x\in \mathcal{X}}^{}b(x)\sum_{x'}^{}P(x'|x,a)\cdot o(y|x')$$where $\delta_{b',b',a,y}=1$ if and only if $b'(x)=\frac{1}{Z}o(y|x)\sum_{x'}P(x|x',a)b(x')$ with $Z:=\sum_{x}^{}o(y|x)\sum_{x'}P(x|x',a)b(x')$, and otherwise $0$.
> 3. $\rho:\mathcal{B}\times \mathcal{A}\to \mathbb{R}$ with: $$\rho(b,a)=\sum_{x}^{}b(x)r(x,a)$$
> 
> Then, $(\mathcal{B},\mathcal{A},\tau,\rho)$ forms a MDP whose optimum policies coincide with the optimum policies for $M$. This is called the ***belief-state MDP***.

^1bdfe5

- **Remark**: The drawback is that the belief-state MDP is not finite and even for the smallest $X$ has an infinite state space. A common approach is to discretize the belief space by sampling or by applying a dimensionality reduction, as not all belief states are reached. 
---
