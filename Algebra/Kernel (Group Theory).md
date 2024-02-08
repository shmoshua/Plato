#Definition #Algebra-I 

> [!definition]
> For a [[Group Homomorphism|group homomorphism]] $\varphi:G \to H$, the ***kernel*** of $\varphi$ is defined as:$$\text{ker}(\varphi):=\{ x\in G: \varphi(x)=e_{H} \}$$
---
##### Properties
> [!lemma] Proposition 1
> If $\varphi:G\to H$ is a homomorphism, then $\text{ker}(\varphi) \unlhd G$.

> [!proof]-
> First, we show that $\text{ker}(\varphi)$ is a subgroup. Let $a,b\in \text{ker}(\varphi)$. Then, $$\varphi(ab^{-1})=\varphi(a)\varphi(b^{-1})=\varphi(a)\varphi(b)^{-1}=e_{H}e_{H}=e_{H}$$
> Therefore, $ab^{-1}\in \text{ker}(\varphi)$. We will also show that $\text{ker}(\varphi)\unlhd G$. For $x\in G$ and $a\in \text{ker}(\varphi)$, we have that: $$\varphi(x a x^{-1})=\varphi(x)\varphi(a)\varphi(x)^{-1}=\varphi(x)\varphi(x)^{-1}=e_{H}$$It follows that $xax^{-1}\in \text{ker}(\varphi)$.
---
> [!lemma] Proposition 2
> If $\varphi:G\to H$ is an isomorphism, then $\text{ker}(\varphi) \leq Z(G)$.

> [!proof]-
> For $a\in \text{ker}(\varphi)$ and $x\in G$, we have that: $$\varphi(ax)=\varphi(a)\varphi(x)=\varphi(x)=\varphi(x)\varphi(a)=\varphi(xa)$$
> Now, from the injectivity of $\varphi$, we have that $ax=xa$. Therefore, $a\in Z(G)$.
---
> [!lemma] Lemma 3
> If $N \unlhd G$, the ***projection*** $$\begin{array}{cccc} {\pi:}&{G}&\to&{G / N}\\&{x} &\mapsto & {xN} \end{array}{}$$ is a surjective homomorphism called the ***natural homomorphism*** of $G$ to $G / N$. It further holds that: $$\text{ker}(\pi)=N$$

> [!proof]-
> We have:
> $$\pi(xy)=(xy)N=(xN)\cdot (yN)=\pi(x)\pi(y)$$
> Further, for $xN\in G / N$, $\pi(x)=xN$. Therefore, $\pi$ is surjective. Lastly, $$\text{ker}(\pi)=\{ x\in G: xN=N \}=\{ x\in G: x\in N \}=N$$
- **Corollary**: For $N\unlhd G$, there exists a group $H$ with a homomorphism $\varphi$ s.t. $\text{ker}(\varphi)=N$.
---


