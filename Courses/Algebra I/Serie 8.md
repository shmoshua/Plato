#Series #Algebra-I 

##### Exercise 45
1. For $n\geq 5$, assume that we have a non-trivial normal subgroup $N\unlhd S_{n}$ s.t. $N\neq A_{n}$. Consider $N \cap A_{n}\unlhd A_{n}$. As $A_{n}$ is simple for $n\geq 5$, $N \cap A_{n}=\{ \iota \}$. As $N$ is non-trivial, we conclude that $N=\{ \iota, \pi \}$ where $\pi$ is odd and $\pi^{2}=\iota$. Now, as $N$ is normal, if $\sigma \pi\sigma ^{-1}=\iota$ for some $\sigma\in S_{n}$, then $\pi=\iota$, which is a contradiction. Therefore, for all $\sigma\in S_{n}$, $\sigma \pi \sigma^{-1}=\pi$, then $\sigma \pi=\pi\sigma$ and $\pi\in Z(S_{n})$. However, as $\pi\neq \iota$, there exists $i\in[n]$ s.t. $\pi(i)\neq i$. Then, there exists $j\in[n]$ s.t. $\pi(i)\neq j\neq i$. It follows that:
	$$(\pi(i,j))(\pi(i))=\pi^2(i)=i \neq j=(i,j)(i)=((i,j)\pi)(\pi(i))$$
    This is a contradiction and $A_{n}$ is the only non-trivial normal subgroup of $S_{n}$.
2. We firstly have that $S_{n}$ for $n\geq 5$ is not abelian. However, the only non-trivial subgroup of $S_{n}$ is $A_{n}$. However, $A_{n}$ is also non-abelian and simple. This shows that $S_{n}$ cannot be solvable.
---
##### Exercise 46
Let's consider $H=\braket{ x }\cong C_{2}$, $N=\braket{  a }\cong C_{p}$ and the outer semi-direct product $G=N\rtimes_{\alpha}H$, where $\alpha:H \to \text{Aut}(N)$ is a homomorphism uniquely determined by $\alpha(x)$. As $\left| \text{Aut}(N) \right|=p-1$ and $2|p-1$, by Cauchy's theorem, there exists an automorphism $\pi:N \to N$ of order 2. Notice that if $\pi(a)=a^k$, $\pi(a^k)=\pi(a)^k=a^{k^2}=a$. Therefore, $\pi(a)=a^{p-1}$. Now, let $\alpha(x)=\pi$. Then, 
1. $(e,x)*_{\alpha}(e,x)=(e\alpha_{x}(e),e)=(e,e)$
2. $(a^{k},e)*_{\alpha}(a,e)=(a^k\alpha_{e}(a),e)=(a^{k+1},e)$. Therefore, $(a,e)^p=(e,e)$.
3. $(a^{p-1},e)*_{\alpha}(e,x)=(a^{p-1}\alpha_{e}(e),x)=(a^{p-1},x)$ and $(e,x)*_{\alpha}(a,e)=(\pi(a),x)=(a^{p-1},x)$

Therefore, $N \rtimes_{\alpha}H\cong D_{p}$. If we choose $\alpha(x)=\iota$ instead, then $N \rtimes_{\alpha}H=N\times H\cong C_{p}\times C_{2}\cong C_{2p}$.

