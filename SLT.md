
#### Exercise 2.3
We have that: $\Phi(a,b) = ab$.$$D_{(1,0)}\Phi(a,b)=v[b,a] = b$$
Similarly, $D_{(0,1)}\Phi(a,b) = a$. So for $w\in\mathbb{R} \times \{ 0 \}$ $\Phi$ is degenrate for direction $(1,0)$ and for direction $(0,1)$, we have $\{ 0 \}\times \mathbb{R}$.

---


#### Exercise 2.6
1. For $\alpha> 0$ and $z\in \mathbb{R}$, $$\text{relu}(\alpha z) = \max\{0,\alpha z\} = \alpha \max\{0,z\} = \alpha \cdot \text{relu}(z)$$
2. For any $t\in \mathbb{R}$, $$f_{e^ta,e^{-t}b}(x)=e^{-t}b\cdot  \text{relu}(e^{t}a x)=b\cdot \text{relu}(ax)=f_{a,b}(x)$$Further for $t = 0$, $\Phi_{0}=\text{id}$. Lastly, for any $(a,b)$, $t\mapsto (e^ta,e^{-t}b)$ is differentiable. 
3. From above we have that $\gamma(t):=(e^t a,e^{-t}b)$. Then, the degenerate direction is: $$\gamma'(0) = (a,-b)$$
4. At the origin we have that $T_{t}(0,0) = (0,0)$ for all $t$. Hence it is trivial.

---
#### Exercise 2.7
1. We have that: 
	$$(\Phi \circ  T_{R}(W))(x) = W^\top R^\top R W x = W^\top W x = \Phi(W)(x)$$
2. $R(\theta)$ is orthogonal for all $\theta$, hence by 1, it is a symmetry. Further, for $\theta =0$, $$R(0) = \begin{bmatrix}1 & 0\\0 &1\end{bmatrix}$$Lastly, we have that for a given $W$, $T_{R(\theta)}(W)$ is differentiable in $\theta$.
3. Let $\gamma(t):= T_{R(t)}(W) = \begin{bmatrix} \cos t&-\sin t\\ \sin t&\cos t\end{bmatrix}W=\begin{bmatrix}W_{1}\cos t-W_{2}\sin t\\W_{1}\sin t - W_{2}\cos t\end{bmatrix}$. Then, $$\gamma'(0) =\begin{bmatrix}-W_{2}\\W_{1}\end{bmatrix}=\begin{bmatrix}0 &-1\\1&0\end{bmatrix}W$$
---
#### Exercise 2.8

1. TODO
2. We have that: $$\Phi(T_{t}^{(a)}(a,b))=\Phi(a+t,b)=(a+t)b \overset{ ! }{ = } ab$$, i.e. $b = 0$. For the other case we have $a = 0$ by symmetry. 
---
#### Exercise 2.9
We have that:
1. We have that: $$D_{(\delta A,\delta B)}\Phi(A,B)=\lim_{ \varepsilon \to 0 } \frac{\Phi(A+\varepsilon\delta A,B+\varepsilon\delta B)-\Phi(A,B)}{\varepsilon}=B\delta A+\delta B A$$
2. For $(A,B) = 0$, $B\delta A+\delta BA = 0$ for any $(\delta A,\delta B)$. $\mathbb{R}^{2m^2}$.
3. Let $B\delta A+\delta BA = 0$ where $A,B$ are invertible. This is equivalent to $$-B\delta A A ^{-1}=\delta B $$. Then, the dimension is $m^{2}$.
---
#### Exercise 2.10
1. We have that: $$D_{\delta b_{i}}\Phi(w)=\lim_{ \epsilon \to 0 } \frac{a_{i}(\sigma((b_{i}+\varepsilon \delta b_{i})x+c_{i})-\sigma(b_{i}x + c_{i}))}{\varepsilon}=0$$
2. We have that: $$D_{(1,-\sigma(c_{i}))}\Phi(w)=\lim_{ \varepsilon \to 0 } \frac{-\varepsilon \sigma(c_{i})+\varepsilon \sigma(c_{i})}{\varepsilon}=0$$
3. We have that: $$D_{(1,-1)}\Phi(w)= \lim_{ \varepsilon \to 0 } \frac{\varepsilon\sigma(b_{i}x+c_{i})-\varepsilon\sigma(b_{j}x+c_{j})}{\varepsilon}=0$$
---
#### Exercise 2.13
Let $\Phi$ be degenerate at $w$ in direction $v$. Then, $$D_{v}L(w)=\frac{v}{\|v\|}\cdot  \nabla L(w)=\frac{v}{\|v\|}\cdot  \mathbb{E}_{{(x,y)\sim q}}\nabla L(w)=$$

---
#### Exercise 3.1
We have that: $$$$

----
#### Exercise 3.2
----
#### Exercise 3.7
We have that: $$L''(\mu)=\frac{d}{d\mu}3\mu^2(\mu^3 - \mu_{0}^3)=15\mu^4 -6\mu \mu_{0}^3$$Hence, $L''(\mu_{0})=9\mu_{0}^4$.

If $\mu_{0}=0$, then: $$V(\varepsilon):=\text{Vol}(B(\mu_{0},\varepsilon))=\text{Vol}\left( \left\{  \mu\in \mathbb{R}: \frac{1}{2}\mu^6<\varepsilon  \right\} \right)=\text{Vol}(B_{ < (2\varepsilon)^{1/6}}(\mu))=2^{7/6}\varepsilon^{1/6}$$
If $\mu_{0}\neq 0$, then
