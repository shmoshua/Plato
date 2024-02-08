#Definition #NLP #ML 

When we refer to a token, we normally refer to its [[Embedding|token embedding]] $x\in \mathbb{R}^{d_{x}}$.

---
##### Single-query Attention

For a primary token $x\in \mathbb{R}^{d_{x}}$ and a context tokens $\{ z_{t} \}_{t=1}^T\subseteq \mathbb{R}^{d_{z}}$, the ***single-query attention*** of $x$ w.r.t. $\{ z_{t} \}_{t}$ is computed as: 
$$\textsf{Attention}(x,z_{1:T}|W_{QKV})=\sum_{t=1}^{T} \frac{\exp(q^\top k_{t} / \sqrt{ d_{\text{attn}} })}{\sum_{u=1}^{T}\exp(q^\top k_{u} / \sqrt{ d_{\text{attn}} })}v_{t}$$
for 
1. $q:=W_{Q}x+b_{Q}\in \mathbb{R}^{d_{\text{attn}}}$
2. $k_{t}:=W_{K}z_{t}+b_{K}\in \mathbb{R}^{d_{\text{attn}}}$ for all $t\in [T]$
3. $v_{t}:=W_{V}z_{t}+b_{V}\in \mathbb{R}^{d_{\text{out}}}$ for all $t\in [T]$
   
where $W_{Q},W_{K}\in \mathbb{R}^{d_{\text{attn}},d_{\text{in}}}$, $W_{V}\in \mathbb{R}^{d_{\text{out}},d_{\text{in}}}$ and $b_{Q},b_{K}\in \mathbb{R}^{d_{\text{attn}}}$ and $b_{V}\in \mathbb{R}^{d_{\text{out}}}$ are learnable parameters.

---
##### Matrix-Representation of Attention with Mask
This is a generalization of the single-query attention. For primary sequence $X\in \mathbb{R}^{d_{X},\ell_{X}}$ of length $\ell_{X}$ and context sequence $Z \in \mathbb{R}^{d_{Z},\ell_{Z}}$ of length $\ell_{Z}$, the ***attention*** of $X$ w.r.t $Z$ with mask $M\in \{ 0,1 \}^{\ell_{Z},\ell_{X}}$ is computed as:
 
$$\textsf{Attention}(X,Z| W_{QKV},M)=V\cdot  \textsf{softmax}\left( \frac{\textsf{mask}_{M}(K^\top Q)}{\sqrt{ d_{\text{attn}} }} \right) \in \mathbb{R}^{d_{\text{out}},\ell_{X}}$$
for
1. $Q:=W_{Q}X+b_{Q}1^\top\in \mathbb{R}^{d_{\text{attn}},\ell_{X}}$
2. $K:=W_{K}Z+b_{K}1^\top\in \mathbb{R}^{d_{\text{attn}}, \ell_{Z}}$
3. $V:=W_{V}Z+b_{V}1^\top\in \mathbb{R}^{d_\text{out},\ell_{Z}}$
   
where $W_{Q},W_{K}\in \mathbb{R}^{d_{\text{attn}},d_{\text{in}}}$, $W_{V}\in \mathbb{R}^{d_{\text{out}},d_{\text{in}}}$ and $b_{Q},b_{K}\in \mathbb{R}^{d_{\text{attn}}}$ and $b_{V}\in \mathbb{R}^{d_{\text{out}}}$ are learnable parameters. Further, $\textsf{softmax}(A)$ for a matrix $A\in \mathbb{R}^{m,n}$ is the column-wise [[softmax]] function, i.e.
$$\textsf{softmax}(A)_{ij}= \frac{\exp(A_{ij})}{\sum_{k=1}^{m}\text{exp}(A_{kj})}$$
and 
$$\textsf{mask}_{M}(A)_{ij}=\begin{cases}A_{ij}&M_{ij}=1\\-\infty & M_{ij}=0\end{cases}$$
- **Bidirectional/Unmasked Self-attention**: An attention is a ***self-attention*** if $Z=X$. If $Z\neq X$, we have a ***cross-attention***. Further, here we have no mask, i.e. $M=1$. Therefore, the bidirectional self-attention is denoted as: $$\textsf{Attention}(X,X|W_{QKV},1)=V\cdot \textsf{softmax}\left( \frac{\textsf{mask}_{M}(K^\top Q)}{\sqrt{ d_{\text{attn}} }} \right) =V\cdot \textsf{softmax}\left( \frac{K^\top Q}{\sqrt{ d_{\text{attn}} }} \right) \in \mathbb{R}^{d_{\text{out}},\ell_{X}}$$
- **Unidirectional/Masked Self-attention**: Here, for a primary token, we only want to consider all preceding tokens as context. Therefore, we have the mask matrix $M\in\{0,1\}^{\ell_{X},\ell_{X}}$ defined as the lower-triangular matrix of $1$, i.e: $$M_{ij}=1\iff i\leq j$$
---
##### Multi-head Attention
An ***attention head*** denotes the set of learnable parameters $W_{QKV}$ in the attention. If we have multiple attention heads in parallel and combine their outputs, we have a ***multi-head attention***. 

For primary sequence $X\in \mathbb{R}^{d_{X},\ell_{X}}$ of length $\ell_{X}$ and context sequence $Z \in \mathbb{R}^{d_{Z},\ell_{Z}}$ of length $\ell_{Z}$, the ***multi-head attention*** of $X$ w.r.t $Z$ with mask $M\in \{ 0,1 \}^{\ell_{Z},\ell_{X}}$ is computed as:
$$\textsf{MH-Attention}(X,Z|\{W_{QKZ}^h,W_{o}^h\}_{h=1}^H, ,b_{o},M)=\sum_{h=1}^{H}W_{o}^h\textsf{Attention}(X,Z|W^h_{QKZ},M)+b_{o}1^\top\in\mathbb{R}^{d_{\text{out}},\ell_{X}}$$
where $W_{o}^h\in \mathbb{R}^{d_{\text{out}}, d_{\text{mid}}}$ is another learnable parameter. Alternatively, we can put the $W_{o}^h$ into one matrix and have $W_{o}:=[W_{o}^1|\dots|W_{o}^H]\in\mathbb{R}^{d_{\text{out}},Hd_{\text{mid}}}$ and $Y:=[Y^1|\dots|Y^H]^\top\in \mathbb{R}^{Hd_{\text{mid}},\ell_{X}}$ where $Y_{i}^\top:=\textsf{Attention}(X,Z|W^h_{QKZ},M)$. Then, 
$$\textsf{MH-Attention}(X,Z|\{W_{QKZ}^h\}_{h=1}^H, ,W_{o},b_{o},M)=W_{o}Y+b_{o}1^\top\in\mathbb{R}^{d_{\text{out}},\ell_{X}}$$
---
