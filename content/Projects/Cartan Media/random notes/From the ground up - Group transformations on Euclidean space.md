---
title: "From the ground up: Group transformations on Euclidean space"
notetype: doc
links:
  - "[[proj/Cartan Media]]"
doc-status: done
---


## Notation

The notation in this note differs from the Cartan media paper, so it should be read with fresh eyes.

#### Vector notation

Let $\mathbb{V}$ be a $d$-dimensional vector space. We choose a basis for $\mathbb{V}$, say $d_i,\ i= 1,\dots, d$. Then we can write elements of $\mathbb{V}$ in terms of components

$$
v = v_i d_i
$$

We may work directly in this basis, by considering the components $v_i$ as a *column vector*, which we write in bold-face notation as

$$
\mathbf{v} = \begin{pmatrix}
v_1 \\
v_2 \\
\vdots \\
v_d
\end{pmatrix} \in \mathbb{R}^d
$$

As a short hand, we can write

$$
v = v^s_i d_i = D \mathbf{v}
$$

So with a given basis $\{ d_i \}$ of a vector space $\mathbb{V}$, we effectively establish an isomorphism with the column vector space $\mathbb{V} \cong \mathbb{R}^d$. We can then also interpret the frame as a linear transformation between the two spaces $D : \mathbb{R}^d \to \mathbb{V}$. The inverse $D^{-1}$ is called the *component map*.

#### Group actions

To keep all the various group actions separate, I will use different notation for each of them. Here is a list of them:

- Translation group action
    $$
    T_v(p), \quad v\in T_p \mathbb{E}^3, p \in \mathbb{E}^3
    $$
- Rotation group action on $T_p \mathbb{E}^3$
    $$
    R \star v, \quad R\in SO(3),\ v\in T_p \mathbb{E}^3
    $$
- Rotation group action on $\mathbb{E}^3$
    $$
    R \odot x, \quad R\in SO(3),\ x\in \mathbb{E}^3
    $$
- Euclidean group action on $\mathcal{F}(T \mathbb{E}^3)$
    $$
    g \cdot x, \quad g\in SE(3),\ q\in \mathcal{F}(T \mathbb{E}^3)
    $$

## Translations

We consider mechanics in Euclidean space $\mathbb{E}^3$. Euclidean space is an *affine space*, meaning, amongst other things, that it lacks an origin.

$T \mathbb{E}^3$ is the tangent bundle of $\mathbb{E}^3$. $T_p \mathbb{E}^3$ is the tangent space at $p \in \mathbb{E}^3$. For a given tangent vector $v \in T_p \mathbb{E}^3$, let $\gamma_v : [-\infty, \infty] \to  \mathbb{E}^3$ be a *geodesic* curve that passes through $p$, such that $\gamma(0) = p$ and $\gamma'_v(0) = v$. Due to the properties of Euclidean space, this is just a straight line.

The geodesic is unique up to reparameterisation. Using the Euclidean metric, we impose that the parameterisation is the arc-length parameterisation, thus making the choice of $\gamma_v$ unique for any $v \in T_p \mathbb{E}^3$.

We define the *translation* of $p$ by $v$ as

$$
T_v(p) = \gamma_v(1)
$$

See below for an illustration:
<img width="400px" src="https://hackmd.io/_uploads/Sy6xITUCa.png">

For any two vectors $v, v' \in T_p \mathbb{E}^3$ it is easy to show that

