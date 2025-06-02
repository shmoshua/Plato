#Definition #ML 

> [!lemma] Proposition 1
> Consider the following loss function: $$R(P):=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]$$where $P$ is a self-adjoint projection. Then, if $\mathbb{E}[x]=0$, 
> 1. $R(P)=\frac{1}{2}(\text{Var}(x)-\text{Var}(Px))$

> [!proof]+
> We have that:
> 1. Consider: $$\begin{aligned}R(P)=\frac{1}{2}\mathbb{E}[\left\| x-Px \right\| ^{2}_{2}]=\frac{1}{2}\mathbb{E}[\|x\|^{2}_{2}]+\frac{1}{2}\mathbb{E}[\left\| Px \right\| ^{2}_{2}]-\underbrace{ \mathbb{E}\left[ \braket{ x , P^{2}x }  \right]  }_{ =\mathbb{E}[\braket{ Px , Px } ]=\mathbb{E}[\left\| Px \right\| ^{2}_{2}] }=\frac{1}{2}(\mathbb{E}[\|x\|^{2}_{2}-\left\| Px \right\| ^{2}_{2}])\end{aligned}$$The rest follows from the fact that $\mathbb{E}[x]=0$.