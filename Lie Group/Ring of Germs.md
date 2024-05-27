#Definition #LieGroups 

> [!definition]
> For a [[smooth manifold]] $M$ and $p\in M$, the ***ring of germs*** of $p$ of smooth functions is given as: $$C^\infty(p):=\{ (U,f):U\ni p\text{ is open and }f\in C^\infty(U,\mathbb{R}) \} /_{\sim}$$
> where $(U_{1},f)\sim(U_{2},g)$ if and only if there exists $p\in U_{3}\subseteq U_{1}\cap U_{2}$ s.t. $f|_{U_{3}}=g|_{U_{3}}$. 
---
##### Properties
> [!lemma] Proposition 1
> For smooth manifold $M$ and $p\in M$, the ring of germs is indeed a [[ring]] with 
> 1. $[(U,f)]+[(V,g)]:=[(U\cap V,f+g)]$
> 2. $[(U,f)]\cdot[(V,g)]:=[(U\cap V,fg)]$

> [!proof]+
> We first show that the operations are well-defined.
> 1. Let $(U_{1},f_{1})\sim(U_{2},f_{2})$ and $(V_{1},g_{1})\sim(V_{2},g_{2})$. Then, $U_{3}\cap V_{3}\subseteq(U_{1}\cap U_{2})\cap(V_{1}\cap V_{2})$ and for $x\in U_{3}\cap V_{3}$: $$(f_{1}+g_{1})(x)=f_{1}(x)+g_{1}(x)=f_{2}(x)+g_{2}(x)=(f_{2}+g_{2})(x)$$$$f_{1}g_{1}(x)=f_{1}(x)g_{1}(x)=f_{2}(x)g_{2}(x)=f_{2}g_{2}(x)$$
> 2. Further, $[(M,0)],[(M,1)]$ are the additive and multiplicative neutral element.
>    The associa

---