$$
T_{v}( T_{v'}(p)) =  (T_{v} \circ T_{v'})(p) = T_{v + v'}(p)
$$

where $\circ$ denotes the composition of functions. This clearly shows that $\{ T_v\ |\ v \in T_p \mathbb{E}^3 \}$ is a *Lie group*, where group multiplication is the composition of functions. The fact that $T_{v} \circ T_{v'} = T_{v + v'}$ also shows that the Lie group is *abelian*. We can identify this Lie group with the *group of translations* $T(3)$.

Note that to construct $T(3)$, we had to pick some element $p \in \mathbb{E}^3$. This was necessary as Lie groups require an identity element. The corresponding identity transformation is in this case $T_0,\ 0 \in T_p \mathbb{E}^3$.

Now that we have gone through all this work, we may write translations using the short-hand:

$$ \tag{1}
T_v(p) = v + p 
$$

Strictly speaking, "$+$" here is not your typical addition. Rather, if we identify $T_p \mathbb{E}^3 \cong T(3)$, then "$+$" is the *action* of $T(3)$ on $\mathbb{E}^3$.

We can extend the definiton of $T_v$ so that it can operate on not just $p$, but all elements of $\mathbb{E}^3$. For any $x \in \mathbb{E}^3$, let $v' \in T_p \mathbb{E}^3$ satisfy $T_{v'}(p) = x$. We then define

