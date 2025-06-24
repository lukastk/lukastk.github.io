---
title: "Derivation of body force in $SO(3)$"
---


$$
\mathcal{T} = \frac{\partial \mathcal{L}}{\partial R}
$$

$$
R = (\mathbf{e}_1\ \mathbf{e}_2\ \mathbf{e}_3)
$$

Let $\mathcal{T}_i = \frac{\partial \mathcal{L}}{\partial \mathbf{e}_i}$, then

$$
\mathcal{T} = (\mathcal{T}_1\ \mathcal{T}_2\ \mathcal{T}_3)^T
$$

$$
\mathcal{T} R = \begin{pmatrix}
\mathcal{T}_1 \cdot \mathbf{e}_1 & \mathcal{T}_1 \cdot \mathbf{e}_2 & \mathcal{T}_1 \cdot \mathbf{e}_3 \\
\mathcal{T}_2 \cdot \mathbf{e}_1 & \mathcal{T}_2 \cdot \mathbf{e}_2 & \mathcal{T}_2 \cdot \mathbf{e}_3 \\
\mathcal{T}_3 \cdot \mathbf{e}_1 & \mathcal{T}_3 \cdot \mathbf{e}_2 & \mathcal{T}_3 \cdot \mathbf{e}_3 
\end{pmatrix}
$$

$$
\begin{aligned}
\hat{b}_1 & = \begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & -1 \\
0 & 1 & 0 
\end{pmatrix} \\
\hat{b}_2 & = \begin{pmatrix}
0 & 0 & 1 \\
0 & 0 & 0 \\
-1 & 0 & 0 
\end{pmatrix} \\
\hat{b}_3 & = \begin{pmatrix}
0 & -1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 0 
\end{pmatrix}
\end{aligned}
$$

Computing $T_i = \text{tr}(\mathcal{T} R \hat{b}_i)$, you get

$$
\begin{aligned}
T_1 & = \mathcal{T}_2 \cdot \mathbf{e}_3 - \mathcal{T}_3 \cdot \mathbf{e}_2 \\
T_2 & = -\mathcal{T}_1 \cdot \mathbf{e}_3 + \mathcal{T}_3 \cdot \mathbf{e}_1 \\
T_3 & = \mathcal{T}_1 \cdot \mathbf{e}_2 - \mathcal{T}_2 \cdot \mathbf{e}_1
\end{aligned}
$$

Now note that using $\mathbf{e}_3 = \mathbf{e}_1 \times \mathbf{e}_2$ we have that

$$
\mathcal{T}_2 \cdot \mathbf{e}_3 = \mathcal{T}_2 \cdot (\mathbf{e}_1 \times \mathbf{e}_2) = - \mathbf{e}_1 \cdot (\mathcal{T}_2 \times \mathbf{e}_2)
$$

where we used the fact that the [triple product](https://en.wikipedia.org/wiki/Triple_product) is unchanged under a circular shift.

So we get

$$
\begin{aligned}
T_1 & = -\mathbf{e}_1( \mathcal{T}_2 \times \mathbf{e}_2 + \mathcal{T}_3 \times \mathbf{e}_3 ) = -\mathbf{e}_1 \cdot \sum_i \mathcal{T}_i \times \mathbf{e}_i \\
T_2 & = -\mathbf{e}_2( \mathcal{T}_1 \times \mathbf{e}_1 + \mathcal{T}_3 \times \mathbf{e}_3 ) = -\mathbf{e}_2 \cdot  \sum_i \mathcal{T}_i \times \mathbf{e}_i \\
T_3 & = -\mathbf{e}_3( \mathcal{T}_2 \times \mathbf{e}_2 + \mathcal{T}_1 \times \mathbf{e}_1 ) = -\mathbf{e}_3 \cdot  \sum_i \mathcal{T}_i \times \mathbf{e}_i
\end{aligned}
$$

Finally

$$
\mathbf{T} = - R^T \sum_i \mathcal{T}_i \times \mathbf{e}_i
$$