---
##### Exercise 47
1. Consider the following homomorphism: $$\begin{array}{cccc} {\psi:}&{N\rtimes_{\varphi}H}&\to&{N\rtimes_{\varphi'}H}\\&{(x,h)} &\mapsto & {(\alpha (x),h)} \end{array}{}$$Then, $$\psi((x_{1},h_{1})*_{\varphi}(x_{2},h_{2}))=\psi(x_{1}\varphi_{h_{1}}(x_{2}),h_{1}h_{2})=(\alpha(x_{1}\varphi_{h_{1}}(x_{2})),h_{1}h_{2})$$
   $$\psi(x_{1},h_{1})*_{\varphi'}\psi(x_{2},h_{2})=(\alpha(x_{1})\varphi_{h_{1}}'(\alpha(x_{2})),h_{1}h_{2})=(\alpha(x_{1})\alpha(\varphi_{h_{1}}(x_{2})),h_{1}h_{2})=(\alpha(x_{1}\varphi_{h_{1}}(x_{2})),h_{1}h_{2})$$
    and $\psi$ is a homomorphism. Further, as $\alpha$ is an automorphism, $\psi$ is surjective. Moreover, $$\text{ker}(\psi)=\{ (x,h):(\alpha(x),h)=(e_{N},e_{H})\}=\{ (e_{N},e_{H}) \}$$
    Therefore, $$N\rtimes_{\varphi}H\cong N\rtimes_{\varphi'}H$$
2. Consider the following homomorphism: $$\begin{array}{cccc} {\psi:}&{N\rtimes_{\varphi}H}&\to&{N\rtimes_{\varphi'}H}\\&{(x,h)} &\mapsto & {(x,\beta(h))} \end{array}{}$$Then, 
	$$\psi((x_{1},h_{1})*_{\varphi}(x_{2},h_{2}))=\psi(x_{1}\varphi_{h_{1}}(x_{2}),h_{1}h_{2})=(x_{1}\varphi_{h_{1}}(x_{2}),\beta(h_{1}h_{2}))$$
	$$\psi(x_{1},h_{1})*_{\varphi'}\psi(x_{2},h_{2})=(x_{1},\beta(h_{1}))*_{\varphi'}(x_{2},\beta(h_{2}))=(x_{1}\varphi_{\beta(h_{1})}'(x_{2}),\beta(h_{1}h_{2}))=(x_{1}\varphi_{h_{1}}(x_{2}),\beta(h_{1}h_{2}))$$
    and $\psi$ is a homomorphism. Further, as $\beta$ is an automorphism, $\psi$ is surjective. Moreover, $$\text{ker}(\psi)=\{ (x,h):(x,\beta(h))=(e_{N},e_{H})\}=\{ (e_{N},e_{H}) \}$$
    Therefore, $$N\rtimes_{\varphi}H\cong N\rtimes_{\varphi'}H$$
---
##### Exercise 48
Let $|G|=28$. We first show that $G$ is not simple. We have $28=2^{2}\cdot 7$. Then, $\left| \text{Syl}_{7}(G) \right|=1$ and there always exists a $N\unlhd G$ with $\left| N \right|=7$. Therefore, $G=N \rtimes_{\kappa}H$ where $\left| H \right|=4$. We will consider the two cases:
1. $H\cong C_{4}$: Then, $G \cong C_{7}\rtimes_{\alpha}C_{4}$ where $\alpha:C_{4}\to \text{Aut}(C_{7})$ where $\text{Aut}(C_{7})\cong C_{6}$ with generator $\pi$. Therefore, there are two homomorphisms: 
	- $\alpha(x)=\iota$. Then, $G\cong C_{7}\rtimes_{\alpha }C_{4}=C_{7}\times C_{4}\cong C_{28}$
	- $\alpha(x)=\pi^3$. Then, $G\cong C_{7}\rtimes_{\alpha }C_{4}$
2. $H\cong C_{2}\times C_{2}$: Then, $G \cong C_{7}\rtimes_{\alpha}(C_{2}\times C_{2})$ where $\alpha:C_{2}\times C_{2}\to \text{Aut}(C_{7})\cong C_{6}$. Therefore, there are four homomorphisms: 
     For $C_{2}\times C_{2} =\{ e,a,b,ab \}$
	- $\alpha_{}(x)=\iota$. Then, $G\cong C_{7}\times C_{2}\times C_{2}\cong C_{14}\times C_{2}$
	- $\alpha(a)=\alpha(b)=\pi^3$, $\alpha(ab)=\iota$
	- $\alpha(a)=\alpha(ab)=\pi^3$, $\alpha(b)=\iota$
	- $\alpha(b)=\alpha(ab)=\pi^3$, $\alpha(a)=\iota$
  
   Notice that for the non-trivial homomorphisms $\alpha,\alpha'$, there exists an automorphism $\beta:C_{2}\times C_{2} \to C_{2}\times C_{2}$  s.t. $\alpha=\alpha'\circ \beta$ (switching the one element that gets maps to $\iota$). Therefore, by Exercise 47, the semi-direct products are isomorphic to each other. Therefore, we only have $G\cong C_{7}\rtimes_{\alpha}(C_{2}\times C_{2})$.  
---