$$
T_v(x) = T_{v + v'}(p) = x + v
$$

## Rotations on $T_p \mathbb{E}^3$

Let $F_p$ denote the set of ordered orthonormal bases of $T_p \mathbb{E}^3$. We write elements of $F_p$ as $E = (e_1, e_2, e_3) \in F_p$.

We now want to define rotations on $F_p$. Just as for translations, where we had to choose a distinguished element $p \in \mathbb{E}^3$, we must choose some reference element of $F_p$. We denote this element $D = (d_1, d_2, d_3) \in F_p$.

:::info
**Aside:** We have thus far chosen a reference point $p \in \mathbb{E}^3$ (an "origin"), and a reference frame $D = (d_1, d_2, d_3) \in F_p$. In physics, making this choice is known as choosing a *lab frame*.
:::

We take it as given that the general linear group acts on the tangent spaces of Euclidean space. That is we have the group $GL(T_p \mathbb{E}^3)$. We will write this action as $A \star v$, for any $A \in GL(T_p \mathbb{E}^3)$ and $v \in T \mathbb{E}^3$. We extend this to frames as well, defining

$$
A \star E = (A \star e_1, A \star e_2, A \star e_3)
$$

Now, consider a frame $E \in F_p$. Let $R \in GL(T_p \mathbb{E}^3)$ be a transformation such that $R \star D = E$. I trust you will believe me without proof that the set $\{ R\ |\ E = RD,\ \forall E \in F_p \}$ is the Lie group of orthogonal rotations $SO(3)$.

We've defined the group action of $SO(3)$ on a single frame $D$. As we did for translations, we can now extend this definition to all frames as follow. For any two elements $E, E' \in F_p$, there exists a rotation $R \in SO(3)$ such that $E = R \star E'$. If $E = R_1 D$ and $E' = R_2 D$, then $R = R_1 R_2^{-1}$.

We can also trivially extend the definition of the $SO(3)$ action to any other tangent space $T_x \mathbb{E}^3$ by parallel transporting $D \in F_p$ to $x \in \mathbb{E}^3$ along the geodesic. 

## Rotations on $\mathbb{E}^3$

We first make the observation again that the rotation of Euclidean space requires first picking out an element $p \in \mathbb{E}^3$. That is, we must always rotate around a given point.

Let $x \in \mathbb{E}^3$ and let $v \in T \mathbb{E}^3$ be such that $x = T_v(p) = v + p$. We can define the action of $R \in SO(3)$ on $x$ as

$$
R \odot x = T_{R \star v} (p)
$$

<img src="https://hackmd.io/_uploads/S1XQ4zPC6.png" width="400px">

This definition also implies that

$$
R \odot p = p
$$

## Euclidean transformations on $\mathcal{F}(T \mathbb{E}^3)$

The *orthonormal tangent frame bundle* $\mathcal{F}(T \mathbb{E}^3)$ is the set of all orthonormal bases of the tangent spaces $T_r \mathbb{E}^3$ for all $r \in \mathbb{E}^3$. That is

$$
\mathcal{F}(T \mathbb{E}^3) = \{ F_r\ |\ r \in \mathbb{E}^3 \}
$$

However, we will now change the notation slightly. We will write elements of orthonormal tangent frame bundle as $(r, E) = F_r \in \mathcal{F}(T \mathbb{E}^3)$.

We now consider Euclidean transformations on the orthonormal tangent frame bundle. Consider pairs of the form $g = (t\ ;\ R)$, where $t \in T_p \mathbb{E}^3 \cong T(3)$ and $R \in SO(3)$. For any two elements $g_1 = (t_1; R_1)$ and $g_2 = (t_2; R_2)$, we define multiplication as $g_1 g_2 = (R_1 \star t_1 + t_2;R_1 R_2)$. Then this forms the *Lie group of special Euclidean transformations* $SE(3)$.

As before, the group itself does not automatically carry with it any information about how it acts on a given space. We will use the definitions of the previous sections to define the action of $SE(3)$ on $\mathcal{F}(T \mathbb{E}^3)$. For an element $q = (r, E) \in \mathcal{F}(T \mathbb{E}^3)$ we define the action as

$$ \tag{2}
\begin{aligned}
g \cdot q & = (T_t(R \odot r), R \star E)  \\
& = (t + R \odot r, R \star E)
\end{aligned}
$$

:::info
There is a slight-of-hand that happens here. Note that $E \in F_r$, and technically $R \star E \in F_r$ as well, but the second argument of $g \cdot q$ should belong to $F_{t + R \odot x}$.
So really the $SE(3)$ action should also include the parallel transport of $R \star E$ from $F_r$ to $F_{t + R \odot x}$ as well.
:::

We will now see if this satisfies the axioms of a left action. It is easy to see that the identity element $(0; I)$ is an identity transformation $I \cdot q = q$. As for whether it is a left action:

Let $g_1 = (t_1; R_1)$ and $g_2 = (t_2; R_2)$, then

$$
\begin{aligned}
(g_1 g_2) \cdot q & = ( (R_1 \star t_2 + t_1) + (R_1 R_2) \odot x, (R_1 R_2) \star E)
\end{aligned}
$$

We also have that $g_2 \cdot q = (t_2 + R_2 \odot x, R_2 \star E)$, and so

$$
\begin{aligned}
g_1 \cdot (g_2 \cdot q) & = (t_1 + R_1 \odot (t_2 + R_2 \odot x), R_1 \star (R_2 \star E) ) \\
& = ( (R_1 \star t_2 + t_1) + (R_1 R_2) \odot x, (R_1 R_2) \star E) \\
& = (g_1 g_2) \cdot q
\end{aligned}
$$

So this is a *left action*.

#### Finally

Let $q_r = (p, D)$. We call this the *lab frame*. In the Cartan media paper, we only really apply the group action to this single element. We can see how our group acts on it. Let $\Phi = (t ; R) \in SE(3)$, then

$$
\begin{aligned}
\Phi \cdot q_r & = (t + R \odot p, R \star D) \\
& = (r, E)
\end{aligned}
$$

where we have defined $r = t + p$ and $E = R \star D$. We see that $p$ plays the role of an "origin" of Euclidean space.

## Representations induced from linear group actions

We have now defined various actions of $SO(3)$ and $SE(3)$ on various spaces. Since the actions are all *linear*, we have that the group actions define *representations* of the group.

For example, we have the $SO(3)$ group action on $T_p \mathbb{E}^3$. This is a *linear map* $v \mapsto R \star v$. We therefore have that the group action defines a representation $\rho : SO(3) \to GL(T_p\mathbb{E}^3)$.

## The necessity of picking an identity / the lab frame

At every stage of the various derivations in this note, we have singled out an element of the spaces we are acting on, in order to define the action of the Lie group. 

Why do we do this? Some motivations:

#### Motive 1

It makes sense by intuition. See the [informal description](https://en.wikipedia.org/wiki/Affine_space#Informal_description) of affine spaces in Wikipedia. In order to conceive of translations, you must first select some reference point $p \in \mathbb{E}^3$ around which to translate. The same goes for rotations.

#### Motive 2

In the Cartan media paper, we only ever apply the group action to a single element: the reference configuration $q_r$ (although strictly speaking, we also apply the inverse action on $q$ as well). We never even make use of group multiplication. We make use of the transitive property of the action, but never between two arbitrary points $q,q' \in \mathcal{F}(T\mathbb{E}^3)$. We only ever transform between $q$ and $q_r$, so it is somewhat natural that we choose a single point $q_r$ as a reference with which to define all $SE(3)$ transformations.

#### Motive 3

Consider again the transitive property of $SE(3)$ on the frame bundle $\mathcal{F}(T\mathbb{E}^3)$. For any two points $q_r, q \in \mathcal{F}(T\mathbb{E}^3)$, the group action is transitive if there exists at least one element $g \in SE(3)$ such that $g \cdot q_r = q$. 

That is, due to transitivity we have that the orbit

$$
G \cdot q_r = \{ g \cdot q_r\ |\ g \in G \}
$$

is equal to the frame bundle itself $G \cdot q_r = \mathcal{F}(T\mathbb{E}^3)$.

However, since $\text{dim}(\mathcal{F}(T\mathbb{E}^3)) = \text{dim}(SE(3))$, we also have that *for any $q_r \in \mathcal{F}(T\mathbb{E}^3)$* the set of group elements

$$
\{ g\ |\ g \cdot q_r = q,\ \forall q \in \mathcal{F}(T\mathbb{E}^3) \}
$$

is also equal to $SE(3)$. That is, picking out a single reference element $q_r$ is enough to generate the entire Lie group.

In less abstract terms: We don't need to re-define $SE(3)$ for every single possible reference frame. It is enough to define $SE(3)$ from within a *single reference frame*. This reference frame is $q_r$.

When $\mathbb{X} = \mathcal{F}(T \mathbb{E}^3)$, we call $q_r$ the *lab frame*. In the more general case, for a general Lie group, we may call it a *generalised lab frame*.

:::warning
**Note:** $q_r$ is only the generalised lab frame if $\text{dim}(\mathbb{X}) = \text{dim}(G)$. If $\text{dim}(\mathbb{X}) < \text{dim}(G)$ then

$$
\{ g\ |\ g \cdot q_r = q,\ \forall q \in G \}
$$

is not equal to $G$ in general.
:::

## Vectors in the lab frame

We can expand tangent vectors in the lab frame basis $D = (d_1, d_2, d_3)$. For any $v \in T_p \mathbb{E}^3$.

$$
v = v^s_i d_i = D \mathbf{v}^s
$$

where the superscript $s$ signifies that we are in the lab frame (or *spatial frame*, as I have called it in the paper). The bold-face signifies that it is a *column vector* $\mathbf{v}^s = (v^s_1\ v^s_2\ v^s_3)^T$, and $D \mathbf{v}^s$ is a short-hand for $v^s_i d_i$, which is loosely motivated by the fact that we can see it as a matrix product

$$
D \mathbf{v}^s = (d_1\ d_2\ d_3) \begin{pmatrix} 
v^s_1 \\ v^s_2 \\ v^s_3
\end{pmatrix}
$$

Using the same sleight-of-hands as before, we can expand vectors in other tangent spaces $T_x \mathbb{E}^3$ using the $D$ basis as well.

:::info
Before we proceed, we should make some conceptual distinctions. We have called $q_r$ the lab frame. This implies that other elements of $\mathcal{F}(T \mathbb{E}^3)$ are not the lab frame. This also implies that sentences such as "<i>The vector $v\in T_p \mathbb{E}^3$ is in the lab frame</i>" carry no meaning. My claim is that notions such as *lab frame* or *moving frame* only makes sense for the components of a vector in a *basis*. A pure vector $v \in T \mathbb{E}^3$ is not in any frame, only a column vector $\mathbf{v}$ with respect to a basis can be said to be in a frame.

I thus draw a distinction between *vector spaces* $\mathbb{V}$ and *column vector spaces* $\mathbb{R}^d$. For a vector space $\mathbb{V}$ of dimension $d$ with a basis $d_1, d_2, \dots, d_d \in \mathbb{V}$, then any vector $v \in \mathbb{V}$ has a corresponding column vector of components $\mathbf{v} \in \mathbb{R}^d$ in that basis.
:::

Likewise, for any element of Euclidean space $x \in \mathbb{E}^3$ we can find a vector $w \in T_p \mathbb{E}^3$ for which $x = w + p = D \mathbf{w}^s + p$. We can thus write $x$ in the lab frame as $\mathbf{w}^s$. Henceforth, to simplify the notation, we will denote the lab frame column vector of a Euclidean point $y \in \mathbb{E}^3$ as the bold-face version $\mathbf{y}^s$.

What is $p$ in the lab frame? Since $p = 0 + p$, we have that $p$ is $\mathbf{0}$ in the lab frame.

We can now also write frame bundle elements $q = (r, E) \in \mathcal{F}(T \mathbb{E}^3)$ in the basis as

$$
(r, E) = (D \mathbf{r}^s + p, (D\mathbf{e}_1^s, D\mathbf{e}_1^s, D\mathbf{e}_1^s) )
$$

The lab frame basis $D$ is, in its own basis, $\mathbf{d}_1^s = (1\ 0\ 0)^T$, $\mathbf{d}_2^s = (0\ 1\ 0)^T$ and $\mathbf{d}_1=3^s = (0\ 0\ 1)^T$.

Since $\mathbf{r}^s, \mathbf{e}_1^s, \mathbf{e}_2^s$ and $\mathbf{e}_3^s$ are all just elements $\mathbb{R}^3$, we can now bundle them together and put them in the form of a matrix. In the Cartan media paper, I assembled them in the form of a $4 \times 4$-matrix that mimicked that of a fundamental representation of $SE(3)$. In Mohammed's note, he bundled it together as a $3 \times 4$-matrix.

We are in principle free to bundle together the components however we wish. However, in the following section we will be considering the matrix representation of the $SE(3)$ action on $\mathcal{F}(T \mathbb{E}^3)$. We have already established that this is a left action, and we further decide on a specific form of the configuration space, this determines uniquely the matrix representation.

## Matrix representations of Lie groups

Earlier we saw that the group actions induced representations of Lie groups. Now that we have a way to express vectors in a basis, we can now also derive *matrix representations* of Lie groups.

For example, consider the action of $SO(3)$ on $T_p \mathbb{E}^3$. Let $w = R \star v$ where $w,v \in T_p \mathbb{E}^3$. Let $\rho(R)$ be the representation of $SO(3)$ such that we can write the group action as $w = \rho(R)(v)$. We can then use the linearity of the map to find

$$
w^s_i d_i = v^s_i (\rho(R)(d_i))
$$

We now define the matrix representation of $R \in SO(3)$ as the matrix $\tilde{\rho}(R) \in \mathbb{R}^{3 \times 3}$ with components

$$
\tilde{\rho}(R)_{ij} = \langle d_i, \rho(R)(d_j) \rangle
$$

where $\langle, \rangle$ is the Euclidean inner product on $T_p \mathbb{E}^3$. This satisfies $w_i^s = \tilde{\rho}(R)_{ij} v^s_j$. We thus have that $\rho(R)(v) = D (\tilde{\rho}(R)\mathbf{v}^s)$ and

$$
\mathbf{w}^s = \tilde{\rho}(R)\mathbf{v}^s
$$

We thus have a matrix representation $\tilde{\rho} : SO(3) \to GL(\mathbb{R}^3)$.

#### Matrix represenation of $SE(3)$ acting on the frame bundle

In the Cartan media paper, I have written components of the frame bundle $q = (r, E) \in \mathcal{F}(T \mathbb{E}^3)$ as 

$$ \tag{3}
q \text{ in lab frame} = \begin{pmatrix}
1 & 0 & 0 & 0 \\
\mathbf{r}^s & \mathbf{e}_1^s  & \mathbf{e}_2^s & \mathbf{e}_3^s 
\end{pmatrix}
$$

(where we have used the updated notation I have introduced in this note).

The configuration space, in the lab frame, are thus elements of the form of Eq. 3. So we have:

1. Fixed the form of the configuration space in a matrix form (Eq. 3)
2. Defined the action of $SE(3)$ on the frame bundle (in Eq. 2)

This fixes uniquely what the matrix representation of $SE(3)$ (given this action) should be.

Let $\zeta : SE(3) \to GL(\mathcal{F}(T \mathbb{E}^3))$ be the representation of the action, such that $g \cdot q = \zeta(g)(q)$. We write the Lie group element as $g = (t; R)$. More explicitly we have that

$$ \tag{4}
\zeta(g)(q) = \zeta(g)((r, E)) = (t + R \odot r, R \star E)
$$

In terms of the corresponding lab frame vectors we have that

$$
\begin{aligned}
t + R \odot r & = D(\mathbf{t}^s + \tilde{\rho}(R) 
\mathbf{r}^s) \\
R \star E & = (\rho(R)(e_1), \rho(R)(e_2), \rho(R)(e_3)) \\
& = (D \tilde{\rho}(R)\mathbf{e}^s_1, D\tilde{\rho}(R) \mathbf{e}^s_2, D \tilde{\rho}(R) \mathbf{e}^s_3))
\end{aligned}
$$


We thus see that we can write the matrix representation of $SE(3)$ as

$$ 
\tilde{\zeta}(g) = \begin{pmatrix}
1 & 0 \\
\mathbf{t}^s & \tilde{\rho}(R)
\end{pmatrix} \in \mathbb{R}^{4 \times 4}
$$

Which satisfies

$$ \tag{5}
\begin{pmatrix}
1 & 0 \\
\mathbf{t}^s & \tilde{\rho}(R)
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 & 0 \\
\mathbf{r}^s & \mathbf{e}_1^s  & \mathbf{e}_2^s & \mathbf{e}_3^s 
\end{pmatrix} = 
\begin{pmatrix}
1 & 0 & 0 & 0 \\
\mathbf{t}^s + \tilde{\rho}(R) \mathbf{r}^s & \tilde{\rho}(R) \mathbf{e}^s_1 & \tilde{\rho}(R) \mathbf{e}^s_2 & \tilde{\rho}(R) \mathbf{e}^s_3
\end{pmatrix}
$$

Compare Eq. 4 and 5 to see that this is indeed the correct matrix representation.


##### Acting on $q_r$

Finally, let's compare the action of a Lie group element $g$ on $q_r$, both in the abstract form and in the Lab frame.

Let $g = (t ; R)$, and recall that $q_r = (p, D)$. We have that

$$
g \cdot q_r = (t + p, R \star D)
$$

As we have previously established, we have that 

$$ \tag{3}
q_r \text{ in lab frame} = 
\begin{pmatrix}
 1 & 0 & 0 & 0 \\
 \mathbf{0} & \mathbf{d}^s_1 & \mathbf{d}^s_2 & \mathbf{d}^s_3
\end{pmatrix} = 
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{pmatrix} = I_4
$$

So 

$$
\tilde{\zeta}(g) I_4 = \tilde{\zeta}(g)
$$