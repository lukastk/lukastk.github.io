---
title: The representation space of the fundamental representation of $SE(3)$
---



The fundamental rep $\rho$ of an element $g \in SE(3)$ is 

$$
\rho(g) = \begin{pmatrix}
1 & \mathbf{0}^T \\
\mathbf{t} & R
\end{pmatrix}
$$

Curiously, the fundamental rep is a 4x4 matrix, despite the fact that it acts on a 3-dimensional space $\mathbb{E}^3$. This is due to the fact that $SE(3)$ includes translations, and translations can only be represented as linear transformations in what's called 'homogeneous coordinates' (recall that the definition of a *representation* are a set of linear transformations that have the same group structure as the original group). That is, given $\mathbf{r} \in \mathbb{E}^3$

$$
g \cdot \mathbf{r} = \rho(g) \begin{pmatrix}
1 \\
\mathbf{r}
\end{pmatrix} = \begin{pmatrix}
1 \\
R \mathbf{r} + \mathbf{t}
\end{pmatrix}
$$

This is where the '$1$' comes from.

We can similarly compute the action of $g$ on a tangent vector $\mathbf{d} \in T \mathbb{E}^3$, which we will denote as $\hat{\cdot}$,  by replacing the $1$ with a $0$.

$$
g\ \hat{\cdot}\ \mathbf{d} = \rho(g) \begin{pmatrix}
0 \\
\mathbf{d}
\end{pmatrix} = \begin{pmatrix}
0 \\
R \mathbf{d}
\end{pmatrix}
$$

We can simulatenously compute the action of $g$ on many elements of $\mathbb{E}^3$ and $T \mathbb{E}^3$ like so

$$
\begin{aligned}
\rho(g) \begin{pmatrix}
1 & 1 & 0 & 1 & 0 \\
\mathbf{r}_1 & \mathbf{r}_2 & \mathbf{d}_1 & \mathbf{r}_3 & \mathbf{d}_2
\end{pmatrix} & \\
=\begin{pmatrix}
1 & 1 & 0 & 1 & 0 \\
R \mathbf{r}_1 + \mathbf{t} 
& R \mathbf{r}_2   + \mathbf{t} 
& R \mathbf{d}_1 
& R \mathbf{r}_3  + \mathbf{t} 
& R \mathbf{d}_2
\end{pmatrix}
\end{aligned}
$$