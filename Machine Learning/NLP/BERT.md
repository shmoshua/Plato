#Definition #ML #NLP 

> [!definition]
> ***BERT(Bidirectional Encoder Representation of Transformers)*** is an encoder-only [[Transformers|transformer]] where given a finite ordered set $V\cong\{ 1,\dots,|V| \}$, a distribution $P\in \Delta(V^*)$ and an i.i.d. dataset $(x^i)_{i\in[n]}\sim P$, aims to estimate $\hat{P}(\cdot)$ of $P(\cdot)$, especially trained by masked language modeling. 
---
##### Algorithm
Given a sequence pair $(x)\subseteq V^*$, the Encoder Transformer outputs the probability distribution $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j})$. We have the following specifications: 
1. **Input**: $z,x\in V^*$
2. **Hyperparameters**: 
	- maximum sequence length $\ell_{\max}\in \mathbb{N}$, 
	- number of encoder layers $L\in \mathbb{N}$,
	- number of attention heads $H\in \mathbb{N}$,
	- embedding size $d_{e}\in \mathbb{N}$,
	- MLP parameter size $d_{\text{MLP}}\in \mathbb{N}$,
	- final linear projection size $d_{f}\in \mathbb{N}$
1. **Parameters**: In $\theta$, we have:
	- token and positional [[Embedding|embedding matrices]] $W_{e}\in \mathbb{R}^{d_{e},|V|}, W_{p}\in\mathbb{R}^{d_{e},\ell_{\max}}$,
	- [[Attention|multi-head attention]] parameters $\mathcal W^l$ for $l\in[L]$,
	- [[Layer Norm|layer-norm]] parameters $\gamma^l_{r},\beta^l_{r}\in \mathbb{R}^{d_{e}}$ for $l\in [L]$ and $r\in\{1,2\}$,
	- MLP parameters $W_{1}^l\in \mathbb{R}^{d_{\text{mlp}},d_{e}},b^l_{1}\in \mathbb{R}^{d_{\text{mlp}}}$,$W_{2}^l\in \mathbb{R}^{d_{e},d_{\text{mlp}}},b^l_{2}\in \mathbb{R}^{d_{e}}$ for $l\in[L_{\text{enc}}]$,
	- final linear projection parameters $W_{f}\in \mathbb{R}^{d_{f},d_{e}}, b_{f}\in \mathbb{R}^{d_{f}}$,
	- final layer-norm parameters $\gamma,\beta\in \mathbb{R}^{d_{f}}$,
	- unembedding matrix $W_{u}\in \mathbb{R}^{|V|,d_{f}}$
2. **Output**: $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j})$
   
Then, the algorithm is given as: 
``` pseudo
\begin{algorithm}
\Caption{E-Transformer($x|\theta$)}
\begin{algorithmic}
\State $X\gets$ \Call{Embed}{$X|W_e,W_p$} \COMMENT{$X_{:,j}\gets (W_e)_{:,x_j}+(W_p)_{:,j}$}
\For{$l=1,...,L$}
\State $X\gets X\ +\ $\Call{MultiHeadAttention}{$X,X|\mathcal{W}^l, 1$}
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_1,\beta^l_1$}
\State $X \gets X+W_2^l\cdot$ \Call{Gelu}{$W_1^l X+b^l_11^\top$} $+b^l_21^\top\in \R^{d_e,|x|}$
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_2,\beta^l_2$}
\Endfor
\State $X \gets $ \Call{Gelu}{$W_fX+b_f1^\top$} 
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma,\beta$}
\Return $P=\text{softmax}(W_uX)\in(0,1)^{|V|,|x|}$
\end{algorithmic}
\end{algorithm}
```
where the column-wise layer-norm is done by applying layer-norm to each column and $$\textsf{gelu}(x):=x\cdot P_{{X\sim \mathcal{N}(0,1)}}(X<x)$$applied element-wise.

---
##### Training
The training of BERT is done as follows: Given a dataset $(x^i)_{i\in[n]}$, initial parameters $\theta$ with hyper-parameters $T\in \mathbb{N}$, $\eta\in (0,\infty)$ and mask probability $p_{\text{mask}}\in(0,1)$, it outputs the trained parameters $\hat{\theta}$. It can be described with the pseudocode below:

```pseudo

\begin{algorithm}
\caption{E-Training($(x^i)_{i\in[n]},\theta|T,\eta,p_\text{mask}$)}
\begin{algorithmic}
\For{$t=1,...,T$}
\For{$i=1,...,n$}
\For{$j=1,...,|x^i|$}
\State $\hat{x}^i_j\gets \texttt{mask\_token} $ with probability $p_\text{mask}$ otherwise $x^i_j$
\Endfor
\State $P(\theta)\gets $ \Call{E-Transformer}{$\hat{x}^i|\theta$} 
\State $J(\theta)\gets -\sum_{j=1}^{|x^i|}\log P(\theta)_{x^i_{j},j}\llbracket \hat x_j^i=\texttt{mask\_token}\rrbracket$
\State $\theta \gets \theta -\eta\cdot\nabla J(\theta)$
\EndFor
\ENDFor 
\Return $\hat\theta=\theta$
\end{algorithmic}
\end{algorithm}
```

---