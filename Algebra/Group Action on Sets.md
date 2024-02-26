#Definition #Algebra 

> [!definition]
> Let $G$ be a [[Group|group]] and $M$ a set. Then, the function $\circ:G\times M\to M, (a,x) \mapsto a\circ x$ is a ***group action of $G$ on $M$*** if the followings hold:
> 1. for all $x\in M$, $e_{G}\circ x = x$.
> 2. for all $a,b\in G$ and $x\in M$, $(ab)\circ x=a \circ(b \circ x)$
> 
> Then, we write $G \curvearrowright M$. $G$ is called the ***transformation group*** and $M$ is called the **$G$-set**. Further, if $M$ is a [[Topological Space|topological space]], for all $g\in G$: $x\mapsto a\circ x$ is a [[Homeomorphism]].
---
##### Properties
> [!lemma] Theorem 1
> The followings hold: 
> 1. Let $\circ:G\times M \to M,(a,x) \mapsto a\circ x$ be a group action. Then, the function $\varphi:G \to S(M), a \mapsto \varphi_{a}$ where $$\varphi_{a}(x)=a\circ x$$ is a [[group homomorphism]].
> 2. If $\varphi:G \to S(M),a \mapsto \varphi_{a}$ is a homomorphism, then we can define a group action as $\circ:G\times M \to M, (a,x)\mapsto a\circ x:=\varphi_{a}(x)$.
>    
> In other words, every group action $G \curvearrowright M$ represents a homomorphism $G \to S(M)$ and vice versa.

> [!proof]-
> Let's prove them!
> 1. Firstly, let's show that for all $a\in G$, $\varphi_{a}\in S(M)$, i.e. $\varphi_{a}$ is a bijection on $M$. As we know that there exists an inverse $\varphi_{a^{-1}}$ for which it holds that for all $x\in M$: $$(\varphi_{a}\circ \varphi_{a^{-1}})(x)=\varphi_{aa^{-1}}(x)=\varphi_{e}(x)=x$$ 
>    Now, we show that $\varphi$ is a group homomorphism. For $a,b\in G$:$$\varphi(ab)(x)=\varphi_{ab}(x)=(ab)\circ x=a\circ (b\circ x)=\varphi_{a}(\varphi_{b}(x))=(\varphi_{a}\circ \varphi_{b})(x)$$ for all $x\in M$. Therefore, $\varphi(ab)=\varphi(a)\circ\varphi(b)$.
> 2. We will show that $G \curvearrowright M$. Firstly, $e \circ x=\varphi_{e}(x)=\text{id}(x) =x$. Secondly, we have for all $a,b\in G$ and $x\in M$: $$(ab)\circ x=\varphi_{ab}(x)=\varphi_{a}(\varphi_{b}(x))=a\circ (b\circ x)$$

---

##### Examples
- $G \curvearrowright G$: Following are possible group action:
	1. left-transformation $(a,x)\mapsto ax$ 
	2. right-transformation $(a,x)\mapsto xa$
	3. [[Conjugation (Group Theory)|conjugation]] $(a,x)\mapsto ax a^{-1}$ which forms a subgroup.
- Let $M$ be the set of subgroups of $G$. Then $\circ:G\times M \to M, (a,H)\mapsto aHa^{-1}$ is the conjugated subgroup of $H$.
- Let $G \curvearrowright M$. For $H\leq G$, we define: $$M^H:=\{ x\in M:\forall h\in H, h\circ x=x\}$$ Prove that if $H \unlhd G$, then the action $G \curvearrowright M$ induces an action on $G / H \curvearrowright M^H$.$$\begin{array}{ccc}\\G / H \times M^H& \to & M^H\\(gH,x)&\mapsto & g\circ x\end{array}$$Then, for $h\in H$: $$h\circ (g\circ x)=(gg^{-1}hg)\circ x=(g \tilde{h})\circ x =g\circ (\tilde{h}\circ x)=g\circ x$$
  Now, suppose $g_{1}H=g_{2}H$. Then, $$f(g_{2}H,x)=g_{2}\circ x=(g_{1}\underbrace{ g_{1}^{-1}g_{2} }_{ \in H })\circ x=(g_{1}h)\circ x=g_{1}\circ (h\circ x)=g_{1}\circ x=f(g_{1}H,x)$$
---