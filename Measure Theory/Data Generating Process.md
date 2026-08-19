#Definition #ILIAD #MeasureTheory #CompMech
 $$\sum_{x\in\square}^{}\sum_{j}^{}T_{ij}^{(x)}=\sum_{x\in\square}^{}\sum_{j}^{}\mathbb{P}(X_{t+1}=x,S_{t+1}=S_{j}|S_{t}=S_{i})=1$$

which token it outputs: $$P=\begin{bmatrix}0 & 1& 0\\0 &0& 1\\1& 0 & 0\end{bmatrix}$$

$$\mathbb{P}(X_{1}=0)=\frac{1}{3}\sum_{i}^{}\sum_{j}^{}T^{(0)}_{ij}=\frac{1}{2}$$

---
$$\begin{aligned}
(\alpha^{(w)}T^{(x)})_{j}
&=\sum_{i}^{}\alpha^{(w)} _{i}T^{(x)}_{{ij}}
\\&=\sum_{i}^{}\mathbb{P}(X_{1:L}=w,S_{L}=S_{i})\mathbb{P}(X_{L+1}=x,S_{L+1}=S_{j}|S_{L}=S_{i})
\\&=\sum_{i}^{}\mathbb{P}(X_{1:L}=w,S_{L}=S_{i})\mathbb{P}(X_{L+1}=x,S_{L+1}=S_{j}|X_{1:L}=w,S_{L}=S_{i})
\\&=\sum_{i}^{}\mathbb{P}(X_{1:L+1}=wx,S_{L+1}=S_{j},S_{L}=S_{i})
\\&=\mathbb{P}(X_{1:L+1}=wx,S_{L+1}=S_{j})
\end{aligned}$$

We have that: $$\sum_{i}^{}\alpha^{(w)}_{i}=\sum_{i}^{}\mathbb{P}(w,S_{L}=S_{i})=\mathbb{P}(w)$$ and $$\pi T^{(w)}=$$

$$\mathbb{P}(010)=\pi T^{(0)}T^{(1)}T^{(0)}1=\begin{bmatrix} 0&1&0\\0&0&0\\0.5&0&0\end{bmatrix}\begin{bmatrix} 0&0&0\\0&0&1\\0.5&0&0\end{bmatrix}=\begin{bmatrix}0&0&1\\0&0&0\\0&0&0\end{bmatrix}\begin{bmatrix} 0&1&0\\0&0&0\\0.5&0&0\end{bmatrix}=\begin{bmatrix} 0.5 &0& 0\\0&0&0\\0&0&0\end{bmatrix}1=\frac{1}{6}$$

---
##### Core 3/4
We have that: 
1. $$\eta^{(w)}_{j}=\mathbb{P}(S_{|w|}=S_{j}|X_{1:|w|}=w)=\frac{\alpha^{(w)}_{j}}{\mathbb{P}(w)}=\frac{\alpha^{(w)}_{j}}{\alpha^{(w)}1}$$
2. Let $w$ any word s.t. $\eta=\eta^{(w)}$. We have that: $$F_{x}(\eta)=\eta^{(wx)}=\frac{\alpha^{(wx)}}{\alpha^{(wx)}1}=\frac{\alpha^{(w)}T^{(x)}}{\alpha^{(w)}T^{(x)}1}=\frac{\eta^{(w)}T^{(x)}}{\eta^{(w)}T^{(x)}1}$$by diving the numerator and denominator by $\alpha^{(w)}1$. The denominator is given as: $$\begin{aligned}\eta^{(w)} T^{(x)}1&=\sum_{i,j}^{}\mathbb{P}(S_{|w|}=S_{i}|w)\mathbb{P}(X_{{|w|}+1}=x,S_{|w|+1}=S_{j}|S_{|w|}=S_{i})
   \\&=\sum_{i}^{}\mathbb{P}(S_{|w|}=S_{i}|w)\mathbb{P}(X_{{|w|}+1}=x|S_{|w|}=S_{i})\\&=\sum_{i}^{}\mathbb{P}(X_{{|w|}+1}=x,S_{|w|}=S_{i}|w)\\&=\mathbb{P}(X_{{|w|}+1}=x|w)\end{aligned}$$

---

So apparently everyone was asked to do an interview except for me. They're scared of me. I think CCRP is truly scared of the influencer potential I have. but guess what: I’m gonna send you one anyway. So, Ladies and... ma baddies, my name is Ted, short for tornado of sexual charisma. I am... a man that truly appreciates the female body. The curves and crevices.... I got that natural pheromone down, like how I walked into beanies yesterday and all the cute lil girls that work there were just... they just couldn't wait for me to like fill their cute lil coffee cups, you know? Like i'll cream ur coffee, grind ur beans and pump my vanilla into ur gaping caramel macchiato type shit. Ugh coffee makes me so horny. So call me girls, and the two of us can do some latte art? You know how they say, once you go Ted, you'll never go to bed.


