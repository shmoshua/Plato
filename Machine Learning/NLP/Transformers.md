#Definition 

> [!definition]
> A ***transformer*** is a neural network architecture that is based on [[Attention|self-attention]] mechanism, [[Embedding|positional embedding]] and the encoder-decoder structure. 

---
##### Types of Transformers

- **D-Transformers**: Given a [[Vocabulary|vocabulary]] $V$, let $P\in \Delta (V^{*})$ and $(x^i)_{i\in[n]}\overset{\text{i.i.d.}}\sim P$. A D-Transformer aims to estimate $\hat{P}$ of $P$, where: $$\hat{P}(x)=\hat{P}_{\theta}(x_{1})\hat{P}_{\theta}(x_{2}|x_{1})\dots \hat{P}_{\theta}(x_{\ell}|x_{1:\ell})$$and $\theta$ denotes all the parameters to be learned. The goal is to learn the distribution over $x_{t}$ given $x_{1:t-1}$ as context.
- **ED-Transformers**: Given a vocabulary $V$ and $P\in \Delta(V^*\times V^*)$, let $(x^i,y^i)_{i\in[n]}$ be the dataset. A ED-Transformer aims to estimate $\hat{P}(\cdot|\cdot)$ of $P(\cdot|\cdot)$, where:$$\hat{P}(y|x)=\hat{P}_{\theta}(y_{1}|x)\hat{P}_{\theta}(y_{2}|y_{1},x)\dots \hat{P}_{\theta}(y_{\ell}|y_{1:\ell},x)$$and $\theta$ denotes all the parameters to be learned. 
- **E-Transformers**: Given a vocabulary $V$ and a set of $C$ classes $\mathcal{C}:=[C]$, $P\in \Delta(V^*\times \mathcal{C})$, let $(x^i,c^i)_{i\in[n]}$ be the dataset. An E-Transformer aims to estimate $\hat{P}(c|x)$ of $P(c|x)$.
---
##### Embedding
In the original transformer, the length-$d_{e}$ embedding $\textsf{embed}:V^*\times [\ell_{\max}]\to \mathbb{R}^{d_{e}}$ is computed as: $$\textsf{embed}(x,\ell)=W^{e}_{:,x_{
\ell}}+W^p_{:,\ell}$$
where $W^e$ is the [[Embedding|token embedding matrix]] and $W^p$ is the [[Positional Embedding|positional embedding matrix]] defined as:
$$W^{p}_{ij}=\begin{cases}\sin\left( j/\ell_{\max}^{(i+1)/d_{e}} \right)&i \text{ odd}\\\cos\left( j/\ell_{\max}^{i/d_{e}} \right)&i \text{ even}\end{cases}$$
---


