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
> 1. Documents $d_{1},\dots,d_{n}\sim \mathcal{D}$ with $s_{i}$ as document length for $i\in[n]$.
> 2. Topics $z_{1},\dots,z_{n}\in[k]$ given by $p(z|d_{i})$.
> 3. Words $x_{it}\in\Sigma$ as words for $t\in [s_{i}]$.
> 4. Dictionary $\Sigma:=[m]$.
> 
> Words in a document are invariant under reordering.

- **Remark**: From the last assumption, we have that $N_{ij}:= \left| \{ x_{it}=w_{j}: t\in[s_{i}] \} \right|$. This gives us the occurrence matrix $N\in \mathbb{\mathbb{N}}^{n,m}$ which is also a minimal sufficient statistic.

---
> [!lemma] Theorem 1 (EM-Algorithm / PLAS)
> In the above setting: 
> 1. the log-likelihood is given by: $$\log p(x;\theta)=\sum_{i,t}\log \sum_{z\in[k]} p(x_{it}|z)p(z|d_{i})=\sum_{i,j} N_{i,j}\log \sum_{z\in[k]} p(w_{j}|z)p(z|d_{i})$$
> 2. the ELBO is given by: $$\text{ELBO}(x;\theta,q)=\sum_{i\in[n]}^{}\sum_{t\in[s_{i}]}^{}\sum_{z\in[k]}^{}q_{itz}(\log p(x_{it}|z)+\log p(z| d_{i})-\log q_{itz})$$
> 3. the EM-algrotihm is given by: $$q_{itz}\gets \frac{p(x_{it}|z)p(z|d_{i})}{\sum_{z'}^{}p(x_{it}|z')p(z'|d_{i})},\quad p(w_{j}|z)\gets\frac{\sum_{i,t}^{}\mathbb{1}_{x_{it}=w_{j}}q_{itz}}{\sum_{i,t}^{}q_{itz}},\quad p(z|d_{i})\gets  \frac{1}{s_{i}}\sum_{t\in[s_{i}]}^{}q_{itz}$$

> [!proof]-
> We have that:
> 1. This is given by: $$p(x;\theta)=\prod_{i,t}^{}\sum_{z}^{}p(x_{it}|z)p(z|d_{i})$$Further, $$\sum_{i,t}\log \sum_{z\in[k]} p(x_{it}|z)p(z|d_{i})=\sum_{i,j,t}\mathbb{1}_{x_{it}=w_{j}}\log \sum_{z\in[k]} p(w_{j}|z)p(z|d_{i})=\sum_{i,j}N_{ij}\log \sum_{z\in[k]} p(w_{j}|z)p(z|d_{i})$$
> 2. Given by: $$\begin{aligned}\sum_{i,t}\log \sum_{z\in[k]} p(x_{it}|z)p(z|d_{i})&= \sum_{i,t}\log \sum_{z\in[k]} q_{itz}\frac{p(x_{it}|z)}{q_{itz}}p(z|d_{i})\\&\ge \sum_{i,t}\sum_{z\in[k]} q_{itz}\left( \log p(x_{it}|z)+\log p(z|d_{i})  - \log q_{itz}\right)\\&= \sum_{i,j,t}\sum_{z\in[k]}\mathbb{1}_{x_{it}=w_{j}} q_{itz}\left( \log p(w_{j}|z)+\log p(z|d_{i})  - \log q_{itz}\right)\end{aligned}$$
> 3. Similarly as above, we have: $$\frac{ \partial \mathcal{L} }{ \partial q_{itz} } =\log p(x_{it}|z)+\log p(z|d_{i})-\log q_{itz}-1-\lambda\overset{ ! }{ = }0$$and we have the desired expression. Further, $$\frac{ \partial \mathcal{L} }{ \partial p(w_{j}|z) } =\frac{\sum_{i,t}^{} \mathbb{1}_{x_{it}=w_{j}} q_{itz}}{p(w_{j}|z)}-\lambda\overset{ ! }{ = }0$$Therefore, we get the desired expression. Lastly, $$\frac{ \partial \mathcal{L} }{ \partial p(z|d_{i}) } =\frac{\sum_{t} q_{itz}}{p(z|d_{i})}-\lambda\overset{ ! }{ = }0$$Therefore, we have the desired expression. 

---
> [!lemma] Theorem 2 (Latent Dirichlet Allocation (LDA))
> Let from the above setting further define that: $$u_{jz}:=p(w_{j}|z),\quad v_{zi}:=p(z|d_{i})$$Now, if we assume that $v_{i}\sim \text{Dir}(\alpha)$ i.i.d. Then, 
> 1. the likelihood is given by:$$p(x_{i1:s_{i}};U)=\int_{\Omega}\prod_{t}^{}p(x_{it}|v_{i},U) p(v_{i}) \, dv,\quad p(x_{it}=w_{j}|U,v_{i})=\sum_{z}^{}u_{jz}v_{zi}$$

> [!proof]-
> We have:
> 1. Notice that: $$p(x_{i1:s_{i}};U)=\int_{\Omega}p(x_{i 1:s_{i}},v_{i};U)  \, dv=\int_{\Omega}p(x_{i 1:s_{i}}|v_{i},U) p(v_{i}) \, dv=\int_{\Omega}\prod_{t}^{}p(x_{it}|v_{i},U) p(v_{i}) \, dv $$and $$p(x_{it}=w_{j}|U,v_{i})=\sum_{z}^{}p(w_{j}|z)v_{zi}=\sum_{z}^{}u_{jz}v_{zi}$$

- **Remark**: LDA incorporates Bayesian learning and prevents overfitting. Produces topic distributions over documents. More complicated but there are other scalable implementations using MCMC or Variational EM.

---
> [!lemma] Theorem 3 (Non-negative Matrix Factorization (NMF))
> From above, we see that $U,V$ are non-negative matrices s.t. $$\widehat{N}:=V^\top U ^\top,\quad \widehat{N}_{ij}=p(w_{j}|d_{i})$$
> Then, 
> 1. the log-likelihood is given by: $$\log p(N;U,V)=\sum_{i,j} N_{ij}\log \widehat{N}_{ij}$$
> 2. In particular, the topic model can be represented as a non-negative matrix factorization problem with log-likelihood objective.
- **Remark**: The NMF can be solved using ***alternating least squares*** with projection steps to project it back to the space of positive matrices.
- **Remark**: Comparing NMF and LDA, 
	1. NMF is fast, simple and interpretable. 
	2. LDA is a fully Bayesian model with priors and better generalization
---
#### 3.3. Embeddings
> [!outlook] Setting
> We have:
> 1. a vocabulary $\Sigma$ 
> 2. a sequence of words $x_{1},\dots,x_{T}\in \Sigma$
> 
> The goal is to learn parameters $\theta$ s.t. each word predicts its context words.

---
> [!lemma] Proposition 1
> We have that:
> 1. the log-likelihood is given as: $$\log p(x;\theta)=\sum_{t=1}^{T}\sum_{i=-R}^{R} \log p(x_{t+i}|x_{t};\theta)\cdot \mathbb{1}_{i\neq 0}$$
> 2. For words $v,w\in \Sigma$, we then have that: $$p(v|w;\theta)=\frac{\exp(\xi_{w}^\top z_{v}+b_{v})}{\sum_{u} \exp(\xi_{w}^\top z_{u}+b_{u})},\quad  w\mapsto \theta_{w}:=(z_{w},\xi_{w},b_{w})\in \mathbb{R}^{2n+1}$$
> 3. The updated log-likelihood is given as: $$\log p(x;\theta)=\sum_{v,w} N_{vw}\left( \xi_{w}^\top z_{v}+b_{v}-\ln \sum_{u}\exp(\xi_{w}^\top z_{u}+b_{u}) \right)$$

---
> [!lemma] Proposition 2 (Binary Classification Objective)
> Let $S^+,S^-\subseteq \Sigma^{2}$ where: 
> $$\begin{aligned}S^+&:=\{ (x_{t},x_{t+i}):t\in[T],i\in\{ -R,\dots,-1,1,\dots,R \} \}\\ S^-&:=\{ (x_{t},v_{tj}):t\in[T],v_{tj}\overset{ \text{iid} }{ \sim } q ,j\in[r]\} \end{aligned}$$where $q\in \Delta(\Sigma)$ and $r$ is the negative-positive ratio parameter. Then, 
> 1. the logistic log likelihood is given by: $$\log(x;\theta)=$$