---
##### Problem 1
1. We have that: 
   $$\begin{aligned}
   \mathcal{L}(W)&=\frac{1}{2}\left\| \text{diag}(s_{1},\dots,s_{d})-\prod_{l=1}^{L}\text{diag}(w_{l}^{(1)},\dots,w_{l}^{(d)}) \right\| ^2_{F}
    \\&=\frac{1}{2}\sum_{i=1}^{d}\left( s_{i}-\prod_{l=1}^{L}w_{l}^{(i)} \right)^2
   \end{aligned}$$
2. We have that the FOCs are: $$0=w_{2}(s-w_{1}w_{2}),\quad 0=w_{1}(s-w_{1}w_{2})$$Hence, if $w_{2} = 0$, then $w_{1}=0$ and we have the origin. Otherwise, $w_{1}w_{2} = s$.
3. We have that in that case: $$W=P_{\leq r}M=\text{diag}(s_{1},\dots,s_{r},0,\dots,0)$$ and the loss is given by: $$\mathcal{L}(W)=\frac{1}{2}\sum_{\alpha =r+1}^{d}s_{\alpha}^{2}$$
4. We have that: $$\mu(g\cdot \theta)=W_{L}g^{-1}_{L-1}g_{L-1}W_{L-1}g_{L-2}^{-1}\cdots g_{1}W_{1} = W_{L}\dots W_{1}=\mu(\theta)$$

---
##### Problem 2
We have that: 
1. $$\dot{W}_{1}=-\nabla_{W_{1}} \frac{1}{2}\left\| M-W_{2}W_{1} \right\| ^{2}_{F}=W_{2}^\top(M-W_{2}W_{1})$$ and $$\dot{W}_{2}=-\nabla_{W_{2}} \frac{1}{2}\left\| M-W_{2}W_{1} \right\|^{2}_{F}=-(-W_{1}(M-W_{2}W_{1})^\top )^\top = (M-W_{2}W_{1})W_{1}^\top$$
2. We have that: $$\begin{aligned}\dot{G}&=\dot{W}_{2}^\top W_{2}+W_{2}^\top \dot{W}_{2}-\dot{W}_{1}W_{1}^\top -W_{1}\dot{W}_{1}^\top\\&=W_{1}(M-W_{2}W_{1})^\top W_{2}+W_{2}^\top(M-W_{2}W_{1})W_{1}^\top-W_{2}^\top(M-W_{2}W_{1})W_{1}^\top -W_{1}(M-W_{2}W_{1})^\top W_{2}\\&=0\end{aligned}$$
3. We have that: 
	1. $$\begin{aligned}\dot{W}&=\dot{W}_{2}W_{1}+W_{2}\dot{W}_{1}\\&=(M-W)W_{1}^\top W_{1}+W_{2}W_{2}^\top(M-W)\end{aligned}$$
	2. It's positive semidefinite by definition. Now, $$W^\top W = W_{1}^\top W_{2}^\top W_{2}W_{1}=W_{1}^\top W_{1}W_{1}^\top W_{1}=(W_{1}^\top W_{1})^{2}$$
	3. Similarly, $$W W^\top = W_{2}W_{1}W_{1}^\top W_{2}^\top = W_{2}W_{2}^\top W_{2}W_{2}^\top = (W_{2}W_{2}^\top)^{2}$$
	4. We have that: $$\dot{W} = (WW^\top)^{1/2}(M-W)+(M-W)(W^\top W)^{1/2}$$
4. Trivial.
---
##### Problem 3
1. We have that: $$WW^\top=U\text{diag}(w_{1},\dots,w_{d})V^\top V \text{diag}(w_{1},\dots,w_{d})U^\top=U\text{diag}(w_{1}^{2},\dots,w_{d}^{2})U^\top=(U\text{diag}(w_{1},\dots,w_{d})U^\top)^{2}$$The other case is similar. Further, $M-W$ is obvious.
2. We have that: $$\dot{W}=U\text{diag}(2w_{1}(s_{1}-w_{1}),\dots,2w_{d}(s_{d}-w_{d}))V^\top$$Therefore, $\dot{w}_{\alpha}=2w_{\alpha}(s_{\alpha}-w_{\alpha})$.
3. We have that: $$w_{f}=\frac{s}{1+\left( \frac{s}{w_{0}}-1 \right)e^{-2st_{\alpha}}} \iff e^{-2st_{\alpha}}=\frac{w_{0}(s-w_{f})}{w_{f}(s-w_{0})}\iff t_{\alpha}=\frac{1}{2s}\ln\frac{w_{f}(s-w_{0})}{w_{0}(s-w_{f})}$$
---
##### Problem 4

---
We have that: $$F(w^{*},1)=\nabla_{w}L(w^*;1)$$

$$0=\frac{ \partial  }{ \partial \beta_{i} } \nabla _{w}L(w^*(\beta);\beta)=\nabla^{2}_{w}L(w^{*}(\beta);\beta)\frac{ \partial w^{*}(\beta) }{ \partial \beta_{i} } + \nabla _{w}L(w^{*}(\beta),z_{i})$$Hence, we have: $$\frac{ \partial w^{*} }{ \partial \beta_{i} } =-H^{-1}\nabla _{w}L(w^{*},z_{i})$$