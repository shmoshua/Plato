#Definition #Algebra-I 

> [!definition]
> If $G \cong (N\times H,*)$ s.t.
> 1. $N\unlhd G, H \leq G$
> 2. $\left| N \cap H \right|=1,G=NH$
>    
> Then, $G$ is the ***inner semi-direct product*** of $N$ with $H$, denoted as: $G=N \rtimes_{\kappa}H$.
> 
> For any groups $N,H$ and a homomorphism $\alpha:H \to \text{Aut}(N)$, $G=(N\times H,*_{\alpha})$ is the ***outer semi-direct product*** of $N$ and $H$, denoted with $N \rtimes_{\alpha}H$.
---
##### Properties
> [!lemma] Fact 1
> For a group $G$, $N\unlhd G$, $H \leq G$, if $\left| H\cap N \right|=1$  and $|N|\cdot|H|=|G|$, then for $a,b\in N$ and $x,y\in H$, we have that: $$(ax)(by)=(axbx^{-1})(xy)\in NH$$

- **Remark**: We can write $G$ as $N \times H$ with binary operation $*$ s.t.$$(a,x)*(b,y)=(axbx^{-1},xy)$$
---
> [!lemma] Proposition 2
> Let $G$ be a group, $N\unlhd G$, $H \leq G$, then $$\begin{array}{cccc} {\kappa:}&{H}&\to&{\text{Aut}(N)}\\&{x} &\mapsto & {\kappa_{x}:N \to N, a \mapsto xax^{-1}} \end{array}{}$$
> is a [[Group Homomorphism|group homomorphism]].

> [!proof]-
> We will show the following:
> 1. $\kappa_{x}\in \text{Aut}(N)$: We have: $$\kappa_{x}(ab)=x(ab)x^{-1}=(xax^{-1})(xbx^{-1})=\kappa_{x}(a)\kappa_{x}(b)$$and $xNx^{-1}=N$. Therefore, $\kappa_{x}$ is an automorphism.
> 2. $\kappa$ is a homomorphism: $$\kappa(xy)(a)=xyay^{-1}x^{-1}=x(\kappa_{y}(a))x^{-1}=\kappa_{x}(\kappa_{y}(a))=(\kappa_{x}\circ \kappa_{y})(a)$$
---
> [!lemma] Proposition 3
> For a group $G$, $N\unlhd G, H\leq G$, where $\left| N\cap H \right|=1$ and $\left| N \right|\cdot \left| H \right|=\left| G \right|$, then: $$G\cong (N \times H, *)$$where $(a,x)*(b,y)=(a\kappa_{x}(b),xy)$ and $\kappa$ is defined as in Proposition 2. Then:
> 1. $(e_{G},e_{G})$ is the neutral element.
> 2. $(x^{-1}a^{-1}x,x^{-1})=(\kappa_{x^{-1}}(a^{-1}),x^{-1})$ is the inverse of $(a,x)$

> [!proof]-
> We have that:
> - Every element in $G$ can be uniquely written as $ax$ where $a\in N$ and $x\in H$.
> - If we write $(a,x),(b,y)\in N \times H$, then with Fact 1, we get: $$(a,x)*(b,y)=(axbx^{-1},xy)=(a\kappa_{x}(b),xy)\in N\times H$$
---
> [!lemma] Theorem 4
> Let $N,H$ be two groups and let: $$\begin{array}{cccc} {\alpha:}&{H}&\to&{\text{Aut}(N)}\\&{x} &\mapsto & {\alpha_{x}} \end{array}{}$$be a homomorphism. Then, $G:=(N\times H,*_{\alpha})$ with $$(a,x)*_{\alpha}(b,y):=(a\alpha_{x}(b),xy)$$is a group.

