#Series #Algorithms 

#### Problem 1.1

 Define $f:\mathbb{R}^n\to \mathbb{R},\beta\mapsto \frac{1}{2n}\left\| X\beta-y \right\|^{2}$. Then, $$\nabla f(\beta ^{*})=\frac{1}{n}X^\top\underbrace{ (X\beta ^{*}-y) }_{ =-w }=-\frac{1}{n}X^\top w$$Let $u:=\widehat{\beta}-\beta ^{*}$. Then, as $\left\| \beta ^{*} \right\|_{1}\leq R$, by the minimality $f(\beta ^{*})\geq f(\beta ^{*}+u)$. Hence, by Taylor:$$f(\beta ^{*})\geq f(\beta ^{*}+u)=f(\beta ^{*})-\frac{1}{n}u^\top X^\top w+\frac{1}{2n}\left\| Xu \right\| ^2_{2}$$It follows that $\left\| Xu \right\|^{2}_{2}\leq 2u^\top X^\top w$ and by Hölder,$$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top w } \leq \|u\|_{1}\left\| X^\top w \right\| _{\infty}$$
 1. **Claim 1**: We have that $\mathbb{E}[\left\| X^\top w \right\|_{\infty}]\leq \sqrt{ n }\cdot O(\sqrt{  \log d })$.
    
    We define $w':= \frac{1}{2\sqrt{ n }}X^\top w$. Then, $w'$ is Gaussian as a sum of independent Gaussian variables. Further, $$\mathbb{E}\left[ \frac{1}{2\sqrt{ n }}X^\top w\right] =\frac{1}{2\sqrt{ n }}X^\top \mathbb{E}[w]=0,\quad\text{Var}\left( \frac{1}{2\sqrt{ n }}X_{i}^\top w \right)=\frac{\sigma^{2}}{4n}X_{i}^\top X_{i}=\frac{\sigma^{2}}{n}\left\| X_{i} \right\| ^2_{2}\leq 1$$Hence, by Exercise Sheet 2 Task 1 Part 1, we get that: $$\mathbb{E}\left[ \max_{i\in[d]} \left(  \frac{1}{2\sqrt{ n }} X^\top_{i}w    \right)^{2}\right] \leq O(\log d)$$Now, by Jensen:$$\left( \mathbb{E}\left[ \frac{1}{2\sqrt{ n }}\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \right)^{2}\leq \mathbb{E}\left[ \frac{1}{4n}\max_{i\in[d]}\braket{ X_{i} , w }   ^{2} \right]=\mathbb{E}\left[ \max_{i\in[d]} \left(  \frac{1}{2\sqrt{ n }} X^\top_{i}w    \right)^{2}\right]$$and 
    
    $\left( \mathbb{E}\left[ \frac{1}{\sqrt{ n }}\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \right)^{2}\leq O(\log d)$. Finally, $$\mathbb{E}\left[\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \leq \sqrt{ n }\cdot O(\log d)^{1/2}$$
 
 However, notice that $\|u\|_{1}\leq\|\beta\|_{1}+\|\beta ^{*}\|_{1}\leq 2 R$ and: $$\mathbb{E}[\left\| X^\top w \right\| _{\infty}]\leq \sqrt{ n }\cdot O(\log 2d)^{1/2}$$Therefore, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^{2}_{2}]\leq \frac{\left\| w_{0} \right\| _{1}}{\sqrt{ n }}O(\log 2d)^{1/2}$$
