#Definition #MachineLearning

> [!definition]
> An ***autoencoder*** is a pair of maps $(F,G)$ where $F:\mathbb{R}^n\to \mathbb{R}^m$ and $G:\mathbb{R}^m\to \mathbb{R}^n$ s.t. $$(F,G)\in \underset{ F,G }{ \text{argmin}\ } \mathbb{E}[\ell(x,GFx)]$$where $\ell:\mathbb{R}^n\times \mathbb{R}^n \to \mathbb{R}$ is the ***loss function***. 
- **Related definition**: A ***linear/affine autoencoder*** is an autoencoder where $F,G$ are linear/affine. 

---
##### Properties
###### Linear Autoencoders
> [!lemma] Proposition 1
> For quadratic loss function $\ell(x,\widehat{x}):=\frac{1}{2}\left\| x-\widehat{x} \right\|^{2}_{2}$, 
> 1. if $\mathbb{E}[x]=0$, then $$\min_{F,G \text{ affine}}\mathbb{E}[\ell(x,GFx)]=\min_{F,G \text{ linear}}\mathbb{E}[\ell(x,GFx)]$$
> 2. for a linear autoencoder, $F,G$ are not unique. 
> 3. we have that: $$\min_{F,G \text{ linear}}\mathbb{E}[\ell(x,GFx)]=\min_{P\in\mathbb{R}^{n\times n}, \text{rnk}(P)\leq m}\mathbb{E}[\ell(x,Px)]$$

> [!proof]+
> We have that:
> 1. Let $F:x\mapsto Ax+a$ and $G:y\mapsto By+b$. Then, $$\begin{aligned}\mathbb{E}[\ell(x,GFx)]=\end{aligned}$$