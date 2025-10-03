#Definition #Markov 

> [!definition]
> Let $\Omega:=\{ \pm 1 \}^n$ and $\mu\in \Delta(\Omega)$. 
> 1. ***Glauber dynamics*** on $\Omega$ is a local [[Markov chain]], i.e. at each step there is only a change to a single coordinate. Precisely,$$P(x\to x^{\oplus i})=\frac{1}{n}\cdot \frac{\mu(x^{\oplus  i})}{\mu(x)+\mu(x^{\oplus  i})}$$

^77c48c

---
##### Properties
> [!lemma] Proposition 1 (Properties of Glauber Dynamics)
> Let $(P,\mu)$ be the Glauber dynamics. Then, 
> 1. $P$ is [[Markov Chain|reversible]] w.r.t $\mu$.

^a44026

> [!proof]-
> We have that:
> 1. For $x\in \Omega$, $$\mu(x)P(x,x^{\oplus  i})=\frac{1}{n}\frac{\mu(x)\mu(x^{\oplus  i})}{\mu(x)+\mu(x^{\oplus  i})}=\mu(x^{\oplus  i})P(x^{\oplus  i},x)$$

^76ec7d

---
