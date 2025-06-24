---
title: "Lie algebras: Vector space vs linear operators"
---


## Lie algebra elements as linear operators

The fundamental representation of $A \in \mathfrak{se}(3)$ is

$$
A = \begin{pmatrix}
0 & 0 \\
\mathbf{a}_1 & \hat{a}_2
\end{pmatrix} \quad (1)
$$

which is a 4x4 matrix. We should more formally write this as 

$$
\rho_\text{fund}(A) = \begin{pmatrix}
0 & 0 \\
\mathbf{a}_1 & \hat{a}_2
\end{pmatrix} \quad (2)
$$

as the notion of a Lie algebra element $A$ is independent from its representation.

Recall that for a Lie algebra $\mathfrak{g}$, a representation is a mapping $\rho : \mathfrak{g} \to \mathfrak{gl}(V)$, where $V$ is some vector space and $\mathfrak{gl}(V)$ is (loosely) the space of all linear operators on $V$. In other words, a representation defines an *action* of $\mathfrak{g}$ on $V$.

In $(2)$ the vector space is $V = \mathbb{E}^3$. The fundamental representation $\rho_\text{fund}(A) : \mathbb{E}^3 \to \mathbb{E}^3$ is the action of $A$ on $\mathbb{E}^3$:

$$
A\cdot \mathbf{v} =\rho_\text{fund}(A)(\mathbf{v}) = \mathbf{a}_1 + \hat{a}_2 \mathbf{v} \quad (3)
$$

which can also be written as

$$
\begin{pmatrix}
0 & 0 \\
\mathbf{a}_1 & \hat{a}_2
\end{pmatrix} \begin{pmatrix}
1 \\ \mathbf{v}
\end{pmatrix} = \begin{pmatrix}
0 \\ \mathbf{a}_1 + \hat{a}_2 \mathbf{v}
\end{pmatrix} \quad (4)
$$


There is a slight inconsistency between how $\rho_\text{fund}(A)$ appears in $(2)$ and $(3)$. In the former it is a matrix, and in the latter it appears as a function that takes $\mathbf{v}$ as its argument. Explanation:
    -  We should see $(2)$ as the *matrix form* of the linear operator $\rho_\text{fund}(A)$ in a given basis of $\mathbb{E}^3$.
    -  We should see $(3)$ as the *linear operator form* of the representation, which is basis-independent.

Henceforth, to be extra clear, we shall differentiate the two notationally. $\rho_\text{fund}(A)$ refers to the linear operator, and $[\rho_\text{fund}(A)]$ will refer to its matrix form (in a given basis of $V= \mathbb{E}^3$). As a short-hand, we may also write $[A] \equiv [\rho_\text{fund}(A)]$.

Some remarks:

