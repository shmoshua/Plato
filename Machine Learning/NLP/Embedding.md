#Definition #ML #NLP 

> [!definition]
> For a finite ordered set $X$, an ***embedding*** for $x_{i}\in X$ is given as: $$W_{:,i}\in \mathbb{R}^{d_{X}}$$
> where $W\in\mathbb{R}^{d_{X},|X|}$ is the ***embedding matrix*** and $d_{X}$ is the desired dimension of the token embedding.
> 
> For an embedding $\hat{x}\in \mathbb{R}^{d_{X}}$, ***unembedding*** $\hat{x}$ denotes retrieving $p_{x}\in \Delta(X)$ by: $$p_{x}=\textsf{softmax}(U \hat{x})$$
> where $U\in \mathbb{R}^{|X|,d_{X}}$ is the ***unembedding matrix***. Sometimes, we have that $U=W^\top$.
---
##### Examples
- **Token Embedding**: We have a [[Vocabulary|vocabulary]] $X=V$, a ***token embedding*** for $v\in V$ where $v$ is the token ID.
- **Positional Embedding**: We have $X=[\ell_{\max}]$ where $\ell_{\max}$ denotes the fixed maximum length of a sequence.
---