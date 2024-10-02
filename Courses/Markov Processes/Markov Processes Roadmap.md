#Roadmap #Markov 

### 1. Markov Chains
![[Markov Chain#^a66180]]
![[Markov Chain#^46a7c5|q]]
![[Markov Chain#^fd0c4e|q]]

---
![[Markov Chain#^d921a8]]
![[Markov Chain#^8dc0d8|p]]

---
- **Remark**: In this course we will:
	1. $P$ is the transition probability matrix.
	2. $\mu$, probability vectors are row vectors with $\|\mu\|_{1}$.
	3. column vectors are $f:\mathcal{S}\to \mathbb{R}$ equipped with $\|\cdot\|_{b}$. Then, $\mu f:=\sum_{i\in \mathcal{S}}^{}\mu_{i}f_{i}=\int_{\mathcal{S}}f \, d\mu$ and $$(P^nf)_{i}:=\sum_{j\in \mathcal{S}}^{}(P^n)_{ij}f_{j}=\sum_{j\in \mathcal{S}}^{}f_{j}\mathbb{P}(X_{n}=j|X_{0}=i)=\mathbb{E}(f(X_{n})|X_{0}=i)$$with $\mu P^nf=\mathbb{E}(f(X_{n}))$ given that $X_{0}\sim \mu$. We also have that $\left\| Pf \right\|_{b}\leq \left\| f \right\|_{b}$.

![[Markov Chain#^4aee27|q]]

---
### 2. Random Walks on $\mathbb{Z}^d$

![[Random Walk#^0af11e]]

---
![[Random Walk#^6363a1]]
![[Random Walk#^82c078|p]]

---
##### 2.1 Recurrence and Transience of Random Walks
![[Random Walk#^3b4697|q]]
![[Random Walk#^15327c|q]]

[!TODO] Things to add

---

### 3. Long Time Behaviors
