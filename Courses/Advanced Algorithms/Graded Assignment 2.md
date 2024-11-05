#Series #Algorithms 

#### Problem 1

1. Let $z\in \text{argmin}_{x\in X\cup Y}h_{j}(x)$. As there are no collisions in the hash function $h_{j}$, we have that $z$ is unique. Then, 
   1. if $z\in X\cap Y$. Then, $g_{j}(X)=z=g_{j}(Y)$. Further, $\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$. Hence, we have: $$\mathbb{P}(z\in X\cap Y\land g_{j}(X)\equiv_{2}g_{j}(Y))=\mathbb{P}(z\in X\cap Y)=\text{Sim}(X,Y)$$
   2. if $z\notin X\cap Y$, then the probability that $g_{j}(X)\equiv_{2}g_{j}(Y)$ is the probability that the two minima of hash values having the same parity. Then,  $$\begin{align}\mathbb{P}(g_j(X)\equiv_{2}g_{j}(Y)\land z\notin X \cap Y)&=\frac{1}{2}(1-\text{Sim}(X,Y))\end{align}$$

	Hence, $$\mathbb{P}(g_{j}(X)\equiv_{2}g_{j}(Y))=\text{Sim}(X,Y)+\frac{1}{2}\left( 1-\text{Sim}(X,Y) \right)=\frac{1+\text{Sim}(X,Y)}{2} $$

2. Let $i\in[\sqrt{ n }]$. Then, $$\mathbb{P}(f_{i}(X)=f_{i}(Y))=\prod_{j=1}^{\ell}\mathbb{P}(g_{i,j}(X)=g_{i,j}(Y))=\frac{\left( 1+\text{Sim}(X,Y) \right) ^\ell}{2^\ell}$$Hence, $$\begin{align}\mathbb{P}(\forall i:f_{i}(X)\neq f_{i}(Y))&=\prod_{i=1}^{\sqrt{ n }}\mathbb{P}(f_{i}(X)\neq f_{i}(Y))\\&=\left( 1-\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^\ell  \right)^{\sqrt{ n }}\\&\leq \left( 1-0.95^{\frac{1}{2}\log_{1 / 0,95}(n)} \right)^{\sqrt{ n }} \\&= \left( 1-(1/0.95)^{-\frac{1}{2}\log_{1 / 0,95}(n)} \right)^{\sqrt{ n }} \\&=\left( 1-\frac{1}{\sqrt{ n }} \right)^{\sqrt{ n }}\\&\leq e^{-1}\end{align} $$Therefore, with at least $1-e^{-1}$ probability, there exists $i$ with $f_{i}(X)=f_{i}(Y)$. In this case we have that $\text{Sim}(X,Z)\geq \text{Sim}(X,Y)$ as the algorithm takes the song with the maximum similarity to $X$.
3. Fix a recorded song $X$. For a song $Z\in 2^{[U]}$, let $T_{Z}$ be the indicator variable denoting if there exists $i$ s.t. $f_{i}(X)=f_{i}(Z)$. Define $T:=\sum_{Z\in S}^{}T_{Z}$. Let $Y\in S$ be the recorded song of $X$. Then,  
	1. For $Y$, $$\begin{align}\mathbb{P}(\exists i:f_{i}(X)= f_{i}(Y))&\leq \sqrt{ n }\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^{\ell}< \end{align}$$ 
	2. For $Z\neq Y$, $$\begin{align}\mathbb{P}(\forall i:f_{i}(X)\neq f_{i}(Z))&=\left( 1-\left( \frac{1+\text{Sim}(X,Z)}{2} \right) ^\ell \right) ^{\sqrt{ n }}\\&\geq \left( 1-0.9^\ell \right) ^{\sqrt{ n }}\end{align}$$ 
$$\begin{align}n-\mathbb{E}[T]&=\sum_{Z\in S}^{}\mathbb{P}(\exists i: f_{i}(X)=f_{i}(Z))\\&\geq\left( 1-\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^\ell   \right)^{\sqrt{ n }}+(n-1)(1-0.9^{\ell})^{\sqrt{ n }}\\&\geq\end{align}$$$$\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^\ell\geq \frac{1}{\sqrt{ n }}$$Hence, 
$$\begin{align}\sum_{Z\in S}^{}\mathbb{P}(\exists i: f_{i}(X)=f_{i}(Z))&\geq\left( 1-\left( \frac{1+\text{Sim}(X,Y)}{2} \right)^\ell   \right)^{\sqrt{ n }}+(n-1)(1-0.9^{\ell})^{\sqrt{ n }}\\&\geq\end{align}$$


---
