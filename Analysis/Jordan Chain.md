#Definition #Analysis #LST 

> [!definition] 
> A ***Jordan chain*** of length $\mu\in \mathbb{N}$ at [[Eigenvalues and Eigenvectors|eigenvalue]] $\lambda\in \mathbb{C}$ is a family of vectors $\{ v^j \}_{j=1}^\mu \subseteq \mathbb{C}^n$ s.t. 
> 1. $\{ v^j \}_{j=1}^\mu$ are [[Linear Independence|linearly independent]], and
> 2. $[A-\lambda I]v^1=0$ and $[A-\lambda I]v^j=v^{j-1}$ for all $j=2,\dots,\mu$.
> 
> A Jordan chain $\{ v_{j} \}_{j=1}^\mu$ is ***maximal*** if it cannot be extended. The elements of all the maximal Jordan chains at $\lambda$ are the ***generalized eigenvectors of $\lambda$.***
---
> [!definition]
> We can define a matrix with the generalized eigenvectors: $$T:=[v^1_{1}|\dots|v^{\mu_{1}}_{1}|\dots|v_{k}^1|\dots|v^{\mu_{k}}_{k}]^{-1}\in \mathbb{C}^{n,n}$$Then, $A=T^{-1}JT$ where $J\in \mathbb{C}^{n,n}$ is a block diagonal $J=\text{diag}(J_{1},J_{2},\dots,J_{k})$ with: $$J_{i}=\begin{bmatrix}\lambda_{i}&1&\cdots&0&0\\0&\lambda_{i}&\ddots&0&0\\\vdots&\vdots&\ddots&\ddots&\vdots\\0&0&\cdots&\lambda_{i}&1\\0&0&\cdots&0&\lambda_{i}\end{bmatrix}\in \mathbb{C}^{\mu_{i},\mu_{i}}$$
> for $i\in[k]$, where $\lambda_{i}\in \mathbb{C}$ is the eigenvalue corresponding to the Jordan chain $\{ v^j_{i} \}_{j=1}^{\mu_{i}}$. $J$ is then called the ***Jordan canonical form*** of $A$ and $\{ J_{i} \}_{i}$ are called the ***Jordan blocks***.
---
##### Properties
> [!lemma] Fact 1
> Let $\{ v_{j} \}_{j=1}^\mu$ be a Jordan chain at $\lambda\in \mathbb{C}$ of $A\in \mathbb{R}^{n,n}$. Then:
> 1. $v^1$ is an eigenvector with eigenvalue $\lambda$.
> 2. $v^j\in \text{ker}[(A-\lambda I)^j]$ for $j=1,\dots,\mu$

> [!proof]-
> We have that: 
> 1. $Av^1=\lambda v^1$ by definition.
> 2. $(A-\lambda I)^jv^j=(A-\lambda I)^{j-1}v^{j-1}=\dots=(A-\lambda I)v^1=0$
---
> [!lemma] Lemma 2
> Assume that a matrix $A$ has $k$ linearly independent eigenvectors $v_{1},\dots,v_{k}\in \mathbb{C}^n$ with corresponding maximal Jordan chains $\{ v^j_{i} \}_{j=1}^{\mu_{i}}$ for $i\in[k]$. Then, $\bigcup_{i=1}^{^k}\{ v_{i}^j \}_{j=1}^{\mu_{i}}$ are linearly independent and $\sum_{i=1}^{k}\mu_{i}=n$.
---
> [!lemma] Theorem 3
> For a matrix $A$ and its Jordan form $A=T^{-1}JT$, $$e^{ At }=T^{-1}e^{ Jt }T$$

>[!proof]-
>Firstly, we have $A^n=T^{-1}J^{n-1}TT^{-1}JT=T^{-1}J^nT$. Then, $$e^{ At }=T^{-1}e^{ Jt }T$$where $e^{ Jt }=\text{diag}(e^{ J_{1}t },\dots,e^{ J_{k}t })$ and:$$e^{ J_{i}t }=\begin{bmatrix}e^{ \lambda_{i}t }&te^{ \lambda_{i}t}&\cdots& \frac{t^{\mu_{i}-2}}{(\mu_{i}-2)!}e^{ \lambda_{i}t}&\frac{t^{\mu_{i}-1}}{(\mu_{i}-1)!}e^{ \lambda_{i}t} \\0&e^{ \lambda_{i}t}&\ddots&\frac{t^{\mu_{i}-3}}{(\mu_{i}-3)!}e^{ \lambda_{i}t}&\frac{t^{\mu_{i}-2}}{(\mu_{i}-2)!}e^{ \lambda_{i}t}\\\vdots&\vdots&\ddots&\ddots&\vdots\\0&0&\cdots&e^{ \lambda_{i}t}&te^{ \lambda_{i}t}\\0&0&\cdots&0&e^{ \lambda_{i}t}\end{bmatrix}$$
---