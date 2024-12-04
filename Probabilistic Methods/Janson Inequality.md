#Definition 

> [!definition]
> Let $R\in \{ 0,1 \}^N$ a random subset with $\mathbb{P}(R_{i}=1)=p_{i}$ independently. Further, let $S_{1},\dots,S_{k}\in \{ 0,1 \}^N$.
> 1. $A_{i}$ denotes the event that $S_{i}\subseteq R$, i.e. $S_{i}\leq R$.
> 2. $X:=\sum_{i\in[k]}^{}\mathbb{1}_{A_{i}}$
> 3. $\mu:=\mathbb{E}\left[ \sum_{i\in[k]}^{}\mathbb{1}_{A_{i}} \right]=\sum_{i\in[k]}^{}\mathbb{P}(S_{i}\subseteq R)$
> 4. $\Delta:=\sum_{(i,j):i \sim j}^{}\mathbb{P}(A_{i}\cap A_{j})=\sum_{(i,j):i \sim j}^{}\mathbb{P}(S_{i}\cup S_{j}\subseteq R)$ where $i\sim j$ iff $i\neq j$ and $S_{i}\cap S_{j}\neq \varnothing$. 
---
##### Properties
> [!lemma] Theorem 1 (Janson Inequality)
> We have that:
> 1. $\mathbb{P}(X=0)\leq \exp \left( -\mu+\frac{\Delta}{2} \right)$
> 2. $\mathbb{P}(X=0)\leq \exp \left( -\frac{\mu^2}{2\Delta} \right)$ if $\Delta\geq \mu$.

> [!proof]-
> We have that: 
> 1. Notice that:$$\begin{align}\mathbb{P}(X=0)&=\mathbb{P}\left( \bigcap_{i\in[k]}^{}A_{i}^c \right)=\mathbb{P}(A_{1}^c)\mathbb{P}(A^c_{2}|A_{1}^c)\dots \mathbb{P}(A_{k}^c|A_{1}^c,\dots,A_{k-1}^c)\end{align}$$For $r_{i}:=\mathbb{P}(A_{i}|A_{i-1}^c,...,A_{1}^c)$, we have that $\mathbb{P}(X=0)=\prod_{i=1}^{k}(1-r_{i})\leq \exp \left( -\sum_{i=1}^{k}r_{i} \right)$. Therefore, it suffices to show that $\sum_{i=1}^{k}r_{i}\geq \mu-\frac{\Delta}{2}$. We claim that $$r_{i}\geq \mathbb{P}(A_{i})-\sum_{j: j < i, i \sim j}^{}\mathbb{P}(A_{i}\cap A_{j})$$Let $D_{0}:=\bigcap_{j:j<i, i \nsim j}^{}A_{j}^c$ and $D_{1}:=\bigcap_{j:j<i, i \sim j}^{}A_{j}^c$. Then, $$\begin{align}r_{i}&\geq \mathbb{P}(A_{i}|A^c_{i-1},\dots,A_{1}^c)=\mathbb{P}(A_{i}|D_{0},D_{1})=\frac{\mathbb{P}(A_{i}\cap D_{0}\cap D_{1})}{\mathbb{P}(D_{0}\cap D_{1})}\geq \frac{\mathbb{P}(A_{i}\cap D_{0}\cap D_{1})}{\mathbb{P}(D_{0})}\\&\geq \mathbb{P}(A_{i}\cap D_{1}|D_{0})=\mathbb{P}(A_{i}|D_{0})-\mathbb{P}(A_{i}\cap D_{1}^c|D_{0})=\mathbb{P}(A_{i})-\mathbb{P}(A_{i}\cap D_{1}^c|D_{0})\end{align}$$Then, note that $A_{i}$ is an increasing event and $D_{0},D_{1}$ are decreasing event. Therefore, $$\mathbb{P}(A_{i}\cap D_{1}^c|D_{0})=\frac{\mathbb{P}(A_{i}\cap D^c_{1}\cap D_{0})}{\mathbb{P}(D_{0})}\leq \mathbb{P}(A_{i}\cap D^c_{1})\leq \sum_{j:j <i, i\sim j}^{}\mathbb{P}(A_{i}\cap A_{j})$$This proves the statement.
> 2. Let $T\subseteq[k]$ and $X_{T}:=\sum_{i\in T}^{}\mathbb{1}_{A_{i}}$. Then, $$\mathbb{P}(X=0)\leq \mathbb{P}(X_{T}=0)\leq \exp \left( -\mu_{T}+\frac{\Delta_{T}}{2} \right) $$Choose $T\subseteq[k]$ by including each vertex with probability $q\in[0,1]$ independently. Then, 
> 	1. $\mathbb{E}[\mu_{T}]=\mathbb{E}\left[ \sum_{i\in[T]}^{}\mathbb{P}(A_{i}) \right]=q\sum_{i\in[k]}^{}\mathbb{P}(A_{i})=q\mu$.
> 	2. $\mathbb{E}[\Delta_{T}]=\mathbb{E}\left[ \sum_{(i,j)\in T^{2}: i\sim j}^{}\mathbb{P}(A_{i}\cap A_{j}) \right]=q^{2}\sum_{(i,j): i\sim j}^{}\mathbb{P}(A_{i}\cap A_{j})=q^{2}\Delta$.
> 	
> 	Therefore, $\mathbb{E}[-\mu_{T}+\Delta_{T} / 2]=-q\mu+q^{2}\Delta / 2$. Hence, we have that if we choose $q=\frac{\mu}{\Delta}$, then: $$\mathbb{P}(X=0)\leq \exp \left( -q\mu+\frac{q^{2}\Delta}{2} \right)=\exp \left( - \frac{\mu^{2}}{\Delta}+\frac{\mu^{2}}{2\Delta}\right) =\exp \left( -\frac{\mu^{2}}{2\Delta} \right) $$where $q\leq 1$ as $\mu\leq \Delta$.

---
##### Examples
> [!h] Example 1
> For $G\sim G(n,p)$, 
> 1. If $p=\text{o}(n^{-1/2})$, $\mathbb{P}(G\text{ is triangle free})=e^{-(1+o(1))n^3p^3/6}$.
> 2. If $p>\frac{2^3n^{-1/2}}{\sqrt{ 3 }}$, $\mathbb{P}(G\text{ is triangle free})\leq e^{-n^2p /6}$.

> [!proof]-
> Let $\{ S_{1},..,S_{k} \}={V \choose 3}$. Then,
> 1. $\mu=\sum_{i\in[k]}^{}\mathbb{P}(S_{i}\subseteq R)={n \choose 3}p^3$
> 2. $i\sim j$ happens if and only if they share one edge. Hence, $$\sum_{(i,j):i \sim j}^{}\mathbb{P}(A_{i}\cap A_{j})=\sum_{(i,j): i\sim j}^{}p^5=2{n \choose 4 }p^5$$
> 
> Then, if $p=o(n^{-1/2})$, by Janson, we have that: $$\mathbb{P}(G\text{ is triangle free}) \leq \exp \left( -{n \choose 3}p^3+{n \choose 4}p^5 \right) \leq \exp \left( -(1+o(1))\frac{n^3p^3}{6} \right) $$
> 
> For 2, if $p>n^{-1/2}$, then: $$\Delta=2{n \choose 4}p^5\geq \frac{n^4}{2^7}p^5\geq \frac{n^3p^3}{6}=\mu$$Hence, $$\mathbb{P}(G\text{ is triangle free})\leq \text{exp}\left( -\frac{\mu}{2\Delta} \right)\leq \exp \left( -\frac{n^2p}{6} \right)  $$
---
