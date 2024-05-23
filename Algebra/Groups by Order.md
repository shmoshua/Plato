#Algebra

Let $G$ be a [[group]].

---
##### Groups with Prime Order
> [!lemma] Proposition 1
> If $\left| G \right|=p$ for prime $p$, then $G\cong C_{p}$.

> [!proof]-
> As $\left| G \right|=p$, there exists non-neutral $a\in G$ s.t. $\text{ord}(a)=p$. Then, $\braket{ a  }\leq G$ but at the same time $\left| \braket{ a  } \right|=\left| G \right|=p$. This shows that $\braket{ a }=G$.
---
##### Groups with Prime-squared Order
> [!lemma] Proposition 2
> For any group $G$ with exactly one non-trivial subgroup, $G\cong C_{p^{2}}$.

> [!proof]-
> Let $H$ be the only proper non-trivial subgroup of $G$. Then, there exists $x\in G\backslash H$. Consider the subgroup $\braket{x}$. As $\langle x\rangle \ne H$ and $x\ne e$, we have that $\langle x\rangle =G$ and $G\cong C_n$ where $n=\text{ord}(x)$. As the number of subgroups of a cyclic group equals the number of divisors, $n$ has 3 divisors. This is only the case if $n=p^2$ for some prime $p$.
---
> [!lemma] Proposition 3
> If $G$ is a group with $|G|=p^{2}$ for a prime $p$, $G$ is [[Abelian Group|abelian]]. Therefore, the only possible groups of order $p^{2}$ is $C_{p}\times C_{p}$ and $C_{p^{2}}$ up to isomorphism.

> [!proof]-
> If $G$ is not abelian, we have $Z(G)\neq G$.  That means, $|Z(G)|<|G|$ and it holds that $|Z(G)| \in\{1,p\}$. But with [[Conjugation (Group Theory)|Proposition 1]], there exists $x_{1},\dots,x_{n}\in G$ with $\left| [x_{i}] \right|>1$ and $$p^{2}=|G|=|Z(G)|+\sum_{i=1}^{n}[G:Z_{G}(x_{i})]$$But as $|Z(G)|$ is $1$ or $p$, we have that $1 <[G:Z_{G}(x_{i})]<p^{2}$ and it follows that $[Z_{G}(x_{i})]=p$. Therefore, we have: $$p^{2} =|Z(G)|+np$$ and $\left| Z(G) \right|=p=\left| Z_{G}(x_{i}) \right|$. As $Z(G)\leq Z_{G}(x_{i})$, it follows that $Z(G)=Z_{G}(x_{i})$.
> 
> Let $x\in G\backslash Z(G)$. Then, $x\in[x_{i}]$ for some $i$, $|Z_{G(x)}|=\left| Z_{G}(x_{i}) \right|=p$ and $Z(G)\leq Z_{G}(x)$. It follows that $$x\in Z_{G}(x)=Z(G)$$which is a contradiction.
---
##### Groups with Order of Product of Primes
> [!lemma] Proposition 4
> Let $G$ be a group with $\left| G \right|=pq$ where $p<q$ are primes. 
> 1. If $p\nmid q-1$, then $G\cong C_{p}\times C_{q}$.
> 2. If $p\mid q-1$, then either $G\cong C_{p}\times C_{q}$ or $G\cong C_{q}\rtimes_{\alpha}C_{p}$ where $\alpha:C_{p}\to \text{Aut}(C_{q})$ is any non-trivial [[Group Homomorphism|homomorphism]].

> [!proof]-
> We know that $\left| \text{Syl}_{q}(G) \right|\mid p$ and $\left| \text{Syl}_{q}(G) \right|\equiv_{q}1$. Therefore, $\left| \text{Syl}_{q}(G) \right|=1$ and for $N\in \text{Syl}_{q}(G)$, $N\unlhd G$. 
> 
> Let $H\in \text{Syl}_{p}(G)$. Then, consider $C_{q}\rtimes_{\alpha}C_{p}$ where $\alpha:C_{p}\to \text{Aut}(C_{q})\cong C_{q-1}$.
> 1. If $p\nmid q-1$, then $p$ and $q-1$ are coprime and the only homomorphism $\alpha$ is the trivial one. Therefore, $G\cong C_{p}\times C_{q}$.
> 2. If $p\mid q-1$, then let $(q-1)=mp$. For a homomorphism $\phi:C_{p}\to C_{q-1}$, we need that: $$e=\phi(e)=\phi(a^p)=\phi(a)^p$$Therefore, the only possible homomorphisms are: $$\begin{array}{cccc} {\phi_{i}:}&{C_{p}}&\to&{C_{q-1}}\\&{a^k} &\mapsto & {b^{ikm}} \end{array}{}$$for $0\leq i<p$. Further, notice that for $1\leq i<p$, we can define $\phi_{i}(a^k)=\phi_{1}(a^{ik})$. Thus, by [[Semi-direct Product|Lemma 6]], $C_{q}\rtimes_{\phi_{i}} C_{p}$ are isomorphic for $1\leq i<p$.
>    
>    In conclusion, we get either $G\cong C_{p}\times C_{q}$ (when $\phi_{0}$) and $G\cong C_{q}\rtimes_{\alpha}C_{p}$ for the rest of the cases.
---
##### N:12
> [!lemma] Proposition 5
> There are 5 groups of order 12 up to isomorphism: $$C_{12},\quad C_{2}\times C_{6},\quad(C_{2}\times C_{2})\rtimes C_{3}\cong D_{6},\quad C_{3}\rtimes C_{4}, \quad C_{3}\rtimes(C_{2}\times C_{2})\cong S_{3}\times C_{2}$$

