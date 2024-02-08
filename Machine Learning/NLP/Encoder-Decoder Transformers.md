#Definition #ML #NLP 

> [!definition]
> An ***encoder-decoder transformer*** is a [[Transformers|transformer]] where given a finite ordered set $V\cong\{ 1,\dots,|V| \}$, a distribution $P\in \Delta(V^*\times V^*)$ and an i.i.d. dataset $(z^i,x^i)_{i\in[n]}\sim P$, aims to estimate $\hat{P}(\cdot|\cdot)$ of $P(\cdot|\cdot)$, where:$$\hat{P}(x|z)=\hat{P}_{\theta}(x_{1}|z)\hat{P}_{\theta}(x_{2}|x_{1},z)\dots \hat{P}_{\theta}(x_{\ell_{X}}|x_{1:\ell_{X}-1},z)$$and $\theta$ denotes all the parameters to be learned. 
---
##### Algorithm
Given a sequence pair $(z,x)\subseteq V^*$, the Encoder-Decoder transformer outputs the probability distribution $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j+1}|x_{1:j},z)$. We have the following specifications: 
1. **Input**: $z,x\in V^*$
2. **Hyperparameters**: 
	- maximum sequence length $\ell_{\max}\in \mathbb{N}$, 
	- number of encoder layers $L_{\text{enc}}\in \mathbb{N}$,
	- number of decoder layers $L_{\text{dec}}\in \mathbb{N}$,
	- number of attention heads $H\in \mathbb{N}$,
	- embedding size $d_{e}\in \mathbb{N}$,
	- MLP parameter size $d_{\text{MLP}}\in \mathbb{N}$
3. **Parameters**: In $\theta$, we have:
	- token and positional [[Embedding|embedding matrices]] $W_{e}\in \mathbb{R}^{d_{e},|V|}, W_{p}\in\mathbb{R}^{d_{e},\ell_{\max}}$,
	- [[Attention|multi-head attention]] parameters $\mathcal W_{\text{enc}}^l$ for $l\in[L_{\text{enc}}]$,
	- [[Layer Norm|layer-norm]] parameters $\gamma^l_{r},\beta^l_{r}\in \mathbb{R}^{d_{e}}$ for $l\in [L_{\text{enc}}]$ and $r\in\{1,2\}$,
	- MLP parameters $W_{1}^l\in \mathbb{R}^{d_{\text{mlp}},d_{e}},b^l_{1}\in \mathbb{R}^{d_{\text{mlp}}}$,$W_{2}^l\in \mathbb{R}^{d_{e},d_{\text{mlp}}},b^l_{2}\in \mathbb{R}^{d_{e}}$ for $l\in[L_{\text{enc}}]$
	- multi-head attention parameters $\mathcal{W^l_{\text{dec}}}$ for $l\in[L_{\text{dec}}]$
	- multi-head cross-attention parameters $\mathcal{W}^l_{\text{cross}}$ for $l\in [L_{\text{dec}}]$
	- layer-norm parameters $\gamma^l_{r},\beta^l_{r}\in \mathbb{R}^{d_{e}}$ for $l\in [L_{\text{dec}}]$ and $r\in\{ 3,4,5 \}$
	- MLP parameters $W_{3}^l\in \mathbb{R}^{d_{\text{mlp}},d_{e}},b^l_{3}\in \mathbb{R}^{d_{\text{mlp}}}$,$W_{4}^l\in \mathbb{R}^{d_{e},d_{\text{mlp}}},b^l_{4}\in \mathbb{R}^{d_{e}}$ for $l\in[L_{\text{dec}}]$
	- unembedding matrix $W_{u}\in \mathbb{R}^{|V|,d_{e}}$
4. **Output**: $P\in (0,1)^{|V|,|x|}$ where $P_{ij}=\hat{P}_{\theta}(x_{j+1}|x_{1:j},z)$
   
