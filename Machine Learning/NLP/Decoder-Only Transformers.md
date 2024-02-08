#Definition #ML #NLP 

> [!definition]
> A ***decoder-only transformer*** is a [[Transformers|transformer]] where given a finite ordered set $V\cong\{ 1,\dots,|V| \}$, a distribution $P\in \Delta(V^*)$ and an i.i.d. dataset $(x^i)_{i\in[n]}\sim P$, aims to estimate $\hat{P}$ of $P$, where:$$\hat{P}(x)=\hat{P}_{\theta}(x_{1})\hat{P}_{\theta}(x_{2}|x_{1})\dots \hat{P}_{\theta}(x_{\ell_{X}}|x_{1:\ell_{X}-1})$$and $\theta$ denotes all the parameters to be learned. The goal is to learn the distribution over $x_{j}$ given $x_{1:j-1}$ as context.
---
##### Algorithm
Given a sequence $x\subseteq V^*$, the Decoder-only transformer outputs the probability distribution $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j+1}|x_{1:j})$. We have the following specifications: 
1. **Input**: $x\in V^*$
2. **Hyperparameters**: 
	- maximum sequence length $\ell_{\max}\in \mathbb{N}$, 
	- number of decoder layers $L\in \mathbb{N}$,
	- number of attention heads $H\in \mathbb{N}$,
	- embedding size $d_{e}\in \mathbb{N}$,
	- MLP parameter size $d_{\text{MLP}}\in \mathbb{N}$
3. **Parameters**: In $\theta$, we have:
	- token and positional [[Embedding|embedding matrices]] $W_{e}\in \mathbb{R}^{d_{e},|V|}, W_{p}\in\mathbb{R}^{d_{e},\ell_{\max}}$,
	- [[Attention|multi-head attention]] parameters $\mathcal W^l$ for $l\in[L]$,
	- [[Layer Norm|layer-norm]] parameters $\gamma^l_{r},\beta^l_{r}\in \mathbb{R}^{d_{e}}$ for $l\in [L_{\text{enc}}]$ and $r\in\{1,2\}$,
	- MLP parameters $W_{1}^l\in \mathbb{R}^{d_{\text{mlp}},d_{e}},b^l_{1}\in \mathbb{R}^{d_{\text{mlp}}}$,$W_{2}^l\in \mathbb{R}^{d_{e},d_{\text{mlp}}},b^l_{2}\in \mathbb{R}^{d_{e}}$ for $l\in[L_{\text{enc}}]$
	- final layer-norm parameters $\gamma,\beta\in \mathbb{R}^{d_{e}}$
	- unembedding matrix $W_{u}\in \mathbb{R}^{|V|,d_{e}}$
4. **Output**: $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j+1}|x_{1:j})$
   
Then, the algorithm is given as: 
``` pseudo
\begin{algorithm}
\Caption{D-Transformer($x|\theta$)}
\begin{algorithmic}
\State $X\gets$ \Call{Embed}{$X|W_e,W_p$}
\For{$l=1,...,L$}
\State $\hat{X}\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_1,\beta^l_1$}
\State $X\gets X\ +\ $\Call{MultiHeadAttention}{$\hat{X},\hat{X}|\mathcal{W}^l, M_{\text{uni}}$}
\State $\hat{X}\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_2,\beta^l_2$}
\State $X \gets X+W_2^l\cdot$ \Call{Gelu}{$W_1^l \hat{X}+b^l_11^\top$} $+b^l_21^\top\in \R^{d_e,|x|}$
\Endfor
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma,\beta$}
\Return $P=\text{softmax}(W_uX)\in(0,1)^{|V|,|x|}$
\end{algorithmic}
\end{algorithm}
```
where the column-wise layer-norm is done by applying layer-norm to each column and $$\textsf{gelu}(x):=x\cdot P_{{X\sim \mathcal{N}(0,1)}}(X<x)$$applied element-wise.

---
##### Training
The training of a decoder transformer is done as follows. Given a dataset $(x^i)_{i\in[n]}$, initial parameters $\theta$ with hyper-parameters $T\in \mathbb{N}$ and $\eta\in (0,\infty)$, it outputs the trained parameters $\hat{\theta}$. It can be described with the pseudocode below:

```pseudo

\begin{algorithm}
\caption{D-Training($(x^i)_{i\in[n]},\theta|T,\eta$)}
\begin{algorithmic}
\For{$t=1,...,T$}
\For{$i=1,...,n$}
\State $P(\theta)\gets $ \Call{D-Transformer}{$x^i|\theta$} 
\State $J(\theta)\gets -\sum_{j=1}^{|x^i|-1}\log P(\theta)_{x^i_{j+1},j}$
\State $\theta \gets \theta -\eta\cdot\nabla J(\theta)$
\EndFor
\ENDFor 
\Return $\hat\theta=\theta$
\end{algorithmic}
\end{algorithm}
```

---
##### Inference
With the following algorithm, we can give a decoder-transformer a prompt $x\in V^*$ as input and receive the continuation $y\in V^*$ with length $\ell_{\text{gen}}$. It also has a temperature parameter $\tau\in(0,\infty)$ where: 
1. $\tau=0$ samples the most likely continuation,
2. $\tau=1$ gives faithful sampling,
3. $\tau =\infty$ samples uniformly randomly. 

```pseudo

\begin{algorithm}
\caption{D-Inference($x,\hat{\theta}$)}
\begin{algorithmic}
\State $\ell_X\gets |x|$
\For{$t=1,...,\ell_\text{gen}$}
\State $P\gets $ \Call{D-Transformer}{$x|\hat{\theta}$} 
\State $p\gets P_{:,\ell+i-1}$
\State sample a token $y$ from $q\varpropto p^{1/\tau}$
\State $x\gets [x:y]$
\ENDFor 
\Return $x_{\ell+1,\ell+\ell_\text{gen}}$
\end{algorithmic}
\end{algorithm}
```
---