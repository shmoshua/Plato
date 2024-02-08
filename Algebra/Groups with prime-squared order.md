#Algebra-I 

---
##### Properties

> [!lemma] Proposition GroupP2.1
> If $G$ is a group with $|G|=p^{2}$ for a prime $p$, $G$ is [[Abelian Group|abelian]].

> [!proof]-
> If $G$ is not abelian, we have $Z(G)\neq G$.  That means, $|Z(G)|<|G|$ and it holds that $|Z(G)| \in\{1,p\}$. But with [[Conjugation (Group Theory)|Fact ConjClass.1]], there exists $x_{1},\dots,x_{n}\in G$ with $\left| [x_{i}] \right|>1$ and $p^{2}=|G|=|Z(G)|+\sum_{i=1}^{n}[G:Z_{G}(x_{i})]$. But as $|Z(G)|$ is $1$ or $p$, we have that $1 <[G:Z_{G}(x_{i})]<p^{2}$ and it follows that $[Z_{G}(x_{i})]=p$. Therefore, we have: $$p^{2} =|Z(G)|+np$$ and $\left| Z(G) \right|=p=\left| Z_{G}(x_{i}) \right|$. It follows that $Z(G)=Z_{G}(x_{i})$.
> 
> Let $x\in G\backslash Z(G)$. Then, $x\in[x_{i}]$ for some $i$, $|Z_{G(x)}|=\left| Z_{G}(x_{i}) \right|=p$ and $Z(G)\leq Z_{G}(x)$. It follows that $$x\in Z_{G}(x)=Z(G)$$which is a contradiction.
---
> [!lemma] Proposition GroupP2.2
> If $G$ is a group with $|G|=p^{2}$ for a prime $p$, either $$G\cong C_{p^2}\quad \text{or}\quad G\cong C_{p}\times C_{p}$$ 
---