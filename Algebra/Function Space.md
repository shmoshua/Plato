#Definition #LST 

> [!definition]
> Let $(V,F,\oplus_{V},\odot_{V})$ be a [[Vector Space|linear space]] and $D$ be any set. Further, let $\mathcal{F}(D,V)$ denote the set of functions of the form $f:D \to V$. A ***function space*** $(\mathcal{F}(D,V),F,\oplus,\odot)$ is defined as follows:
> - $(f\oplus g):D \to V$ s.t. $(f \oplus g)(d)=f(d) \oplus_{V} g(d)$ for all $d\in D$.
> - $(a \odot f):D \to V$ s.t. $(a \odot f)(d)= a\odot_{V} f(d)$ for all $d\in D$.
> 
> The identity element is $e:D\to V$ s.t. $e(d)=0$ for all $d\in D$ and the inverse element $(\ominus  f)(d) = -f(d)$ for all $d\in D$.
---
##### Examples
- $C([t_{0},t_{1}],\mathbb{R}^n)$ is the linear space of [[Continuous Functions|continuous functions]] $f:[t_{0},t_{1}]\to \mathbb{R}^n$.
- $C^1([t_{0},t_{1}],\mathbb{R}^n)$ is the linear space of [[Differentiable Functions|differentiable functions]] $f:[t_{0},t_{1}]\to \mathbb{R}^n$.
- $C^k([t_{0},t_{1}],\mathbb{R}^n)$ is the linear space of $k$-times [[Differentiable Functions|differentiable functions]] $f:[t_{0},t_{1}]\to \mathbb{R}^n$.
- $C^\infty([t_{0},t_{1}],\mathbb{R}^n)$ is the linear space of infinitely [[Differentiable Functions|differentiable functions]] $f:[t_{0},t_{1}]\to \mathbb{R}^n$.
- $C^\omega([t_{0},t_{1}],\mathbb{R}^n)$ is the linear space of [[Analytic Functions|analytic functions]] $f:[t_{0},t_{1}]\to \mathbb{R}^n$, i.e. functions which are infinitely differentiable and whose Taylor series expansion converges for all $t\in [t_{0},t_{1}]$.
---
