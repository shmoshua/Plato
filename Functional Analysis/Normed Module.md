#Definition #Algebra 

> [!definition]
> Let $A$ be a [[Seminorm|normed ring]]. 
> 1. A ***seminormed $A$-module*** is a $A$-[[module]] $M$ with a [[Seminorm|seminorm]] s.t. there exists $c>0$ s.t. $$\|am\|\leq c\left| a \right| \|m\|,\quad \forall a\in A,m\in M$$
> 2. A ***normed $A$-module*** is a $A$-[[module]] $M$ with a [[Seminorm|norm]] s.t. there exists $c>0$ s.t. $$\|am\|\leq c\left| a \right| \|m\|,\quad \forall a\in A,m\in M$$
- **Related definition**: A normed $A$-module is ***Banach*** if it is [[Complete Metric Space|complete]].
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be a seminormed/normed $A$-module. Then, 
> 1. there exists another seminorm/norm $\|\cdot\|'_{M}$ on $M$ equivalent to $\|\cdot\|_{M}$ s.t.$$\|am\|'_{M}\leq \left| a \right| \|m\|'_{M} $$  

> [!proof]+
> Let's define the new seminorm as: $$\|m\|'_{M}:=\sup_{\left| a \right| \leq 1}\|am\|_{M}$$Then, we show that this is a seminorm. 
> 1. $\|bm\|'_{M}:=\sup_{\left| a \right|\leq 1}\|abm\|_{M}\leq \sup_{\left| a \right|\leq 1}\left| ab \right|\|m\|_{M}\leq \left| b \right|\|m\|_{M}\leq \left| b \right|\|m\|'_{M}$.
> 2. $\|m+n\|'_{M}=\sup_{\left| a \right|\leq 1}\|am+an\|_{M}\leq\sup_{\left| a \right|\leq 1}\|am\|_{M}+\sup_{\left| a \right|\leq 1}\|an\|_{M}=\|m\|'_{M}+\|n\|'_{M}$.
> 
> Further, if $\|\cdot\|_{M}$ is a norm, then 