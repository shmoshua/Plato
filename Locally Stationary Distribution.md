#Project 

> [!definition]
>  Let $P$ be a finite irreducible [[Markov Chain|Markov kernel]], reversible w.r.t. $\pi> 0$. 
>  1. For $\varepsilon>0$, a distribution $\nu$ is ***$\varepsilon$-locally stationary*** if: 
> 	 $$\mathcal{E}_{P}(f,\log f):=\braket{ f , (I-P)\log f } _{\pi}\leq\varepsilon$$
> 	where $f:= d\nu / d\pi$.
---
##### Properties
> [!lemma] Proposition 1 (Derivative of KL Divergence)
> Let $\nu_{t}:=\exp(-t(I-P))\nu$. Then, 
> $$\mathcal{E}_{P}(f_{t},\log f_{t})=-\frac{d}{dt}\operatorname{KL}(\nu_{t}\|\pi)$$

> [!proof]-
> We have that: 
> $$\begin{aligned}\frac{d}{dt}\operatorname{KL}(\nu_{t}\|\pi)&=\frac{d}{dt}\sum_{x} \nu_{t}(x)\log f_{t}(x) \\&= \sum_{x} \pi(x)\frac{d}{dt}f_{t}(x)\log f_{t}(x) \\&= \sum_{x} \pi(x)\left(\log f_{t}(x)+1\right)\frac{d}{dt}f_{t}(x)\\&=-\braket{ (I-P)f_{t} , \log f_{t}+1}_{\pi}\\&=-\braket{f_{t} , (I-P)\log f_{t}+1}_{\pi} 
> \\&=-\braket{f_{t} , (I-P)\log f_{t}}_{\pi} \\&=-\mathcal E_{P}(f_{t},\log f_{t})\end{aligned}$$
> where 
> $$\frac{d}{dt}\nu_{t}=\nu\frac{d}{dt} \exp(t(P-I))=\nu_{t}(P-I)$$