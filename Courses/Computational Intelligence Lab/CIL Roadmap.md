#Roadmap #CIL 

### 1. Dimension Reduction

![[Autoencoder#^6dcd94]]
![[Autoencoder#^35e987]]

---
![[Autoencoder#^38e8ec]]
![[Autoencoder#^626192]]
![[Autoencoder#^02c4f2|p]]

---
![[Autoencoder#^050a0e]]
![[Autoencoder#^ea0c91|p]]

---
##### Principal Component Analysis
![[Principal Component Analysis#^51f957]]
![[Principal Component Analysis#^a15f10|p]]

---
![[Principal Component Analysis#^585c59]]
![[Principal Component Analysis#^991e71|p]]
![[Principal Component Analysis#^507e38]]

---
![[Principal Component Analysis#^ea7a15]]
![[Principal Component Analysis#^acbb43|p]]

---
### 2. Matrix Completion
![[Matrix Completion#^8ebf29]]

---
![[Matrix Completion#^63d4f7]]
![[Matrix Completion#^5fbf4c|p]]

---
![[Matrix Completion#^8c83e6]]
![[Matrix Completion#^bbfd3e|p]]
![[Matrix Completion#^e18767]]
![[Matrix Completion#^16c47f|p]]

---
![[Matrix Completion#^85d503]]
![[Matrix Completion#^05885c|p]]

---
![[Matrix Completion#^7c8d1b]]
![[Matrix Completion#^cd1140|p]]

---
#### 2.1 Exact Matrix Recovery
> [!lemma] Proposition 1
> Let $A\in \mathbb{R}^{n,n}$ with $\text{rnk}(A)=k$. Then,
> 1. $A$ is not exactly reconstructible if $\left\| \Omega \right\|^{2}_{F}< 2nk-k^{2}$.

> [!proof]-
> We have that:
> 1. By counting the degrees of freedom, only on the left singular vectors we have: $$\sum_{i=1}^{k}n-i=nk-\frac{k(k+1)}{2}$$Therefore, all together we have: $$k+2\left( nk-\frac{k(k+1)}{2} \right)=2nk-k^{2}$$

---
> [!lemma] Theorem 2
> Let $A\in \mathbb{R}^{n,n}$ with $\text{rnk}(A)=k$ that is incoherent with $\mu\geq 1$. If $S$ samples are observed at random, then there exists a universal constant $C\geq 0$ s.t. 
> 1. if $S\geq C\mu^{2}nk\log^6 n$ then: $$A= \underset{ B: \Omega \odot (A-B)=0 }{ \text{argmin} }\left\| B \right\| _{*}$$with probability $\geq 1-n^{-3}$.

---
### 3. Latent Variable Models
#### 3.1 Mixture Models
> [!outlook] Setting
> Let $\pi\in\Delta([k])$ and  $Z_{1},\dots,Z_{n}\sim \pi$ i.i.d. Then, we have that: $p(x_{i}|z_{i}):=p(x_{i};\theta_{z_{i}})$

---
> [!lemma] Theorem 1 (EM-Algorithm)
> In other above setting:
> 1. The log-likelihood is given by $$\log p(x_{1:n};\theta)=\sum_{i\in[n]}^{}\log \sum_{z=1}^{k}\pi_{z}p(x_{i};\theta_{z})$$
> 2. The ELBO is given by:$$\text{ELBO}(x_{1:n};\theta,q)=\sum_{i\in[n]}^{}\sum_{z\in[k]}q_{iz}\log p(x_{i};\theta_{z})-\text{D}(q_{i}\|\pi)$$
> 3. The EM algorithm is given by:
> 	$$q_{iz}\gets \mathbb{P}(Z_{i}=z|x_{i};\theta),\quad \pi_{z}\gets \frac{1}{n}\sum_{i}^{}q_{iz}$$

> [!proof]-
> We have that: 
> 1. From the setting: $$p(x;\theta)=\sum_{z=1}^{k}p(x,z)=\sum_{z=1}^{k}\pi_{z}p(x;\theta_{z})$$
> 2. We have that: $$\log p(x_{1:n};\theta)=\sum_{i\in[n]}^{}\log \sum_{z=1}^{k}\pi_{z}p(x;\theta_{z})= \sum_{i\in[n]}^{}\log \sum_{z=1}^{k}q_{z}\frac{\pi_{z}}{q_{z}}p(x;\theta_{z})\geq  \sum_{i\in[n]}^{}\sum_{z=1}^{k}q_{z}\log \left( \frac{\pi_{z}}{q_{z}}p(x;\theta_{z}) \right)$$
> 3. Consider the Lagrangian: $$\mathcal{L}(q_{i}):=\sum_{z} q_{iz}(\log p(x;\theta_{z})+\log \pi_{z}-\log q_{iz})-\lambda\left( \sum_{z}^{}q_{iz}-1 \right)$$ We have that: $$\frac{ \partial \mathcal{L} }{ \partial q_{iz} }=\log p(x_{i};\theta_{z})+\log \pi_{z}-\log q_{iz}-1-\lambda\overset{ ! }{ = } 0 $$Therefore, $q_{iz}\propto \pi_{z}p(x_{i};\theta_{z})$ and as $\left\| q_{i} \right\|_{1}=1$, we have that $q_{iz}=\mathbb{P}(Z_{i}=z|x_{i};0)$. 
>    
>    Consider now the alternate Lagrangian: $$\mathcal{L}(\pi):=\sum_{i,z}^{}q_{iz}\log \pi_{z}-\lambda\left( \sum_{z}^{}\pi_{z}-1 \right)$$We have that: $$\frac{ \partial \mathcal{L} }{ \partial \pi_{z} } =\frac{\sum_{i}^{}q_{iz}}{\pi_{z}}-\lambda=0$$Therefore, by setting $\pi_{z}:= \frac{1}{n}\sum_{i}^{}q_{iz}$. To optimize $\theta$, we need to know the exact underlying models.

---
#### 3.2 Topic Models
> [!outlook] Setting
> We have:
> 1. Documents $i:=1,\dots,n$ with $s_{i}$ as document length.
> 2. Words $x_{it}\in\Sigma$ as words for $t\in [s_{i}]$.
> 3. Dictionary $\Sigma:=[m]$.
> 
> Words in a document are invariant under reordering.

- **Remark**: From the last assumption, we have that $N_{ij}:= \left| \{ x_{it}=w_{j}: t\in[s_{i}] \} \right|$. This gives us the occurrence matrix $N\in \mathbb{\mathbb{N}}^{n,m}$ which is also a minimal sufficient statistic.

---
> [!lemma] Theorem 1 (EM-Algorithm)
> In the above setting: 
> 1. the log-likelihood is given by: $$\log p(N;\theta)=\sum_{i,j} N_{i,j}\log \sum_{z\in[k]} p(w_{j}|z)p(z|d_{i})$$