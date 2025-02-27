#Algorithms #Series 

#### Problem 1
1. We assume that we have a non-degenerate Gaussian distribution, i.e. $\Sigma_{ii}>0$ for all $i\in[d]$. Then, for any $t>0$, $$\begin{align}\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>t)&=\mathbb{P}(\exists i\in[d]:x_{i}^{2}>t)\leq \sum_{i\in[d]}^{}\mathbb{P}(x_{i}^{2}>t)= \sum_{i\in[d]}^{}\mathbb{P}(\left| x_{i} \right| >\sqrt{ t })\end{align}$$Now, for all $i\in[d]$, we have that $y_{i}:=\frac{1}{\sqrt{ \Sigma_{ii} }}x_{i}\sim \mathcal{N}(0,1)$ and:$$\mathbb{P}(\left| x_{i} \right| >\sqrt{ t })=\mathbb{P}\left(y_{i} > \sqrt{ \frac{t}{\Sigma_{ii}} } \right)\leq 2\exp\left(-\frac{t}{2\Sigma_{ii}} \right)\leq 2e^{-t/2}$$Hence, $\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>t)\leq 2de^{-t/2}$. 
   
   Now, let $t=2\log 4d$. Then, $\mathbb{P}(\max_{i\in[d]}x_{i}^{2}>2\log d)\leq \frac{1}{2}$. Hence, $$\mathbb{E}[\max_{i\in[d]}x_{i}^{2}]= \sum_{n=1}^{}$$

2. Let $z:=\max_{i\in[d]}x^2_{i}$. By Jensen, $$\exp(t\mathbb{E}[z])\leq \mathbb{E}[\exp(tz)]=\mathbb{E}[\max_{i\in[d]}\exp(tx_{i}^{2})]\leq \sum_{i\in[d]}^{}\mathbb{E}[\exp(tx_{i}^{2})]=$$
3. 