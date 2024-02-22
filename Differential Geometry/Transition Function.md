#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $\{ U_{\alpha} \}$ be a cover of $M$. We can define the local trivialization as: $$\psi_{\alpha}:\pi ^{-1}(U_{\alpha})\to U_{\alpha}\times \mathbb{R}^k$$Then, the ***transition function*** is defined as:$$\tau_{\beta\alpha}:U_{\alpha}\cap U_{\beta}\to \text{GL}(k,\mathbb{R})$$s.t. $$(\psi_{\beta}\circ \psi_{\alpha}^{-1})(q,v)=(q,\tau_{\beta\alpha}(q)v)$$
---
##### Properties:
> [!lemma] Lemma 1
> We have: 
> 1. $\tau_{\alpha\alpha}=I_{m}$
> 2. $\tau_{\gamma\beta}\circ \tau_{\beta\alpha}=\tau_{\gamma\alpha}$ on $U_{\alpha}\cap U_{\beta}\cap U_{\gamma}$ called the cocycle condition.
---
> [!lemma] Proposition 2
> GIven a cover $\{ U_{\alpha} \}$ and $\tau_{\beta\alpha}$ with these properties, we can construct a rank $k$ vector bundle $E\to M$ with the trivializations $\psi_{\alpha}$ of $\pi ^{-1}(U_{\alpha})$ that admits $\tau_{\beta\alpha}$ as transition functions.