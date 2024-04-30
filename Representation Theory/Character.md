#Definition #RepresentationTheory 

> [!definition]
> Let $V$ be a finite-dimensional [[representation]] of an [[Associative Algebra|associative $K$-algebra]] $A$ with action $\rho$. Then, the ***character*** of $V$ is a linear map $$\begin{array}{cccc} {\chi_{V}:}&{A}&\to&{K}\\&{a} &\mapsto & {\text{Tr}(\rho(a))} \end{array}{}$$
> A ***character*** $\chi$ of a group $G$ for a field $L$ is a group homomorphism $\chi:G\to L^\times$
- **Related definition**: Let $[A,A]:=\braket{ [x,y]:x,y\in A }$. Then, $[A,A]\subseteq \text{ker }\chi_{V}$ and we can quotient the map into $\chi_{V}:A / [A,A]\to K$ as well.
- **Related definition**: The characters $\chi_{1},\dots,\chi_{n}$ are ***linearly independent*** over $L$, if there is no non-trivial $a_{1},\dots,a_{n}\in L$ s.t. $a_{1}\chi_{1}+\dots+a_{n}\chi_{n}=0$.
---
##### Properties
> [!lemma] Theorem 1
> Let $\chi_{1},\dots,\chi_{n}$ be distinct characters of a group $G$ for a field $L$. Then, they are linearly independent over $L$.

> [!proof]-
> Assume they are linearly dependent. Then, choose $a_{1},\dots,a_{m}\in L$ with minimal number of non-zero coefficients s.t. $a_{1}\chi_{1}+\dots+a_{m}\chi_{m}=0$ with $m\leq n$.
> 
> Let $g_{0}\in G$ s.t. $\chi_{1}(g_{0})\neq \chi_{m}(g_{0})$. Then, for all $g\in G$, $$a_{1}\chi_{1}(g g_{0})+\dots+a_{m}\chi_{m}(g g_{0})=a_{1}\chi_{1}(g)\chi_{1}(g_{0})+\dots+a_m\chi_{m}(g)\chi_{m}(g_{0})=0$$Therefore, $$a_{1}\chi_{1}(g)(\chi_{n}(g_{0})-\chi_{1}(g_{0}))+a_{m-1}\chi_{m-1}(g)(\chi_{m}(g_{0})-\chi_{m-1}(g_{0}))=0$$As $\chi_{m}(g_{0})-\chi_{1}(g_{0})\neq 0$, we have a non-trivial relation which contradicts the minimality of $m$.
---
> [!lemma] Theorem 2
> Let $\sigma_{1},\dots,\sigma_{n}$ be distinct embeddings of a field $K$ into $L$. Then, they are linearly independent over $L$ as functions on $K$. 
> 
> In particular, distinct automorphisms on a field are linearly independent.

> [!proof]-
> Consider any injective homomorphism $\sigma:K\to L$. Then, as $\sigma(0)=0$ and $\sigma$ is injective, $\sigma(K^\times)\subseteq L^\times$ and $\sigma$ is a character of $K^\times$ into $L^\times$. 
---
