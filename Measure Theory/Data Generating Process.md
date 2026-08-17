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

So apparently everyone was asked to do an interview except for me. they're scared of me.  CCRP is truly scared of the influencer potential I have. but guess what: I’m gonna send you one anyway. So Ladies and... beautiful women, I'm Ted, I can cook, I can clean. My friends describe me as a man written by a woman. I read, I'll give you massages, I'll bark like a dog if you'd like me to. 
curves and crevices.

because there is no documentary without men. 


And clearly, I am the only real man this town has to offer. Yeah, the ladies know it. The chicks that work at beanies, they are SOOOO hot. And they love me. Gave ‘em my number but they’re too shy to make the first text. Saw the one lattey hottay on tinder tho,  Maybe she could show them a pic of Charlotte, this other chick at my office. Yeah, I dream of them sometimes… In a professional sort of way of course. Wouldn’t wanna violate corporate code.