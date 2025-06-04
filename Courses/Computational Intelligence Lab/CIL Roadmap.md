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