#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach Algebra|Banach algebra]] and $\hat{A}$ the [[Guelfand Spectrum|Guelfand spectrum]] of $A$. The ***Guelfand topology*** is a topology on $\widehat{A}\subseteq A^{*}$ induced by the [[Weak Topology|weak*-topology]] on $A^{*}$.
---
##### Properties

---
From weak*-topology, let: $$U:=N(\varphi;(x_{1},\lambda_{1}),\dots,(x_{n},\lambda_{n});\varepsilon):=\{ \chi\in \widehat{A_{I}}:\left| \chi(x_{i},\lambda_{i})-\varphi(x_{i},\lambda_{i}) \right| <\varepsilon , \forall i\in [n] \}$$Then, 
1. if $\varphi_{\infty}\notin U$, then for any $\chi$ is some $\psi_{I}$ and $\psi_{I}\in U$ if and only if $$\psi\in N(\varphi;x_{1},\dots,x_{n};\varepsilon):=\{ \chi\in \widehat{A}:\left| \chi(x_{i})-\varphi(x_{i}) \right| <\varepsilon,\forall i\in [n] \}$$
1. if $\varphi_{\infty}\in U$ and $\varphi=\varphi_{\infty}$, then: $$U \backslash\{ \varphi_{\infty} \}=\{ \psi\in \widehat{A}:\left| \psi(x_{i}) \right| <\varepsilon,\forall i\in [n] \}=\widehat{A} \backslash\bigcup_{i\in [n]}^{}\{ \psi\in \widehat{A}:\left| \psi(x_{i}) \right|  \geq \varepsilon\}$$where $\{ \psi\in \widehat{A}:\left| \psi(x_{i}) \right|\geq \varepsilon \}$ is a closed set in $\widehat{A}$ and as $\widehat{A}$ is closed in $A^{*}$, by Banach Alaogolu, $\{ \psi\in \widehat{A}:\left| \psi(x_{i}) \right|\geq \varepsilon \}$ is compact. Therefore, $U\backslash\{ \varphi_{\infty} \}=\widehat{A} \backslash K$ where $K$ is compact. 
2. if $\varphi_{\infty}\in U$ and $\varphi=\varphi_{I}$, then we have $\left| \varphi(x_{i})\right|<\varepsilon$ for all $i$ and: $$U \backslash\{ \varphi_{\infty} \}=\{ \psi\in \widehat{A}:\left| \psi(x_{i})-\varphi(x_{i}) \right| <\varepsilon,\forall i\in [n]\ \}=\widehat{A} \backslash \bigcup_{i\in [n]}^{}\{ \psi\in \widehat{A}:\left| \psi(x_{i})-\varphi(x_{i}) \right| \geq \varepsilon \}$$Similar.
---

   