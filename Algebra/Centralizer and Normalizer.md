#Definition #Algebra

>[!definition]
> For a group $G$ and $S\subseteq G$. The ***centralizer*** $Z_{G}(S)$  is defined as: $$Z_{G}(S):=\{ x\in G: xax ^{-1}=a \quad \forall a\in S\}$$
> i.e. it's the set of all elements that commute with all $a\in S$. Further, the ***normalizer*** $N_{G}(S)$ is defined as: $$N_{G}(S):=\{ x\in G: xS x ^{-1}=S \}$$

---
##### Properties
> [!lemma] Fact 1
> For a group $G$ and an element $a\in G$:
> 1. If $x\in Z_{G}(a)$, then $x^{-1}\in Z_{G}(a)$.
> 2. $Z_{G}(a) \leq G$.
> 3. $\braket{ a  }\leq Z_{G}(a)$

> [!proof]-
> It holds that:
> 1. if $x\in Z_{G}(a)$, then $ax=xa$. Then, $x^{-1}ax x^{-1}=x^{-1}xax^{-1}$. Therefore, $x^{-1}a=a^{-1}x$. 
> 2. If $x,y\in Z_{G}(a)$, then $y^{-1}\in Z_{G}(a)$. Therefore, 
>     $$a(x y^{-1})=(ax)y^{-1}=(xa)y^{-1}=x(ay^{-1})=x(y^{-1}a)=(x y^{-1})a$$
> 3. As $a^ka=a^{k+1}=aa^k$. Therefore, $\braket{ a }\subseteq Z_{G}(a)$. 
---
> [!lemma] Proposition 2
> For every $H\leq G$, $Z_{H}(a)=Z_{G}(a)\cap H$.

> [!proof]-
> The inclusion $\subseteq$ is trivial. For the other side, let $h\in H$ s.t. $ah=ha$. Then, by definition, $h\in Z_{H}(a)$.
---
> [!lemma] Proposition 3
> Let $H\leq G$. Then, 
> 1. $Z_{G}(H)\unlhd N_{G}(H)$
> 2. there exists $K\leq \text{Aut}(H)$ s.t. $N_{G}(H) /Z_{G}(H)\cong K$.

> [!proof]-
> We have: 
> 1. for $x\in Z_{G}(H)$ and $n\in N_{G}(H)$, and $y\in H$: $$nxn^{-1}y=nx\underbrace{ n^{-1}yn }_{ \in H } n^{-1}=nn^{-1}ynxn^{-1}=ynxn^{-1}$$Therefore, $nxn^{-1}\in Z_{G}(H)$.
> 2. We define: $$\begin{array}{cccc} {\varphi:}&{N_{G}(H)}&\to&{\text{Aut}(H)}\\&{g} &\mapsto & {h\mapsto ghg^{-1}} \end{array}{}$$Then, $\varphi$ is a homomorphism as: $$\varphi(g_{1}g_{2})(h)=g_{1}g_{2}hg_{2}^{-1}g_{1}^{-1}=g_{1}\varphi(g_{2})(h)g_{1}^{-1}=\varphi(g_{1})(\varphi (g_{2})(h))=(\varphi(g_{1})\circ \varphi(g_{2}))(h)$$Further, $$\text{ker }\varphi=\{ g\in N_{G}(H):ghg^{-1}=h\quad \forall h\in H \}=Z_{G}(H)$$Therefore, $N_{G}(H) / Z_{G}(H)\cong \text{Im }\varphi\leq \text{Aut}(H)$.
--- 
##### Related Definitions
- [[Center of a group]]