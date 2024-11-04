#Series #Algorithms 

#### Problem 1

1. Let $x'\in \arg\min_{x\in X} h_{j}(x)$ and $y'\in \arg\min_{y\in Y} h_{j}(y)$. As there are no collisions in the hash function $h_{j}$, we have that $x'$ and $y'$ are unique. 
	1. if $x'\in \left| X\cap Y \right|$ and $h_{j}(x')\equiv_{2}h_{j}(y')$, then $x'=y'$. Assume otherwise. Then, $h_{j}(x')\ne h_{j}(y')$ and $h_{j}(y')<h_{j}(x')$ and $h_{j}(x')=h_{j}(y')+2k$ for some $k\in \mathbb{N}_{\geq 1}$. 
	   $$\begin{align}\mathbb{P}(h_{j}(x')\equiv_{2}h_{j}(y')|x'\in \left| X\cap Y \right| )\end{align}$$
	2. if $x',y'\in \left| X\cap Y \right|$ and $h_{j}(x')\equiv_{2}h_{j}(y')$, then $x'=y'$. Assume otherwise. Then, by no collision, $h_{j}(x')\ne h_{j}(y')$ and $h_{j}(y')<h_{j}(x')$ and $h_{j}(y')>h_{j}(x')$ which is a contradiction.
	3. if $x'\notin \left| X\cap Y \right|$ or $y'\notin \left| X\cap Y \right|$ and $h_{j}(x')\equiv_{2}h_{j}(y')$. Wlog assume that $x'\notin $
   
	Ordering $X\cup Y$, but they have to be starting from a common member: $$\frac{\left| X\cap Y \right|}{\left| X \cup Y \right| } $$

$$\begin{align}\mathbb{P}(g_{j}(X)= g_{j}(Y))&=\mathbb{P}\left( \min_{x\in X}h_{j}(x)=\min_{y\in Y} h_{j}(y)\right) \\&=\mathbb{P}\left( h_{j}(x')=h_{j}(y') \right)\\&= \end{align}$$
Let $\sigma\in S_{[U]}$ be the permutation. Then, we have that if:
$$\text{Sim}(X,Y)+(1-\text{Sim}(X,Y))\cdot \frac{1}{2}$$
$$\begin{align}\mathbb{P}(g_{j}(X)\equiv_{2} g_{j}(Y))&=\mathbb{P}\left( \min_{x\in X}h_{j}(x)\equiv_{2}\min_{y\in Y} h_{j}(y)\right) \\&=\mathbb{P}\left( h_{j}(x')\equiv _{2}h_{j}(y') \right)\\&= \mathbb{P}(x'=y'\in|X\cap Y|\lor \end{align}$$