#Definition #RepresentationTheory 
> [!definition]
> For a [[quiver]] $Q:=(I,E)$, a ***(quiver) representation*** of $Q$ is a family $\{ V_{i} \}_{i\in I}$ and $\{ x_{h} \}_{h\in E}$ s.t. 
> 1. $V_{i}$ is assigned to each vertex $i\in I$.
> 2. a linear map $x_{h}:V_{h'}\to V_{h''}$ is assigned to each edge $h\in E$.
- **Related Definition**: A ***subrepresentation*** of a representation $(V_{i},x_{h})$ of $Q$ is a representation $(W_{i},x'_{h})$ where: $W_{i}\subseteq V_{i}$ for all $i\in I$ and $x_{h}'=x_{h}|_{W_{h'}}:W_{h'}\to W_{h''}$ for all $h\in E$.
- **Related Definition**: The ***direct sum*** of two representations $(V_{i},x_{h})$ and $(W_{i},y_{h})$ is the representation $(V_{i}\oplus W_{i},x_{h}\oplus y_{h})$.
-  **Related Definition**: For representations $(V_{i},x_{h})$ and $(W_{i},y_{h})$ of $Q$, a ***homomorphism*** $\varphi$ is a collection of maps $\varphi_{i}:V_{i}\to W_{i}$ s.t. $y_{h}\circ\varphi_{h'}=\varphi_{h''}\circ x_{h}$ for all $h\in E$.
---
##### Properties
> [!lemma] Theorem 1
> A quiver representation of $Q$ is equivalent to a representation of the [[path algebra]] $P_{Q}$.

> [!proof]-
> Let $V$ be a representation of the path algebra $P_{Q}$. We will construct a quiver representation as follows:
> 1. $V_{i}:=p_{i}V$ for all $i\in I$ and
> 2. $x_{h}=a_{h}|_{p_{h'}V}:p_{h'}V\to p_{h''}V$.
>  
>  Similarly, let $(V_{i},x_{h})$ be a representation of a quiver $Q$. From this representation, we can construct a representation of the path algebra $P_{Q}$: 
>  1. $V:=\bigoplus_{i\in I}V_{i}$
>  2. $p_{i}:V\to V_{i}$ be the projection onto $V_{i}$, 
> 
> and for any path $p=h_{1}\dots h_{m}$ let $a_{p}=x_{h_{1}}\dots x_{h_{m}}:V_{h'_{m}}\to V_{h''_{1}}$ be the composition of the operators corresponding to the edges occurring in $p$.
---
