#Definition #AlgebraicTopology 

> [!definition]
> A ***diagonal approximation*** $\Delta$ is a collection is a collection of [[chain complex|chain maps]] of the form: $$\Delta:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X)$$for all [[topological space]] $X$ s.t.
> 1. $\Delta$ is natural w.r.t. continuous maps $f:X\to Y$, i.e. $\Delta_{Y}\circ f_{c}=(f_{c}\otimes f_{c})\circ\Delta_{X}$
> 2. on degree 0, $\Delta(x)=x\otimes x$ for all $x\in S_{0}(X)$.

---
##### Properties
> [!lemma] Theorem 1 (Uniqueness of Diagonal Approximation Up to Chain Homotopy)
> Let $\Delta,\Delta'$ be two diagonal approximations. Then, 
> 1. $\Delta \sim \Delta'$, i.e. they are [[Chain Homotopy|chain homotopic]] via a chain homotopy natural w.r.t $f:X\to Y$.

> [!proof]-
> We want to show that there exists a chain homotopy: $$D:\mathcal{S}_{*}(X)\to (\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X))[1]$$that is natural w.r.t. $f:X\to Y$ s.t. $\partial_{\otimes}D+D\partial=\Delta-\Delta'$. 
> 
> We will show that using induction over $n$. 
> 1. If $n=0$, setting $D=0$ suffices as $\Delta(x)=\Delta'(x)$ for all $x\in S_{0}(X)$.
> 2. If $n\geq 1$, assume that $D$ is defined for all $0\leq p<n$ and topological spaces $X$ s.t. it is natural w.r.t. $f:X\to Y$ and $\partial_{\otimes}D+D\partial=\Delta-\Delta'$. 
>    
>    Let $d_{n}:\Delta^n\to \Delta^n,x\mapsto x$ be the identity. Then, we claim that $(\Delta-\Delta'-D\partial)(d_{n})\in (\mathcal{S}_{}(X)\otimes \mathcal{S}(X))_{n}$ is a chain. We have that: $$\partial_{\otimes }(\Delta-\Delta'-D\partial)(d_{n})=(\Delta \partial-\Delta'\partial+\Delta'\partial-\Delta \partial+D\partial^{2})(d_{n})=0$$Further, as from [[Singular Homology|Lemma 8]], $H_{n}(\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X))=0$, we have that there exists $a_{n}\in (\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X))_{n+1}$ s.t. $\partial_{\otimes}a_{n}=(\Delta-\Delta'-D\partial)(d_{n})$. Let $D(d_{n}):=a_{n}$. Clearly, $$\partial_{\otimes }D(d_{n})=\partial_{\otimes }a_{n}=(\Delta-\Delta'-D\partial)(d_{n})$$Now, for $\sigma\in S_{n}(X)$, we define: $$D(\sigma):=(\sigma_{c}\otimes  \sigma_{c})D(d_{n})$$Then, $D$ is well-defined and for any $f:X\to Y$:$$D(f_{c}(\sigma))=((f\circ  \sigma)_{c}\otimes  (f\circ  \sigma)_{c})D(d_{n})=(f_{c}\otimes  f_{c})(\sigma_{c}\otimes  \sigma_{c})D(d_{n})=(f_{c}\otimes  f_{c})D(\sigma)$$Lastly, $$\begin{aligned}\partial D(\sigma)&=\partial(\sigma_{c}\otimes  \sigma_{c})D(d_{n})=(\sigma_{c}\otimes  \sigma_{c})\partial D(d_{n})\\&=(\sigma_{c}\otimes  \sigma_{c})(\Delta-\Delta'-D\partial)(d_{n})\\&=(\Delta-\Delta'-D\partial)(\sigma \circ  d_{n})=(\Delta-\Delta'-D\partial)(\sigma)\end{aligned}$$
- **Corollary**: For any two cocycles $\varphi\in S^p(X),\psi\in S^q(X)$, for any diagonal approximation $\Delta$ and $\Delta_{\Theta}$ from Example 1, $$[(\varphi \otimes \psi)\circ  \Delta]=[(\varphi \otimes \psi)\circ  \Delta_{\Theta}]=[(\varphi \times \psi)\circ  d_{c}]=[\varphi \cup \psi]=[\varphi]\cup[\psi]$$
---
##### Examples
> [!h] Example 1 (Via Theta)
> Let $\Theta:\mathcal{S}_{*}(X\times X)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X)$ be a chosen map from [[Singular Homology|Eilenberg-Zilberg]]. Then, $$\Delta:\mathcal{S}_{*}(X)\overset{ d_{c} }{ \to } \mathcal{S}_{*}(X\times X)\overset{ \Theta }{ \to } \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X)$$for $d:X\to X\times X,x\mapsto (x,x)$ is a diagonal approximation.