> [!proof]-
> We have $\left| \text{Syl}_{3}(G) \right|\mid 4$ and $\left| \text{Syl}_{3}(G) \right|\equiv_{3}1$. Therefore, $\left| \text{Syl}_{3}(G) \right|=1$ or $4$. Similarly, $\left| \text{Syl}_{2}(G) \right| 3$ and $\left| \text{Syl}_{2}(G) \right|\equiv_{2}1$. Thus, $\left| \text{Syl}_{2}(G) \right|=1$ or $3$.
> 1. **Case $\left| \text{Syl}_{3}(G) \right|=4$.** Then, there are $2\cdot 4=8$ elements of order $3$ in $G$. Therefore, $\left| \text{Syl}_{2}(G) \right|=1$ and there exists $N\unlhd G$ with $\left| N \right|=4$. Further, as there exists $H\leq G$ with $\left| H \right|=3$, $\left| N\cap H \right|=1$ and it holds that $G=N\rtimes_{\kappa}H$.
> 	- If $N\cong C_{4}$, $\left| \text{Aut}(C_{4}) \right|=\varphi(4)=2$ and $\text{Aut}(C_{4})\cong C_{2}$. Therefore, there is no nontrivial homomorphism $\alpha:C_{3}\to \text{Aut}(C_{4})$. This means that $G\cong C_{3}\times C_{4}\cong C_{12}$.
> 	- If $N\cong C_{2}\times C_{2}$, we have that for any $\varphi\in \text{Aut}(C_{2}\times C_{2})$, $\varphi(0,0)=(0,0)$ and $\varphi^3=\iota$. Therefore, we get three homomorphisms:
> 		1. $\phi_{0}(a)=\iota$
> 		2. $\phi_{1}(a):(a,b)\mapsto(a,e)$
> 		3. $\phi_{2}(a):(a,b)\mapsto(e,b)$
> 		
> 		However, $\phi_{2}(a)=\phi_{1}(a^{-1})$. Therefore, we get two groups up to isomorphism: $C_{2}\times C_{2}\times C_{3}$ and $(C_{2}\times C_{2})\rtimes_{\phi_{1}}C_{3}$
> 2. **Case $\left| \text{Syl}_{3}(G) \right|=1$**. Then, there exists $N\unlhd G$ with $\left| N \right|=3$. Further, there exists $H\leq G$ with $\left| H \right|=4$. 
> 	- If $H\cong C_{4}$, $\left| \text{Aut}(C_{3}) \right|=2$ and $\text{Aut}(C_{3})\cong C_{2}$. Then we have two isomorphisms:
> 		1. $\phi_{0}=\iota$
> 		2. $\phi_{1}(a)=b$
> 		
> 		Therefore, we get: $C_{3}\times C_{4}$ and $C_{3}\rtimes_{\phi_{1}}C_{4}$
> 	- If $H\cong C_{2}\times C_{2}$, we have four isomorphisms: one trivial and three where each of the non-trivial elements in $C_{2}\times C_{2}$ is mapped to $e$ in $C_{2}$ and the rest to $a$. However, due to the isomorphism $\alpha:C_{2}\times C_{2}\to C_{2}\times C_{2}$, we have only two groups: $C_{2}\times C_{6}$ and $C_{3}\rtimes_{\phi}(C_{2}\times C_{2})$ 
---
##### List
1. $n=1$: $C_{1}$
2. $n=2$: $C_{2}$
3. $n=3$: $C_{3}$
4. $n=4$: $C_{4}, C_{2}\times C_{2}$
5. $n=5$: $C_{5}$ 
6. $n=6$: $C_{6}, C_{3}\rtimes_{\alpha}C_{2}$
7. $n=7$: $C_{7}$
8. $n=8$:
9. $n=9$: $C_{9},C_{3}\times C_{3}$
10. $n=10$: $C_{10},C_{5}\rtimes_{\alpha}C_{2}$
11. $n=11$: $C_{11}$
12. $n=12$: $C_{12}, C_{2}\times C_{6}, D_{6},C_{3}\rtimes C_{4}, S_{3}\times C_{2}$
13. $n=13$: $C_{13}$
14. $n=14$: $C_{14},C_{7}\rtimes_{\alpha}C_{2}$
15. $n=15$: $C_{15}$
16. $n=16$:
17. $n=17$: $C_{17}$
18. $n=18$: 
19. $n=19$: $C_{19}$
20. $n=20$:
21. $n=21$: $C_{21},C_{7}\rtimes_{\alpha}C_{3}$
22. $n=22$: $C_{22},C_{11}\rtimes_{\alpha}C_{2}$
23. $n=23$: $C_{23}$
24. $n=24$:
25. $n=25$: $C_{25}, C_{5}\times C_{5}$
26. $n=26$: $C_{26},C_{13}\rtimes_{\alpha}C_{2}$
27. $n=27$:
28. $n=28$:
29. $n=29$: $C_{29}$
30. $n=30$:
