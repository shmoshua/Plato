#Algorithms #Series 

#### Problem 1
1. We assume that we have a non-degenerate Gaussian distribution, i.e. $\Sigma_{ii}>0$ for all $i\in[d]$. 
2. 
   
   
   Then, for any $t>0$, $$\begin{align}\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>t)&=\mathbb{P}(\exists i\in[d]:x_{i}^{2}>t)\leq \sum_{i\in[d]}^{}\mathbb{P}(x_{i}^{2}>t)= \sum_{i\in[d]}^{}\mathbb{P}(\left| x_{i} \right| >\sqrt{ t })\end{align}$$Now, for all $i\in[d]$, we have that $y_{i}:=\frac{1}{\sqrt{ \Sigma_{ii} }}x_{i}\sim \mathcal{N}(0,1)$ and:$$\mathbb{P}(\left| x_{i} \right| >\sqrt{ t })=\mathbb{P}\left(y_{i} > \sqrt{ \frac{t}{\Sigma_{ii}} } \right)\leq 2\exp\left(-\frac{t}{2\Sigma_{ii}} \right)\leq 2e^{-t/2}$$Hence, $\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>t)\leq 2de^{-t/2}$. 
   
   Now, let $t=2\log 4d$. Then, $\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>2\log d)\leq \frac{1}{2}$. Hence, $$\mathbb{E}[\max_{i\in[d]}x_{i}^{2}]= \sum_{n=1}^{}$$

2. Let $z:=\max_{i\in[d]}x^2_{i}$. For any $t\in \mathbb{R}$, it holds that:$$\exp(t\mathbb{E}[z])\leq \mathbb{E}[\exp(tz)]=\mathbb{E}[\max_{i\in[d]}\exp(tx_{i}^{2})]\leq \sum_{i\in[d]}^{}\mathbb{E}[\exp(tx_{i}^{2})]=\sum_{i\in [d]}^{}\exp\left( \frac{t^{2}\Sigma_{ii}}{2} \right)\leq de^{t^{2} /2}$$Hence, by setting $t=\sqrt{ \log d }$,  $$\mathbb{E}[z]\leq \frac{\log d}{t}+ \frac{t}{2}=\frac{3}{2}\sqrt{ \log d }=O(\sqrt{ \log d })$$
   Let $x\sim \mathcal{N}(0,\sigma^{2})$ where $\sigma^{2}\leq1$. Then,
   $$\mathbb{E}[e^{tx^{2}}]=\frac{1}{\sqrt{ 2\pi\sigma^{2} }}\int_{-\infty}^{\infty} e^{tx^2}e^{-x^{2}/2\sigma^{2}} \, dx =\frac{1}{\sqrt{ 2\pi\sigma^{2} }}\int_{-\infty}^{\infty} e^{-\frac{x^2}{2}(1/\sigma^{2}-2t)} \, dx $$By setting $\rho^{2}:=\frac{\sigma^{2}}{1-2t\sigma^{2}}$, we have: $$\mathbb{E}[e^{tx^{2}}]=\frac{\sqrt{ 1+2t\rho^{2} }}{\sqrt{ 2\pi \rho^{2} }}\int_{-\infty}^{\infty} e^{-x^2/2\rho^{2}} \, dx =\sqrt{ 1+2t\rho^{2}}=\frac{1}{\sqrt{ 1-2t\sigma^{2} }}\leq \frac{1}{\sqrt{ 1-2t }}$$Then, $$\exp(t\mathbb{E}[z])\leq \mathbb{E}[\exp(tz)]=\mathbb{E}[\max_{i\in[d]}\exp(tx_{i}^{2})]\leq \sum_{i\in[d]}^{}\mathbb{E}[\exp(tx_{i}^{2})]\leq \frac{d}{\sqrt{ 1-2t }}$$and $$\mathbb{E}[z]\leq \frac{1}{t}\log d$$
3. 