> [!proof]-
> We have that:
> 1. $\Delta$ is a chain map as $\Theta$ is a chain map.
> 2. Naturality follows that of $\Theta$.
> 3. On degree $0$, $\Delta(x)=\Theta \circ d_{c}(x)=\Theta(x,x)=x\otimes x$.

---
> [!h] Example 2 (Alexander-Whitney Diagonal Approximation)
> Let $\sigma:\Delta^n\to X$. For $0\leq p\leq n$, we define: $$\begin{aligned}\sigma\rfloor_{p}:\Delta^p\to X,\quad [v_{0}:\dots:v_{p}]\mapsto \sigma([v_{0}:\dots:v_{p}:0:\dots:0])\\{_{q}\lfloor \sigma}:\Delta^q\to X,\quad [v_{0}:\dots:v_{q}]\mapsto \sigma([0:\dots:0:v_{0}:\dots:v_{q}])\end{aligned}$$
> Then, it holds that for $F^k:=[e_{1},\dots,\widehat{e_{k}},\dots,e_{n}]:\Delta^n\to \Delta^{n-1}$:
> 1. for $p+q=n$:$$F^k(\sigma\rfloor_{p})=\begin{cases}(F^k\sigma)\rfloor_{p-1}&0\leq k\leq p,1\leq p\\0&k=0,p=0\end{cases},\quad F^k({_{q}\lfloor \sigma})=\begin{cases}{_{q-1}\lfloor (F^{k+p}\sigma)}&0\leq k\leq q,1\leq q\\0&k=0,q=0\end{cases}$$
> 2. for $s+t=n-1$ and $0\leq k\leq n$:$$(F^k\sigma)\rfloor_{s}=\begin{cases}\sigma\rfloor_{s}&0\leq s\leq k-1\\F^k(\sigma\rfloor_{s+1})&k\leq s\end{cases},\quad {_{t}\lfloor (F^{k}\sigma)}=\begin{cases}{_{t}\lfloor \sigma}&t\leq  n-1-k\\ F^{k-s}({_{t+1}\lfloor \sigma})&n-k\leq t\end{cases}$$
> 
> the ***Alexander-Whitney diagonal approximation*** is given by: $$\Delta^{\text{AW}}(\sigma):=\sum_{p+q=n} \sigma\rfloor_{p}\otimes{_{q}\lfloor \sigma }\in(\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X))_{n} $$

> [!proof]+
> We have that:
> 1. If $0\leq k\leq p, 1\leq p$ then: $$\begin{aligned}F^k(\sigma\rfloor_{p})([v_{0}:\dots:v_{p-1}])&=\sigma\rfloor_{p}([v_{0}:\dots:v_{k-1}:0:v_{k}:\dots:v_{p-1}])\\&=\sigma([v_{0}:\dots:v_{k-1}:0:v_{k}:\dots:v_{p-1}:0:\dots:0])\\&=F^k\sigma([v_{0}:\dots:v_{p-1}:0:\dots:0])\\&=(F^k\sigma)\rfloor_{p-1}[v_{0}:\dots:v_{p-1}]\end{aligned}$$Otherwise, we have: $\begin{aligned}F^0(\sigma\rfloor_{0})=0\end{aligned}$. Similarly, if $0\leq k\leq q,1\leq q$: $$\begin{aligned}F^k({_{q}\lfloor \sigma})([v_{0}:\dots:v_{p-1}])&={_{q}\lfloor\sigma}([v_{0}:\dots:v_{k-1}:0:v_{k}:\dots:v_{q-1}])\\&={\sigma}([0:\dots:0:v_{0}:\dots:v_{k-1}:0:v_{k}:\dots:v_{q-1}])\\&=F^{p+k}\sigma([0:\dots:0:v_{0}:\dots:v_{q-1}])\\&={_{q-1}\lfloor (F^{p+k}\sigma)}[v_{0}:\dots:v_{p-1}]\end{aligned}$$and $F^0({_{q}\lfloor \sigma})=0$ otherwise.
> 2. If $0\leq s\leq k-1$, then: $$\begin{aligned}(F^k\sigma)\rfloor_{s}[v_{0}:\dots:v_{s}]&=F^k\sigma[v]\end{aligned}$$