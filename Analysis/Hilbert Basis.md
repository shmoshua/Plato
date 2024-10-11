#Definition #Analysis 

> [!definition]
> For a [[Separable Space|separable]] [[Hilbert space]] $\mathcal{H}$, an orthonormal system $\{ e_{k} \}_{k}$ is a ***Hilbert basis*** if the span is [[Dense Subset|dense]] in $\mathcal{H}$, i.e.$$\mathcal{H}=\overline{\text{Span} \{ e_{k} \}_{k}  }$$
---
##### Properties
> [!lemma] Theorem 1 (Completeness Criterion)
> Let $\mathcal{H}$ be a [[Separable Space|separable]] [[Hilbert space]] and $\{ e_{k} \}_{k}$ an orthonormal system. Then, the following are equivalent:
> 1. $\{ e_{k} \}_{k}$ is a Hilbert basis.
> 2. for all $x\in \mathcal{H}$, $$x=\sum_{k=0}^{\infty}\braket{ x , e_{k} } e_{k}$$
> 3. for all $x\in \mathcal{H}$, if $\braket{ x , e_{k} }=0$ for all $k\in \mathbb{N}$, then $x=0$.

> [!proof]-
> We have:
> - (1=>2): Since $\text{Span}\{ e_{k} \}_{k}$ is dense, for every $x\in \mathcal{H}$ and $\varepsilon>0$, there exists $n\in\mathbb{N}$ and $a_{1},\dots,a_{n}\in\mathbb{C}$ s.t. $$\left\| x-\sum_{k=0}^{n}a_{k}e_{k} \right\|^{2} <\varepsilon$$Thus, with $S_{n}(x):=\sum_{k=0}^{n}\braket{ x , e_{k} }e_{k}$, $$\begin{align}\varepsilon&>\left\| x-\sum_{k=0}^{n}a_{k}e_{k} \right\|^{2}\\&=\left\| x-S_{n}(x) \right\| ^{2}+\left\| S_{n}(x)-\sum_{k=0}^{n} a_{k}e_{k}\right\|^{2}+2\text{Re}\left\langle x-S_{n}(x) , S_{n}(x)-\sum_{k=0}^{n}a_{k}e_{k} \right\rangle  \\&=\left\| x-S_{n}(x) \right\| ^{2}+\left\| S_{n}(x)-\sum_{k=0}^{n} a_{k}e_{k}\right\|^{2}\\&\geq \left\| x-S_{n}(x) \right\| ^{2}\end{align}$$Therefore, $S_{n}(x)\to x$.
> - (2=>1): As $S_{n}(x)\to x$, we have for every $\varepsilon>0$, $$\left\| x-S_{n}(x) \right\| <\varepsilon$$for some $n\in \mathbb{N}$ large enough. 
> - (2=>3): If $\braket{ x , e_{k} }=0$ for all $k\in \mathbb{N}$, $$x=\sum_{k=0}^{\infty}\braket{ x , e_{k} } e_{k}=0$$
> - (3=>2): For any $x\in \mathcal{H}$, $$\braket{ x-S_{n}(x) , e_{j} } =\braket{ x , e_{j} } -\sum_{k=0}^{n}\braket{ x , e_{k} } \delta_{jk}=0$$Therefore, by the continuity of inner product, $\braket{ x-\sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k} , e_{j} }=0$ for all $j\in \mathbb{N}$ and $$x=\sum_{k=0}^{\infty}\braket{ x , e_{k} } e_{k}$$
---
> [!lemma] Theorem 2 (Existence of a Basis)
> A [[Hilbert space]] admits a Hilbert basis $\{ e_{k} \}_{k}$ if and only if it is [[Separable Space|separable]].

