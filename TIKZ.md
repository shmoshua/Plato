##### DAGS
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}

\begin{document}

\begin{tikzpicture}

\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
\tikzset{edge/.style = {->,> = latex'}}
% vertices
\node[vertex] (a) at  (4,2) {$w$};
\node[vertex] (b) at  (0,0) {$y_1$};
\node[vertex] (b1) at (1.5,0) {$y_2$};
\node[vertex] (b2) at (3,0) {$y_3$};
\node[vertex] (c) at  (8,0) {$y_n$};


%edges
\draw[edge] (a) to (b);
\draw[edge] (a) to (b1);
\draw[edge] (a) to (b2);
\draw[edge] (a) to (c);

\path (b2) to node {\dots} (c);

\end{tikzpicture}
\end{document} 
```