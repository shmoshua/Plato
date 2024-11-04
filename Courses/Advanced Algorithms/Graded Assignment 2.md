#Series #Algorithms 

#### Problem 1

1. Let $z\in \text{argmin}_{x\in X\cup Y}h_{j}(x)$. As there are no collisions in the hash function $h_{j}$, we have that $z$ is unique. Then, 
   1. if $z\in X\cap Y$. Then, $g_{j}(X)=z=g_{j}(Y)$. Further, $\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$. Hence, we have: $$\mathbb{P}(z\in X\cap Y\land g_{j}(X)\equiv_{2}g_{j}(Y))=\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$$
   2. if $z\notin X\cap Y$, then the probability that $g_{j}(X)\equiv_{2}g_{j}(Y)$ is the probability that the two minima of hash values having the same parity. Then,  $$\begin{align}\mathbb{P}(g_j(X)\equiv_{2}g_{j}(Y)\land z\notin X \cap Y)&=\frac{1}{2}(1-\text{Sim}(X,Y))\end{align}$$

	Hence, $$\mathbb{P}(g_{j}(X)\equiv_{2}g_{j}(Y))=\text{Sim}(X,Y)+\frac{1}{2}\left( 1-\text{Sim}(X,Y) \right)=\frac{1+\text{Sim}(X,Y)}{2} $$

2. Let $i\in[\sqrt{ n }]$. Then, $$\mathbb{P}(f_{i}(X)=f_{i}(Y))=\prod_{j=1}^{\ell}$$


	