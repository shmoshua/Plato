#Definition #Algebra

> [!definition]
> Let $G \curvearrowright M$ be a [[Group Action on Sets|group action]] and $x\in M$. If the [[Orbit and Stablizer|orbit]] has $|Gx|=1$, i.e. $\text{St}_{G}(x)=G$, then $x$ is called a ***fixed point***.

---
##### Examples
1. **Conjugation**: $G \curvearrowright G$, $(a,x)\mapsto axa^{-1}$. Then, 
	- $[x]=\{ axa^{-1}:a\in G \}$.
	- $\text{St}_{G}(x)=\{ a\in G:ax=xa \}=$ [[Centralizer and Normalizer|$Z_{G}(x)$]].
	- $\left| [x] \right|=[G:\text{St}_{G}(x)]$. 
	- $x$ is a fixed point $\iff$ $x\in$ [[Center of a group|$Z(G)$]].
2. **Normalization**: $G\curvearrowright\text{SG}(G)$, the set of all subgroups of $G$, defined as $(a,H)\mapsto aHa^{-1}$. Then, 
	- $[H]=\{ aHa^{-1}:a\in G \}$, i.e. the conjugation classes of $H$.
	- $\text{St}_{G}(H)=\{ a\in G:aH=Ha \}$ is called the ***normalizer***, written as $N(H)$.
	- $G=N(H)$ if and only if $H\unlhd G$.
	- $\left| [H] \right|=[G:N(H)]$
	- $H\unlhd N(H)= \text{St}_{G}(H)\leq G$
---