> [!proof]-
> Let $\{ e_{k} \}_{k}$ be a Hilbert basis. Then, $$\mathcal{D}:=\left\{  \sum_{k=0}^{n}q_{k}e_{k}:n\in \mathbb{N},q_{k}\in \mathbb{Q}+i\mathbb{Q}  \right\}$$is a countable dense subset of $\mathcal{H}$.
> 
> Conversely, suppose there exists a countably dense subset $\mathcal{D}:=\{ v_{k} \}_{k}$ of $\mathcal{H}$. Then let 
> 1. $e_{0}:=v_{j_{0}} / \|v_{j_{0}}\|$ where $v_{j_{0}}$ is the first non-zero vector in $\mathcal{D}$.
> 2. for every $k\geq 0$, $j_{k+1}:=\min\{ j:v_{j}\text{ is linearly independent to }\{ v_{0},\dots,v_{j_{k}} \} \}$. Then, $$e'_{k+1}:=v_{j_{k+1}}-\sum_{p=0}^{k}\braket{ v_{j_{k+1}} , e_{p} } e_{p}, \quad e_{k+1}:= \frac{e'_{k+1}}{\|e'_{k+1}\|}$$
> 
> Then, $\{ e_{k} \}_{k}$ is an orthonormal system with a dense span as the span contains $\mathcal{D}$.
---
> [!lemma] Theorem 3
> Let $\mathcal{H}$ be a  [[Separable Space|separable]] [[Hilbert space]] with orthonormal basis $\{ e_{k} \}_{k}$. Then, $\mathcal{H}$ is isometric to $\ell^2(\mathbb{N},\mathbb{C})$, i.e. there exists a linear isometric isomorphism $J:\mathcal{H}\to \ell^{2}(\mathbb{N},\mathbb{C})$ s.t. $$\braket{ x , y } _{\mathcal{H}}=\braket{ Tx , Ty } _{\ell^2(\mathbb{N})},\quad \forall x,y\in \mathcal{H}$$

> [!proof]-
> We define: $$\begin{array}{cccc} {J:}&{\text{Span}\{ e_{k} \}_{k}}&\to&{\ell^{2}(\mathbb{N})}\\&{\sum_{k=0}^{n}x_{k}e_{k}} &\mapsto & {\sum_{k=0}^{n}x_{k}\delta_{k}} \end{array}{}$$Then, it is a linear isometry on $\text{Span}\{ e_{k} \}_{k}$. Therefore, $J$ is a bounded linear operator and by [[Bounded Linear Map|BLT theorem]], we can uniquely extend it to a linear isometry $\overline{J}:\mathcal{H}\to \ell^2(\mathbb{N,C})$.
> 
> We are left to show that $\overline{J}$ is an isomorphism. As it preserves the distance, it is injective. To show that it is surjective, for $y\in \ell^2(\mathbb{N})$, $x:=\sum_{k\in \mathbb{N}}^{}y(k)e_{k}\in \mathcal{H}$ as: $$\|x\|^{2}_{\mathcal{H}}=\left\| \sum_{k\in \mathbb{N}}^{}y(k)e_{k} \right\|^{2}_{\mathcal{H}}=\sum_{k\in \mathbb{N}}^{}\left| y_{k} \right|^{2}=\|y\|^2_{\ell^2(\mathbb{N})}<+\infty  $$Therefore, $\overline{J}x=y$.
---
> [!lemma] Theorem 4 (Basis of Product Hilbert Spaces)
> Let $\{ e_{i} \}_{i}$ be a Hilbert basis of $L^2(X,\mu)$. Then, for $$E_{ij}:X\times X\to \mathbb{K}, \quad (x,y)\mapsto \overline{e_{i}(x)}{e_{j}(y)}$$
> 1. $E_{ij}\in L^2(X\times X,\mu \otimes \mu)$ and
> 2. $\{ E_{ij} \}_{i,j}$ forms a Hilbert basis of $L^2(X\times X,\mu \otimes \mu)$.

> [!proof]-
> We have that:
> 1. Notice that: $$\left\| E_{ij} \right\| _{L^2(X\times X)}^2=\int_{X}^{} \int_{X}^{} (\overline{e_{i}(y)}e_{j}(x) )^{2}\, d\mu(x)  \, d\mu(y)= \left\| e_{i} \right\| ^2\left\| e_{j} \right\| ^2$$
> 2. Firstly, we show that they are orthonormal: $$\begin{align}\braket{ E_{ij} , E_{pq} }&=\int_{X\times X}^{} \overline{e_{i}(y)}e_{j}(x)\overline{e_{q}(x)}e_{p}(y) \, d\mu \times \mu  \\&=\left( \int_{X}^{} e_{j}(x)\overline{e_{q}(x)} \, d\mu(x) \right)\left( \int_{X}^{} e_{p}(y)\overline{e_{i}(y)} \, d\mu(x) \right)\\&=\braket{ e_{j} , e_{q} } \braket{ e_{p} , e_{i} }\\&=\delta_{jq}\delta_{ip}  \end{align}$$Therefore, we only need to check that they form a basis. Assume $h\in L^2(X\times X)$ s.t. $\braket{ h , E_{ij} }=0$ for all $i,j$. Then, $$\begin{align}0=\int_{X\times X}h(x,y)e_{i}(y)\overline{e_{j}(x)} \, d\mu \times \mu &=\int_{X}^{} \left( \int_{X}^{} h_{x}(y)e_{i}(y) \, d\mu(y)  \right) \overline{e_{j}(x)} \, d\mu(x) \\&=\left\langle{ x\mapsto\int_{X}h_{x}e_{i}  \, d\mu(y)  , e_{j} }\right\rangle \end{align}$$Therefore, $\int_{X}h_{x}e_{i}  \, d\mu(y)=0$ for a.e. $x$. Let $$E_{i}:=\left\{  x\in X:\int_{X}^{} h_{x}e_{i}d\mu(y) \neq 0 \right\}$$Then $\mu(E_{i})=0$ and for $E:=\bigcup_{i=1}^{\infty}E_{i}$, $\mu(E)\leq \sum_{i=1}^{\infty}\mu(E_{i})=0$. Therefore, for each $x\in X \backslash E$, $h(x,y)=0$ $\mu \times \mu$.a.e. This means that: $$\begin{align}\int_{X\times X}^{} \left| h(x,y) \right| ^{2} \, d\mu \times \mu&=\int_{X}^{} \left( \int_{X}^{} \left| h(x,y) \right| ^{2} \, d\mu(y)  \right)  \, d\mu(x) \\&=\int_{X \backslash E}^{} \left( \int_{X}^{} \left| h(x,y) \right| ^{2} \, d\mu(y)  \right)  \, d\mu(x) \\&=0\end{align}$$This proves that $h=0$ in $L^2(X\times X)$.

---
##### Examples
> [!h] Example 1
> Consider $\ell^2(\mathbb{N},\mathbb{C})$. Then, 
> 1. $\{ \delta_{n} \}_{n}\subseteq \ell^2(\mathbb{N})$ forms a Hilbert basis where $\delta_{n}(m)=\delta_{nm}$. 
> 2. $c_{00}(\mathbb{N})\subseteq \ell^2(\mathbb{N})$ is a proper dense subset and therefore not a Hilbert space.

> [!proof]-
> We have that: 
> $$\braket{ \delta_{n} , \delta_{m} } =\sum_{k=0}^{\infty}\delta_{n}(k)\delta_{m}(k)=\delta_{nm}$$Furthermore, if for $f\in \ell^2(\mathbb{N})$ and $n\in \mathbb{N}$: $$\braket{ f , \delta_{n} }=\sum_{k=0}^{\infty}f(k)\delta_{nk}=f(n)=0$$Then, $f=0$. Therefore, by theorem 1, $\{ \delta_{n} \}_{n}$ is a Hilbert basis.
> 
> Furthermore, we have that: $c_{00}(\mathbb{N})=\text{Span}\{ \delta_{n} \}_{n}$.
---
> [!h] Example 2 (Fourier Basis)
> For every $k\in \mathbb{Z}$, define $e_{k}\in L^2((-\pi,\pi),\mathbb{C})$ as: $$e_{k}(x):= \frac{1}{\sqrt{ 2\pi }}e^{ikx}$$Then, $\mathcal{F}:=\{ e_{k}: k\in \mathbb{Z} \}$ is a Hilbert basis for $L^2((-\pi,\pi),\mathbb{C})$.