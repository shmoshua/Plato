#Definition #RepresentationTheory 

> [!definition]
> Let $K$ be a field and $A,B$ two associative $K$-algebras. A ***$(A,B)$-bimodule*** is a $K$-vector space $V$ s.t. 
> 1. $V$ is a [[Representation|left $A$-module]].
> 2. $V$ is a [[Representation|right $B$-module]].
> 3. for any $v\in V$, $a\in A,b\in B$: $(av)b=a(vb)$
- **Remark**: With this notation, a left $A$-module is a $(A,K)$-bimodule and a right $A$-module is a $(K,A)$-bimodule.
---
##### Properties
> [!lemma] Proposition 1
> Let $B$ be a $K$-[[Associative Algebra|algebra]] and $W$ a left $B$-module, $V$ a right $B$-module. Then, $$V\otimes _{B}W:=(V\otimes W) /\braket{ vb\otimes w-v\otimes bw|v\in V,w\in W,b\in B  } $$
> 1. If $V$ is actually a $(A,B)$-bimodule, $V\otimes_{B}W$ is a left $A$-module.
> 2. If $W$ is actually a $(B,C)$-bimodule, $V\otimes_{B}W$ is a right $C$-module.
> 3. If $V$ is a $(A,B)$-bimodule and $W$ a $(B,C)$-bimodule, $V\otimes_{B}W$ is a $(A,C)$-bimodule.

> [!proof]-
> We have: 
> 1. $a(v\otimes_{B}w)=av\otimes_{B}w$.
> 2. $(v\otimes_{B}w)c=v\otimes_{B}wc$.
---
> [!lemma] Proposition 2 (Associativity of bimodules)
> Let $A,B,C,D$ be four algebras. Let $V$ be a $(A,B)$-bimodule, $W$ a $(B,C)$-bimodule and $X$ a $(C,D)$-bimodule. Then, $$\begin{array}{cccc} &{(V\otimes _{B}W)\otimes _{C}X}&\to&{V\otimes _{B}(W\otimes _{C}X)}\\&{(v\otimes _{B}w)\otimes _{C}x} &\mapsto & {v\otimes _{B}(w\otimes _{C}x)} \end{array}{}$$is an isomorphism.
---
> [!lemma] Proposition 3
> Let $A,B,C,D$ be 4 algebras. Then,
> 1. Let $V$ be a $(A,B)$-bimodule and $W$ a $(B,C)$-bimodule. For $b\in B,c\in C, f\in \text{Hom}_{A}(V,W)$, by setting $$(bf)(v)=f(vb), \quad (fc)(v)=f(v)c$$$\text{Hom}_{A}(V,W)$ is a $(B,C)$-bimodule.
> 2. Let $V$ be a $(B,A)$-bimodule, $W$ a $(C,B)$-bimodule and $X$ a $(C,D)$-bimodule. Then, $$\begin{array}{cccc} {}&{\text{Hom}_{B}(V,\text{Hom}_{C}(W,X))}&\to&{\text{Hom}_{C}(W\otimes _{B}V,X)}\\&{f} &\mapsto & {w\otimes _{B}v\mapsto f(v)w} \end{array}{}$$is an isomorphism as $(A,D)$-bimodules.
----
