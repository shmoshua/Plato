#Definition #Algebra

> [!definition]
> Let $H,K \leq G$. then $HK=\{ hk:h\in H,k\in K \}$ is the ***inner product*** of $H$ and $K$.
- **Remark**: Inner product is generally not commutative.
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a finite group and $H,K \leq G$. Then, $$|HK|= \frac{|H|\cdot|K|}{|H\cap K|}$$

> [!proof]-
> It holds that $HK=\bigcup_{h\in H}^{}hK$ and $H\cap K \leq H$. We have that:
> - for $h_{1},h_{2}\in H$, it holds that $h_{1}K=h_{2}K$ if and only if $h_{1}h_{2}^{-1}\in K$, from Lemma 1. 
> - for $h_{1},h_{2}\in H$, it holds that $h_{1}(H\cap K)=h_{2}(H\cap K)$ if and only if $h_{1}h_{2}^{-1}\in H\cap K$, iff $h_{1}h_{2}^{-1}\in K$.
> 
> Therefore, we have that: $h_{1}K=h_{2}K$ if and only if $h_{1}(H\cap K)=h_{2}(H\cap K).$ It follows that $$|HK|=\left|\bigcup_{h\in H}^{}hK\right|=[H:(H\cap K)]\cdot|K|=\frac{|H|\cdot|K|}{|H\cap K|}$$
- **Corollary**: For $H,K\leq G$ s.t. $|H\cap K|=1$ and $|H|\cdot|K|=|G|$, then $HK=G=KH$.
- **Remark**: If $H,K \leq G$, the inner product $HK$ is generally not a subgroup of $G$.
  This is because, the inverse of $hk\in HK$, $(hk)^{-1}=k^{-1}h^{-1}$ is generally in $KH$.
---
> [!lemma] Theorem 2
> Let $K \leq G$ and $N \unlhd G$, then it holds that:
> $$KN=NK \leq G$$

> [!proof]-
> Let $k\in K$ and $n\in N$. Then, $\tilde{n}:=knk^{-1}\in N$. Therefore, $kn=\tilde{n}k$. It follows that $KN \subseteq NK$. One can show analogously, that $NK \subseteq KN$. Then, we have $NK=KN$.
>
> Let $k_{1}n_{1},k_{2}n_{2}\in KN$. Then, $$(k_{1}n_{1})(k_{2}n_{2})^{-1}=k_{1}\underbrace{ n_{1}n_{2}^{-1} }_{ =:n_{3}\in N }k_{2}^{-1}=\underbrace{ k_{1}(k_{2}^{-1} }_{ =:k_{3}\in K }\underbrace{ k_{2})n_{3}k_{2}^{-1}}_{ =:n_{4}\in N }=k_{3}n_{4}\in KN$$
> Therefore, $KN \leq G$.
---
##### Examples

For the cube group $C$, we have: 
1. $N \unlhd C$ where $N\cong C_{2}\times C_{2}$ defined as the rotations with $\pi$ through axes through surface middle points.
2. $K\cong C_{4}$ defined as the rotations with $\frac{\pi}{2}$.

Then, $|N|=|K|=4$ and $|K\cap N|=2$. Therefore, $|KN|=\frac{4\cdot{4}}{2}=8$. Therefore, $KN\leq C$ and it holds that $KN\cong D_{4}$.

---
$C_{3}\cong \{ e,\rho,\rho^2 \}$ rotation with $\frac{2\pi}{3}$ with the space diagonal and $K\cong D_{4}$. Then, $|C_{3}\cap D_{4}|=1$. Therefore, $C_{3}D_{4}=C=D_{4}C_{3}$.

---