> [!proof]-
> We have that: 
> 1. $*_{\alpha}$ is well-defined as $a\alpha_{x}(b)\in N$ and $xy\in H$.
> 2. $*_{\alpha}$ is associative as: $$((a_{1},x_{1})*_{\alpha}(a_{2},x_{2}))*_{\alpha}(a_{3},x_{3})=(a_{1}\alpha_{x_{1}}(a_{2}),x_{1}x_{2})*_{\alpha}(a_{3},x_{3})=(a_{1}\alpha_{x_{1}}(a_{2})\alpha_{x_{1}x_{2}}(a_{3}),x_{1}x_{2}x_{3})$$and
> 	$$(a_{1},x_{1})*_{\alpha}((a_{2},x_{2})*_{\alpha}(a_{3},x_{3}))=(a_{1},x_{1})*_{\alpha}(a_{2}\alpha_{x_{2}}(a_{3}),x_{2}x_{3})=(a_{1}\alpha_{x_{1}}(a_{2}\alpha_{x_{2}}(a_{3})),x_{1}x_{2}x_{3})$$where $\alpha_{x_{1}}(a_{2})\alpha_{x_{1}x_{2}}(a_{3})=\alpha_{x_{1}}(a_{2})\alpha_{x_{1}}(\alpha_{x_{2}}(a_{3}))=\alpha_{x_{1}}(a_{2}\alpha_{x_{2}}(a_{3}))$.
> 3. $(e_{N},e_{H})$ is left-neutral.
> 	$$(e_{N},e_{H})*_{\alpha}(a,x)=(\iota(a),x)=(a,x)$$
> 4. $(\alpha_{x ^{-1}}(a^{-1}),x ^{-1})$ is left-inverse of $(a,x)$.$$(\alpha_{x ^{-1}}(a),x^{-1})*_{\alpha}(a,x)=(\alpha_{x^{-1}}(a^{-1})\alpha_{x ^{-1}}(a),x^{-1}x)=(\alpha_{x^{-1}}(a^{-1}a),e_{H})=(e_{N},e_{H})$$
---
> [!lemma] Fact 5
> If $N,H$ are groups and $G:= N \rtimes_{\alpha}H$, then for $N_{0}:=\{ (a,e_{H}):a\in N \}$ and $H_{0}:=\{ (e_{N},x): x\in H \}$: $$G \cong N_{0} \rtimes_{\kappa}H_{0}$$
---
> [!lemma] Lemma 6
> Let $N,H$ be groups and $\varphi,\psi:H\to \text{Aut}(N)$ be homomorphisms. Further, let $\alpha:H\to H$ be an automorphism s.t. $\varphi=\psi \circ\alpha$.  Then, $$N\rtimes_{\varphi}H\cong N\rtimes_{\psi}H$$

> [!proof]-
> Consider the isomorphism $$\begin{array}{cccc} {f:}&{N\rtimes_{\varphi}H}&\to&{N\rtimes_{\psi}H}\\&{(n,h)} &\mapsto & {(n,\alpha(h))} \end{array}{}$$Since $\alpha$ is a bijection, $f$ is a bijection. To show that $f$ is a homomorphism: 
> $$\begin{align}f((n_{1},h_{1})*_{\varphi} (n_{2},h_{2}))=f(n_{1}\varphi_{h_{1}}(n_{2}),h_{1}h_{2})=(n_{1}\varphi_{h_{2}}(n_{2}),\alpha(h_{1}h_{2}))\end{align}$$
> $$f(n_{1},h_{1})*_{\psi}f(n_{2},h_{2})=(n_{1},\alpha(h_{1}))*_{\psi}(n_{2},\alpha(h_{2}))=(n_{1}\psi_{\alpha(h_{1})}(n_{2}),\alpha(h_{1})\alpha(h_{2}))$$which proves the statement.
---
##### Examples
- We consider:
	1. $N:=\braket{ a   }\cong C_{7}$ and 
	2. $H := \braket{  x  }\cong C_{3}$
	   
  Then, $G:= N \rtimes_{\alpha}H$. Therefore, let's consider the homomorphisms $\alpha :H \to \text{Aut}(N)$. For $\psi\in \text{Aut}(N)$, as $N=\braket{ a }$, $\psi$ is defined through $\psi(a)$. Similarly, $\alpha$ is uniquely defined through $\alpha(x)$. 
  
  Let $\psi_{k}\in \text{Aut}(N)$ where $\psi_{k}(a)=a^k$. Then, we have:
  - $\text{ord}(\psi_{1})=1$
  - $\text{ord}(\psi_{2})=3$
  - $\text{ord}(\psi_{3})=6$
  - $\text{ord}(\psi_{4})=3$
  - $\text{ord}(\psi_{5})=6$
  - $\text{ord}(\psi_{6})=2$
    
  Therefore, the only possibilities for $\alpha$ are: 
  - $\alpha_{1}(x)=\psi_{1}$ with $G\cong C_{7} \times C_{3}\cong C_{21}$
  - $\alpha_2(x)=\psi_{2}$ and
  - $\alpha_4(x)=\psi_{4}$ are two non-abelian groups that are isomorphic to each other.
    
  This shows that there are only two groups of order $21$ up to isomorphism.
---
  
  
