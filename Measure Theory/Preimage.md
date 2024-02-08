#Definition #MeasureTheory 

> [!definition]
> For non-empty sets $X,Y$, a map $\varphi:X \to Y$ and $A \in \mathcal{{P}}(Y)$, the ***preimage*** of $A$ is $$\varphi^{-1}[A]:=\{ x\in X:\varphi(x)\in A \}$$
---
##### Properties
> [!lemma] Proposition 1
> For a function $\varphi:X \to Y$, it holds that: 
> 1. $\varphi ^{-1}[A^c]=(\varphi^{-1}[A])^c$ for all $A \in\mathcal P(Y)$.
> 2. If $A,B \subseteq Y$, $$\varphi^{-1}[A\cap B]=\varphi ^{-1}[A]\cap \varphi^{-1}[B]$$
> 3. If $\{ A_{k} \}_{k}\subseteq \mathcal P(Y)$,$$\varphi^{-1}\left[ \bigcup_{k=1}^{\infty}A_{k} \right] =\bigcup_{k=1}^{\infty}\varphi^{-1}[A_{k}]$$
> 4. If $(Y,\mathcal{F},\mu)$ is a [[Measure Space|measure space]], then: $$\varphi^{-1}[\mathcal{F}]:=\{ \varphi^{-1}[A]:A\in \mathcal{F} \}$$is a [[Sigma Algebra|$\sigma$-algebra]] in $X$.

> [!proof]-
> We have: 
> 1. $\varphi ^{-1}[A^c]=\{ x\in X:\varphi(x)\in A^c \}=\{ x\in X:\varphi(x)\in A\}^c=\varphi ^{-1}[A]^c$
> 2. $\varphi ^{-1}[A\cap B]=\{ x\in X:\varphi(x)\in A\cap B \}=\varphi ^{-1}[A]\cap\varphi ^{-1}[B]$
> 3. We have: $$\begin{align}\varphi ^{-1}\left[ \bigcup_{k=1}^{\infty}A_{k} \right] &=\left\{  x\in X :\varphi(x)\in \bigcup_{k=1}^{\infty}A_{k} \right\}\\&=\bigcup_{k=1}^{\infty}\{ x\in X:\varphi(x)\in A_{k} \}\\&=\bigcup_{k=1}^{\infty}\varphi ^{-1}[A_{k}]\end{align}$$
> 4. We have that: 
> 	- $X\in \varphi ^{-1}[\mathcal{F}]$ as $\varphi ^{-1}[Y]=X$.
> 	- For $\varphi^{-1}[A],\varphi^{-1}[B]\in \varphi ^{-1}[\mathcal{F}]$, there exist $\varphi ^{-1}[A]\cup\varphi ^{-1}[B]=\varphi ^{-1}[A\cup B]\in \varphi ^{-1}[\mathcal{F}]$
> 	- For $\varphi^{-1}[A],\varphi^{-1}[B]\in \varphi ^{-1}[\mathcal{F}]$, there exist $\varphi ^{-1}[A]\backslash \varphi ^{-1}[B]=\varphi ^{-1}[A\backslash B]\in \varphi ^{-1}[\mathcal{F}]$
> 	- For $(\varphi ^{-1}[A_{k}])_{k}$, $$\bigcup_{k=1}^{\infty}\varphi ^{-1}[A_{k}]=\varphi ^{-1}\left[ \bigcup_{k=1}^{\infty}A_{k} \right] \in \varphi ^{-1}(\mathcal{F})$$
---