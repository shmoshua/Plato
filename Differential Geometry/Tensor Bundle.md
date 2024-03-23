#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $r,s\in \mathbb{N}$. Then, the ***$(r,s)$-tensor bundle*** over $M$ is a [[vector bundle]] defined as:$$\text{T}_{(r,s)}M:=\bigcup_{p\in M}^{}\{ p \}\times\underbrace{ \text{T}M\otimes \dots \otimes \text{T}M }_{ r\text{ times} }\otimes \underbrace{ \text{T}^{*}M\otimes \dots \otimes \text{T}^{*}M }_{ s\text{ times} }$$
- **Remark**:  $(\text{T}_{(r,s)}M)_{p}:=\text{T}_{p}M\otimes \dots \otimes \text{T}_{p}M \otimes \text{T}^{*}_{p}M\otimes \dots \otimes \text{T}^{*}_{p}M$ is the space of [[Multilinear k-Form|multilinear $(r+s)$-forms]] $\text{T}^{*}_{p}M\otimes\dots \otimes \text{T}^{*}_{p}M\otimes \text{T}_{p}M \otimes\dots \otimes \text{T}_{p}M\to \mathbb{R}$.
---
##### Properties
> [!lemma] Lemma 1
> A smooth section of the $(r,s)$-tensor bundle $T\in \Gamma(\text{T}_{(r,s)}M)$ is uniquely characterized by the following $C^\infty(M)$-multilinear map: $$\begin{array}{cccc} &{(\Gamma(\text{T}^{*}M))^r \times(\Gamma(\text{T}M))^s}&\to&{C^\infty(M)}\\&{(\omega_{1},\dots,\omega_{r},X_{1},\dots,X_{s})} &\mapsto & {T(\omega_{1},\dots,\omega_{r},X_{1},\dots,X_{s})} \end{array}{}$$

> [!proof]-
> We have that for each $p\in M$, $T_{p}\in (\text{T}_{(r,s)}M)_{p}$ and there exists a multilinear-$(r+s)$-form $$\Phi_{T,p}:\text{T}^{*}_{p}M\otimes\dots \otimes \text{T}^{*}_{p}M\otimes \text{T}_{p}M \otimes\dots \otimes \text{T}_{p}M\to \mathbb{R}$$Therefore, we define: $$T(\omega_{1},\dots,\omega_{r},X_{1},...,X_{s})(p)=\Phi_{T,p}((\omega_{1})_{p},\dots,(\omega_{r})_{p},(X_{1})_{p},\dots,(X_{s})_{p})$$which is smooth. 
---
