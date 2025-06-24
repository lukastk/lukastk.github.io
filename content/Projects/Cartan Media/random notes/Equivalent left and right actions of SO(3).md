---
title: Equivalent left and right actions of $SO(3)$
---



Consider the vector space $T \mathbb{E}^3$. We have frames $d_1, d_2, d_3 \in T \mathbb{E}^3$ and $e_1, e_2, e_3 \in T \mathbb{E}^3$. They are related by the left action of $SO(3)$ as follows

$$ \tag{1}
e_i = R d_i
$$

Now consider a vector $v \in T \mathbb{E}^3$. It can be expanded as $v = v_i d_i$. We have that

$$ \tag{2}
R v = v_i R d_i = v_i e_i
$$

If we let $R_{ij} = \langle d_i, R d_j \rangle$, then

$$ \tag{3}
R_{ij} v_j = (R v)_i
$$

In the notation of my various notes, I've kept vectors and column vectors as distinct, where the latter is written using bold-face notation. We can thus write (3) as

$$ \tag{4}
\Pi(R) \mathbf{v} = \begin{pmatrix}
(R v)_1 \\ (R v)_2 \\ (R v)_3
\end{pmatrix}
$$

where $\mathbf{v} = (v_1\ v_2\ v_3)^T \in \mathbb{R}^3$ and $\Pi : SO(3) \to GL(\mathbb{R}^3)$ is a matrix representation of $SO(3)$.

---

Let's go back to (1). There must exist some set of coefficients $\tilde{R}_{ij}$ such that

$$ \tag{5}
e_j = d_i \tilde{R}_{ij}
$$

where $\tilde{R}_{ij}$ are yet to be related to $R$ at this stage.

Comparing (1-2) and (5), we find that

$$
\Pi(R)_{ij} = R_{ij} = \tilde{R}_{ij}
$$

So we see that it is really the same matrix representation of $SO(3)$ acting in both instances, but where its left and right multiplication defines its left and right action respectively. The left and right action here are completely equivalent.

The right action of $R$ in (5) acts on the frame $d_1, d_2, d_3$ as a whole, whilst the left action in (1) acts on individual vectors. The reason why they can be made equivalent, is because the individual basis vectors in the frame $d_i$ are also vectors.

My aim in writing this note is to show that the two approaches seem to be equivalent. The benefit of the right action is that it does seem to act on the whole frame at once. However, the con is that this general approach requires us to only consider configuration spaces $\mathbb{X}$ that have trivial stabiliser (i.e. $\mathbb{X} \cong G$). There is no way to write down (5) if we were to consider the configuration space of a Cosserat surface $(r, e) \in \mathbb{X}$, which consist of a single director.

I think the interpretation of the right-action (5) is that we are considering $d_i$ and $e_i$ a *basis* of $T \mathbb{E}^3$. However, for a Cosserat rod $e_i$ are not really a basis, they are actual configurational degrees of freedom.

<!--

#### Equivalent left and right actions of $SE(3)$

Consider an $SE(3)$ element $g = (t, R)$. Its action on Euclidean space is

$$
g \cdot x = t + Rx
$$

where $x \in \mathbb{E}^3$. Taking the derivative of this action gives us the action of $SE(3)$ on $T \mathbb{E}^3$

$$
g \cdot v = R v
$$

where $v \in T \mathbb{E}^3$.

Consider an element $m = (x, d_1, d_2, d_3) \in F(\mathbb{E}^3)$. We can easily extend the action to the frame bundle as

$$
g \cdot m = (t + Rx, R d_1, R d_2, R d_3)
$$

Now consider an element $n = (y, e_1, e_2, e_3) \in F(\mathbb{E}^3)$ which is related to $m$ as $m = g \cdot n$. We have that

$$
\begin{aligned}
y & = t + Rx \\
e_j & = R d_i
\end{aligned}
$$

From the previous section, we know that we can write

$$
e_j = d_i R_{ij}
$$

Now let us expand $x$ in $d_i$ as $x = x_i d_i$. Then $Rx = x_j e_j = d_i R_{ij} x_j$. So if we write $y = y_i d_i$ and $t = t_i d_i$ then

$$
\begin{aligned}
y =  \\
e_j & = d_i R_{ij}
\end{aligned}
$$

-->