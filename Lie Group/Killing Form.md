#Definition #LieGroups 

> [!definition]
> For a $\mathbb{K}$-[[Lie algebra]] $\mathfrak{g}$, the ***Killing form*** of $\mathfrak{g}$ is the symmetric bilinear form: $$K_{\mathfrak{g}}:\mathfrak{g\times g}\to \mathbb{K},\quad (x,y)\mapsto \text{tr}(\text{ad}(x)\text{ad}(y))$$
---
##### Properties
> [!lemma] Proposition 1
> For all $x,y,z\in\mathfrak{g}$, $$K_{\mathfrak{g}}(\text{ad}(z)x,y)+K_{\mathfrak{g}}(x,\text{ad}(z)y)=0$$

> [!proof]-
> We have that: $$\begin{align}K_{\mathfrak{g}}(\text{ad}(z)x,y)+K_{\mathfrak{g}}(x,\text{ad}(z)y)&=\text{tr}(\text{ad}([z,x])\text{ad}(y))+\text{tr}(\text{ad}(x)\text{ad}([z,y]))\\&=\text{tr}([\text{ad}(z),\text{ad}(x)]\text{ad}(y))+\text{tr}(\text{ad}(x)[\text{ad}(z),\text{ad}(y)])\\&=\text{tr}(\text{ad}(z)\text{ad}(x)\text{ad}(y))-\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))\\&=\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))-\text{tr}(\text{ad}(x)\text{ad}(y)\text{ad}(z))\\&=0\end{align}$$using the cyclic property of the trace.
---
> [!lemma] Lemma 2
> For a connected [[Lie group]] $G$ with Lie algebra $\mathfrak{g}$, $$K_{\mathfrak{g}}(\text{Ad}(g)x,\text{Ad}(g)y)=K_{\mathfrak{g}}(x,y),\quad \forall g\in G, x,y\in \mathfrak{g}$$

> [!proof]+
> Let $z\in \mathfrak{g}$. Then, let: $$\phi(t):=K_{\mathfrak{g}}(\text{Ad}(\exp(tz))x,\text{Ad}(\exp(tz))y)$$Computing the derivative, we have: $$\phi'(0)=$$
> 
> $$\begin{align}K_{\mathfrak{g}}(\text{Ad}(\exp(tz))x,\text{Ad}(\exp(tz))y)&=\text{tr}(\text{ad}(\text{Ad}(\exp(tz))x)\text{ad}(\text{Ad}(\exp(tz))y))\end{align}$$