Then, the algorithm is given as: 
``` pseudo
\begin{algorithm}
\Caption{ED-Transformer($z,x|\theta$)}
\begin{algorithmic}
\State \Comment{Encoding the context sequence $z$}
\State $Z\gets $ \Call{Embed}{$z|W_e,W_p$}$\in \R^{d_e,|z|}$  \COMMENT{$Z_{:,j}\gets (W_e)_{:,z_j}+(W_p)_{:,j}$}
\For{$l=1,...,L_{\text{enc}}$}
\State $Z\gets Z\ +\ $\Call{MultiHeadAttention}{$Z,Z|\mathcal{W}^l_{\text{enc}}, 1$}
\State $Z\gets $ \Call{ColwiseLayerNorm}{$Z|\gamma^l_1,\beta^l_1$}
\State $Z \gets Z+W_2^l\max(0,W_1^l Z+b^l_11^\top)+b^l_21^\top\in \R^{d_e,|z|}$
\State $Z\gets $ \Call{ColwiseLayerNorm}{$Z|\gamma^l_2,\beta^l_2$}
\Endfor
\State
\State \Comment{Decoding the primary sequence $x$}
\State $X\gets$ \Call{Embed}{$X|W_e,W_p$}
\For{$l=1,...,L_{\text{dec}}$}
\State $X\gets X\ +\ $\Call{MultiHeadAttention}{$X,X|\mathcal{W}^l_{\text{dec}}, M_{\text{uni}}$}
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_3,\beta^l_3$}
\State $X\gets X\ +\ $\Call{MultiHeadAttention}{$X,Z|\mathcal{W}^l_{\text{cross}}, 1$}
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_4,\beta^l_4$}
\State $X \gets X+W_4^l\max(0,W_3^l X+b^l_31^\top)+b^l_41^\top\in \R^{d_e,|x|}$
\State $X\gets $ \Call{ColwiseLayerNorm}{$X|\gamma^l_5,\beta^l_5$}
\Endfor
\State \Return $P=\text{softmax}(W_uX)\in(0,1)^{|V|,|x|}$
\end{algorithmic}
\end{algorithm}
```
where the column-wise layer-norm is done by applying layer-norm to each column.

---
##### Training
The training of an encoder-decoder transformer is an algorithm $\text{ED-Training}$. Given a dataset $(z^i,x^i)_{i\in[n]}$, initial parameters $\theta$ with hyper-parameters $T\in \mathbb{N}$ and $\eta\in (0,\infty)$, it outputs the trained parameters $\hat{\theta}$. It can be described with the pseudocode below:

```pseudo

\begin{algorithm}
\caption{ED-Training($(z^i,x^i)_{i\in[n]},\theta|T,\eta$)}
\begin{algorithmic}
\For{$t=1,...,T$}
\For{$i=1,...,n$}
\State$\ell_X\gets |x^i|$
\State $P(\theta)\gets $ \Call{ED-Transformer}{$z^i,x^i|\theta$} 
\State $J(\theta)\gets -\sum_{j=1}^{\ell_X-1}\log P(\theta)_{x^i_{j+1},j}$
\State $\theta \gets \theta -\eta\cdot\nabla J(\theta)$
\EndFor
\ENDFor 
\Return $\hat\theta=\theta$
\end{algorithmic}
\end{algorithm}
```

---
##### Inference
With the following algorithm, we can give an encoder-decoder transformer a prompt $z\in V^*$ as input and receive the output sequence $x\in V^*$. It also has a temperature parameter $\tau\in(0,\infty)$ where: 
1. $\tau=0$ samples the most likely continuation,
2. $\tau=1$ gives faithful sampling,
3. $\tau =\infty$ samples uniformly randomly. 

```pseudo

\begin{algorithm}
\caption{ED-Inference($z,\hat{\theta}$)}
\begin{algorithmic}
\State $x\gets [\texttt{bos\_token}]$\Comment{beginning-of-sequence token}
\State $\ell_X\gets |x|$
\State $y\gets 0$
\While{$y\ne\texttt{eos\_token}$}
\State $P\gets $ \Call{ED-Transformer}{$z,x|\hat{\theta}$} 
\State $p\gets P_{:,|x|}$
\State sample a token $y$ from $q\varpropto p^{1/\tau}$
\State $x\gets [x:y]$
\ENDwhile 
\Return $x$
\end{algorithmic}
\end{algorithm}
```
---

$$\begin{align}&A\\&\quad\quad\quad\quad B\\&=C\\&=D\end{align}$$