#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be an [[LCA group]] and $\lambda$ its [[Haar measure]]. Then, for i.e. for a [[complex measure]] $\mu$, i.e. $\mu\in \mathcal{M}(G)$, we define its ***Fourier transform*** $\widehat{\mu}$ as:$$\widehat{\mu}(\gamma)=\int_{G}^{} \overline{(x,\gamma)} \, d\mu(x) $$
- **Remark**: This extends the usual [[Fourier Transform|Fourier transform on $L^1(G)$]] by: $$L^1(G)\hookrightarrow \mathcal{M}(G),\quad f\mapsto f\cdot \lambda$$
---
##### Properties
> [!lemma] Proposition 1
> We have that the map $$\begin{array}{cccc} {}&{\mathcal{M}(G)}&\to&{B(\widehat{G})}\\&{\mu} &\mapsto & {\widehat{\mu}} \end{array}{}$$ is a bijection, where 
---
> [!lemma] Proposition 2
> Let $\mu\in \mathcal{M}(G)$ and assume $\widehat{\mu}\in L^1(\widehat{G})$. Then, there exists $f\in L^1(G)$ s.t. $\mu=f\cdot\lambda$ and: $$f(x)=\int_{\widehat{G}}^{} \widehat{\mu}(\gamma)(x,\gamma) \, d\omega(\gamma) $$for almost every $x\in G$, where $\omega$ is the [[Haar measure]] on $\widehat{G}.$

> [!proof]-
> We have that $\widehat{\mu}\in L^1(\widehat{G})\cap B(\widehat{G})$. Then by the [[Fourier Transform|Inversion formula]], $$\widehat{\widehat{\mu}}(x)=\int_{\widehat{G}}^{} \widehat{\mu}(\gamma)\overline{(x,\gamma)} \, d\omega(\gamma) $$is in $L^1(G)$ and: $$\int_{G}^{} \overline{(x,\gamma)}d\mu(x)= \widehat{\mu}(\gamma)=\int_{G}^{} \widehat{\widehat{\mu}}(x) (x,\gamma)\, d\lambda(x)=\int_{G}^{} \widehat{\widehat{\mu}}(x ^{-1})\overline{ (x,\gamma)}\, d\lambda(x) $$From Proposition 1, we have the injectivity and if we set $f(x)=\widehat{\widehat{\mu}}(x ^{-1})$, then $\mu=f\cdot\lambda$.
 
---