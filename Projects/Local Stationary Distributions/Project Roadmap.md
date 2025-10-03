 #Project #Roadmap 

### 1. Background
#### 1. Glauber Dynamics
![[Glauber Dynamics#^77c48c]]

---
![[Glauber Dynamics#^a44026]]
![[Glauber Dynamics#^76ec7d|p]]

---
#### 2. Locally Stationary Distributions
##### 2.1 Total Variance and Dirichlet Form
![[Local Stationary Distributions#^6965b1]]

---
![[Local Stationary Distributions#^740eb0]]
![[Local Stationary Distributions#^f7cf08|p]]

---
![[Local Stationary Distributions#^7b987c]]

---
> [!lemma] Proposition 1 (Alternative definitions of Dirichlet Form)
> Let $(P,\pi)$ be a reversible Markov chain. For $f,g:\Omega\to \mathbb{R}$, $$\mathcal{E}(f,g)=\braket{ f , (I-P)g }_{\pi} :=\sum_{x\in \Omega}^{}\pi(x)f(x)(g(x)-(Pg)(x))$$

> [!proof]-
> We have that: $$\begin{aligned}2\mathcal{E}_{P}(f,g)&=\sum_{x,y}^{}\pi(x)P(x,y)(f(x)-f(y))(g(x)-g(y))\\&=\sum_{x,y}\pi(x)P(x,y)\left[ f(x)g(x)-f(x)g(y)-f(y)g(x)+f(y)g(y) \right]\\&=2\sum_{x,y}\pi(x)P(x,y)f(x)g(x)-2\sum_{x,y}\pi(x)P(x,y)f(x)g(y)\\&=2\sum_{x}\pi(x)f(x)g(x)-2\sum_{x,y}\pi(x)P(x,y)f(x)g(y)\\&=2\sum_{x}\pi(x)f(x)(g(x)-(Pg)(x))\\&=2\braket{ f , (I-P)g } _{\pi}\end{aligned}$$

---
![[Local Stationary Distributions#^773377]]