- Specifically, $\rho_\text{fund}(A)$ is the infinitesimal version of the fundamental action of $SE(3)$ on $\mathbb{E}^3$.
- In $(4)$, we see that the $\mathbb{E}^3$ element $\mathbf{v}$ has a $1$ prepended. This might seem a bit confusing, but this is necessary in order to represent translation as a linear operation. You can read more about this [here](https://hackmd.io/@lukastk/HJN0gdqsT) and [here](https://math.stackexchange.com/questions/3453270/why-is-this-translation-not-a-linear-transformation).
- You may notice that the prepended $1$ has turned into a $0$ in the RHS of $(4)$. This is because strictly speaking the $\rho_\text{fund}(A)$ is a mapping from $\mathbb{E}^3$ to the tangent space $T \mathbb{E}^3$ (so its signature is actually $\rho_\text{fund}(A) : \mathbb{E}^3 \to T \mathbb{E}^3$). To see why read [this](https://hackmd.io/@lukastk/HJN0gdqsT)  again. The fact that the codomain is now the tangent space makes intuitive sense, as $\mathbf{a}_1$ and $\hat{a}_2$ correspond to an infinitesimal translation and rotation respectively (i.e. a velocity and an angular velocity). So $\mathbf{a}_1 + \hat{a}_2 \mathbf{v}$ should be interpreted as a tangent vector (the rate-of-change of $\mathbf{v}$ when acted upon by $A$). The only reason I got away with writing $\rho_\text{fund}(A) : \mathbb{E}^3 \to \mathbb{E}^3$ above is because of the isomorphism $\mathbb{E}^3 \cong T\mathbb{E}^3$.
- It's important to keep in mind that as soon as you are working with matrix-forms $[A]$ of the representation, you have implicitly assumed that you are working on some basis of the fundamental representation space $V = \mathbb{E}^3$.

## Lie algebra elements as vectors

In the above we represented Lie algebra elements as linear operators on $\mathbb{E}^3$. However, Lie algebras also "exist" without reference to their action on some vector space. **In fact, they are vector spaces themselves.**

For example, given some basis $E_i \in \mathfrak{se}(3),\ i=1,\dots,6,$ we may write any Lie algebra element $A \in \mathfrak{se}(3)$ as $A = A_i E_i$. The components $A_i$ can also be seen as a 6-component column vector $\vec{A} = (\mathbf{a}_1^T\ \mathbf{a}_2^T)^T$ in the given basis (In the paper, I often write this as $\{ \mathbf{a}_1 ; \mathbf{a}_2\}$ instead). Why 6? That's because $\text{dim}(SE(3)) = \text{dim}(\mathfrak{se}(3)) = 6$.

**Remark:** *With the risk of adding extra confusion, I should point out that the linear operators $\rho_\text{fund}(A)$ are also vectors. That is, the set $\{ \rho_\text{fund}(A)\ |\ A \in \mathfrak{se}(3) \} \subset \mathbb{R}^{4 \times 4}$ is a vector space. This is one of the (many) reasons why we often identify Lie algebras with their fundamental representations.*

We thus have two ways of writing down a Lie algebra element $A$ explicitly (given a basis of $V = \mathbb{E}^3$):
1. As a matrix $[A]$
2. As a column vector $\{ \mathbf{a}_1 ; \mathbf{a}_2\}$.

Now, since $\mathfrak{se}(3)$ is a vector space, we may consider linear operators **acting on $\mathfrak{se}(3)$**. A set of such linear operators is given by the adjoint. For any Lie algebra element $B \in \mathfrak{se}(3)$, we have that $\text{ad}_B : \mathfrak{se}(3) \to \mathfrak{se}(3)$ is a linear operator acting on $\mathfrak{se}(3)$.

So if we write $\mathfrak{se}(3)$ as a vector space of 6-vectors, in a given basis, then we must have that $\text{ad}_B$ should be a $6\times 6$ matrix in that basis. We denote this matrix as $[\text{ad}_A] \in \mathbb{R}^{6 \times 6}$.

Finally, we should also note that $\text{ad}$ is actually **also a representation** of $\mathfrak{se}(3)$. Its signature is $\text{ad} : \mathfrak{se}(3) \to \mathfrak{gl}(\mathfrak{se}(3))$. So in this case, we have that $V = \mathfrak{se}(3)$ (i.e. the Lie algebra is acting on itself).

Let's tie it all together: Let $\odot$ denote the adjoint action, and let $A, B \in \mathfrak{se}(3)$, then all of the below are equivalent ways of writing the adjoint:

$$
\begin{aligned}
A \odot B & = \text{ad}_A B \\
& = [A,B] \\
& = \rho_\text{fund}^{-1}([A][B] - [B][A]) \\
& = ([\text{ad}_A] \begin{pmatrix}
B_1\ B_2\ B_3\ B_4\ B_5\ B_6
\end{pmatrix}^T )_i E_i \\
& = E_i [\text{ad}_A]_{ij} B_j
\end{aligned}
$$


## Completing the picture

What's an easy way to simultaneously treat Lie algebra elements as matrices and vectors? One way is to write a basis for the Lie algebra using its fundamental representation. See $(1)$ again. It is quite easy to parse out what a basis for all matrices of the form $(1)$ could be:

$$
\begin{aligned}
\tilde{E}_1 & = \rho_\text{fund}(\{(1\ 0\ 0 )^T; (0\ 0\ 0 )^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix} \\
\tilde{E}_2 & = \rho_\text{fund}(\{(0\ 1\ 0 )^T; (0\ 0\ 0 )^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix} \\
E_3 & =\rho_\text{fund}(\{(0\ 0\ 1 )^T; (0\ 0\ 0)^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0
\end{pmatrix} \\
\tilde{E}_4 & =\rho_\text{fund}(\{(0\ 0\ 0 )^T; (1\ 0\ 0 )^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & -1 \\
0 & 0 & 1 & 0
\end{pmatrix} \\
\tilde{E}_5 & =\rho_\text{fund}(\{(0\ 0\ 0 )^T; (0\ 1\ 0 )^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0 \\
0 & -1 & 0 & 0
\end{pmatrix} \\
\tilde{E}_6 & =\rho_\text{fund}(\{(0\ 0\ 0 )^T; (0\ 0\ 1 )^T) = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & -1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix}
\end{aligned}
$$

We can now "forget" the difference between $A$ and $\rho_\text{fund}(A)$, identifying $A \sim \rho_\text{fund}(A)$. Now, any element $A \in \mathfrak{se}(3)$ can be written as $A = A_i \tilde{E}_i$, and in vector form this is $A = \{ (A_1, A_2, A_3)^T; (A_4, A_5, A_6)^T \}$.

Some remarks:
- We have considered basis sets over two different spaces in the note: over the representation space $V = \mathbb{E}^3$ and over the Lie algebra $\mathfrak{se}(3)$. In principle these can be chosen independently. 
- However, the basis set $\tilde{E}_i \in \mathfrak{se}(3),\ i=1,\dots,6$ defined above is actually *induced* from a given basis  $\mathbf{d}_i \in \mathbb{E}^3,\ i=1,2,3,$ over the representation space.
    - *"Weren't the matrices $\tilde{E}_i$ a basis over the representation, and not the Lie algebra?"*: 
        - Yes but we have now identified the fundamental representation with the Lie algebra itself. So a basis over the set $\{ [A]\ |\ A \in \mathfrak{se}(3) \}$ is now a basis over the Lie algebra itself.
    - *"We haven't defined $\mathbf{d}_i$!"*
        - Yes, but as soon as you write down a $d \times d$ matrix, you implicitly assume that you are working in some basis for the $d$-dimensional vector space that the matrix acts on.
        - Recall that: 
            - a *vector* = element of a vector space
            - a *column vector* = a $d \times 1$-sized matrix of components of the vector in a given basis

