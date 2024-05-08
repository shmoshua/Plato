#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a graph. For $U\subseteq V$, the ***induced graph*** $G[U]$ is defined as $(U,E')$ where
> 1. $E':=\{ \{ x,y \}\in E:x,y\in U \}$

- **Related definition**: If $H\subseteq G$, $G[H]:=G[V(H)]$.
- **Related definition**: For $U\subseteq V$, the ***deletion*** $G -U:=G[V \backslash U]$. For $H\subseteq G$, $G-H:=G -V(H)$.
- **Related definition**: For $F\subseteq \{ \{ u,v \} : u,v\in V \}$, $G+F:=(V,E\cup F)$ and $G-F:=(V,E \backslash F)$.