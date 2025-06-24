
## Dynamical systems

A general **dynamical system** is of the form

$$
\dot{\mathbf{x}} = \mathbf{F}(\mathbf{x}) \quad (1)
$$

where $\mathbf{F} : \mathbb{R}^d \to \mathbb{R}^d$ is called the **drift**, $\mathbf{x} : [0,T] \to \mathbb{R}^d$ is the system state and $[0,T]$ is the time domain. 

A **fixed point** of a dynamical system is a point $\mathbf{x}_f$ such that $\mathbf{F}(\mathbf{x}_f) = 0$. 

## Linear dynamical systems

A **linear dynamical system** is of the form

$$
\dot{\mathbf{x}} = A (\mathbf{x} - \mathbf{x}_0) \quad (2)
$$

where $A$ is a $d\times d$ matrix, and $\mathbf{x}_0$ is a fixed point of the system.

Given some initial configuration $\mathbf{x}(0)$, the system will evolve as

$$
\mathbf{x}(t) = e^{t A} (\mathbf{x}(0) - \mathbf{x}_0) \quad (3)
$$

where $e^{t A}$ is the matrix exponential.

### Linear stability

The **stability** of a linear dynamical system around its fixed point $\mathbf{x}_0$ depends on the eigenspectrum of $A$. It's beyond the scope of this note to have a full discussion of the different classifications of linear stability (see any standard reference for more info), but briefly:

- If $\mathbf{x}(t)$ diverges as $t \to \infty$, given some initial condition $\mathbf{x}(0) = \mathbf{x}_0 + \delta \mathbf{x}$, then the system is **unstable**.
- If $\mathbf{x}(t) \to \mathbf{x}_0$ as $t \to \infty$, then the system is **stable**.

## Linearisation

A non-linear dynamical system can be **linearised** using the Taylor expansion of the drift around a given point $\mathbf{x}_r$:

$$
\mathbf{F}(\mathbf{x}) = \mathbf{F}(\mathbf{x}_r) + J_{\mathbf{x}_r} (\mathbf{x} - \mathbf{x}_r) + \dots \quad (4)
$$

where $(J_{\mathbf{x}_r})_{ij} = \frac{\partial F_i}{\partial x_j} \bigg|_{\mathbf{x} = \mathbf{x}_r}$ is the **Jacobian** evaluated at $\mathbf{x} = \mathbf{x}_r$.

The linearisation is then

$$
\dot{\mathbf{x}} = J_{\mathbf{x}_r} (\mathbf{x} - \mathbf{x}_r) \quad (5)
$$

In practice we will often write $\delta \mathbf{x} = \mathbf{x} - \mathbf{x}_r$, and write the equation as

$$
\delta \dot{\mathbf{x}} = J_{\mathbf{x}_r} \delta \mathbf{x} \quad (6)
$$

such that $\delta \mathbf{x}$ measures the perturbation of the system around its fixed point.

In most cases, we want to linearise a system around a fixed point of the drift, so $\mathbf{x}_r = \mathbf{x}_f$. If this is the case, then we can analyse the eigenspectrum of $J$ to determine the **stability of the system around $\mathbf{x}_f$**.

### Simpler way to linearise

Using the Taylor expansion can be quite involved. An alternative method is to simply compute $\mathbf{F}(\mathbf{x}_f + \delta \mathbf{x})$ and throw away any terms that are of quadratic or higher order in $\delta \mathbf{x}$. The resulting expression will be the linearised system.

## Linearising PDEs

The equations of motion of a Cosserat rod are

$$
\begin{aligned}
\dot{X} & = \mathcal{D}_u N \\
\mathcal{D}^*_t S & = \mathcal{D}^*_u Q+T
\end{aligned} \quad (7)
$$

where $\mathrm{M}$ is the mass-matrix of the rod. The generalised stress and generalised body force will in general be functions of the system configuration $Q = Q(X)$ and $T= T(X)$ (for simplicity we are neglecting any dependence on $\Phi$).


If we write $\mathbf{x} = (X^T\ N^T)^T \in \mathbb{R}^{12}$ and $\mathbf{F} = ((\mathcal{D}_u N)^T\ (\mathrm{M}^{-1}(\mathcal{D}^*_u Q+T))^T)^T$ then the equations become

$$
\dot{\mathbf{x}} = \mathbf{F}(\mathbf{x}, \partial_u \mathbf{x}) \quad (8)
$$

We can do linear stability analysis on $(8)$ the same way as before, but where we now would have to determine  spatial configurations $\mathbf{x}_f(u)$ such that $\mathbf{F}(\mathbf{x}_f, \partial_u \mathbf{x}_f)= 0$ for $u \in [0, L]$.

In the case of the Cosserat rod, finding the fixed point is usually quite trivial. Since we are linearising, there is no need for us to consider generalised body forces and stresses that are non-linear, so the general form is

$$
\begin{aligned}
Q & = \mathrm{K}(X - X_{f}) \\
T & = \mathrm{L}(X - X_{f2})
\end{aligned}
$$

The scenario we are working in does not include a body force, so we can also set $\mathrm{L} = 0$. We thus have that the fixed point configuration is $X = X_{f}$ and $N= 0$. The shape of the fixed point configuration will depend on the $u$-dependence of $X_{f}$, but to keep it simple we will assume that $X_{f}$ is constant, such that $\partial_u X_{f} = 0$. A straight rod configuration will look like $X_f = \{ (1\ 0\ 0)^T ; (0\ 0\ 0)^T \}$.

It is fairly simple to systematically linearise $(7)$. Substitute $\delta X = X - X_f$ and $\delta N = N$ into $(7)$, and only keep terms that are linear in $\delta X$ and $\delta N$. You should probably make use of the subcomponents of the generalised strains and velocities $X = \{ \theta ; \pi \}$ and $N = \{ V ; \Omega \}$.

Note that, since we are now linearising a PDE (which involves spatial derivatives along $u$), as opposed to an ODE, the Jacobian will in general be a differential operator (rather than just a matrix). The linearised system will thus be of the form

$$
\dot{\mathbf{x}} = \mathcal{A}_{\mathbf{x}_r} (\mathbf{x} - \mathbf{x}_r)
$$

where $\mathcal{A}_{\mathbf{x}_r}$ is a matrix where each component is some linear combination of real numbers and linear operators.


### Linear stability analysis of PDEs

There are now a couple of different approaches to do linear stability analysis. Perhaps one of the more straight-forward methods is to convert the problem into an ODE, which I outline below. I also found [these](http://math.bu.edu/people/mabeck/lin_stab_minicourse_2012.pdf) notes that might provide some additional methods.

:::warning
Note: I wrote this section before I figured out the two solution strategies at the bottom of this document. Ultimately I think Strategy 1 is the best option.
:::


#### Transforming the PDE into an ODE

It is possible to work in the PDE form in principle, but when doing numerics it is often easier if we convert $(8)$ to an ODE, by expanding $\mathbf{x}$ in a functional basis.

We write

$$
x_i(t,u)_ = \sum_{k=1}^\infty c_{ik}(t) f_k(u) \quad (9)
$$

where $f_k(u)$ are basis functions that satisfy $\langle f_k, f_l \rangle = \delta_{kl}$ for some inner product. We then have

$$
\begin{aligned}
\dot{x}_i & = \sum_{k=1}^\infty \dot{c}_{ik}(t) f_k(u) \\
\partial_u x & = \sum_{k=1}^\infty c_{ik}(t) \partial_u f_k(u) 
\end{aligned} \quad (10)
$$

Since the system configuration, and its derivatives, are now completely determined by the coefficients $c_k$, and since the basis functions $f_k$ are linearly independent, we can now rewrite $(8)$ as

$$
\dot{c}_{ik} = F_{ik}(c_{11}, c_{12}, \dots) \quad (11)
$$

where $F_{ik} = \langle f_k, F_i(\mathbf{x}, \partial_u \mathbf{x}) \rangle$.

If we truncate to $M$ modes, $(11)$ is now a dynamical system in $6M$ dimensions.

---

What basis functions should we use? Given that we are looking at an open rod, it would make sense to use the *Chebyshev polynomials of the first kind*.


### Overdamped equations of motion

We can add a friction $T = - \Gamma N$, where $\Gamma$ is a friction matrix. If we assume that we are working in an overdamped regime, then $\dot{N} \approx 0$. We can then substitute the force balance equations into the kinematic equations of motion to get

$$
\dot{X} = \mathcal{D}_u( \Gamma^{-1}( \mathcal{D}_u^* Q)) \quad (12)
$$

which are the overdamped equations of motion. All techniques outlined above still applies to $(12)$. The only difference is that the RHS $(12)$ now also depend on the second derivative of $X$.




## Applying a follower force

Below is an outline of what I think the right steps are in this calculation, but you should read around the literature more thoroughly.

:::info
Here are some relevant references to read:
- https://royalsocietypublishing.org/doi/10.1098/rsif.2017.0491
- https://archive.org/details/@mirtitles?query=bolotin
:::

A follower force is not a generalised stress or a generalised body force. Rather, it is a boundary force (See Eq. 30b in the Cartan media paper).

Boundary forces work effectively like boundary conditions on the system. For example, a boundary force at $u=0$ would be expressed as

$$
Q = P_0,\ \text{ at } u = 0 \quad (13)
$$

where $P_0$ is the boundary force. Since $Q = Q(X)$, $(13)$ induces a boundary condition on $X$. Now let $Q = \mathrm{K} (X - \bar{X})$, where $\bar{X} = (1\ 0\ 0\ 0\ 0\ 0)^T$, then the boundary condition is

$$
X = \mathrm{K}^{-1} P_0 + \bar{X},\ \text{ at } u = 0 \quad (14)
$$

In our scenario, we will consider a follower force that acts tangentially. $P_0$ will thus be of the form $P_0 = (g\ 0\ 0\ 0\ 0\ 0)^T$, where $g \in \mathbb{R}$ is the magnitude of the force.

---

How do you do the linearisation? The constant fixed point generalised strain configuration $X_f = \{ (1\ 0\ 0)^T ; (0\ 0\ 0)^T \}$ from earlier is no longer valid given $(14)$. In general the fixed point configuration would now be $u$-dependent.

My hunch would be that you would now have to solve for the correct fixed point configuration $X_f(u)$ given a boundary force magnitude $g$. That is, you have to find the solution $X_f^{(g)}$ of the 2nd order  differential equation (presuming overdamped dynamics)

$$
0 = F(X_f^{(g)}, \partial_u X_f^{(g)}, \partial_u^2 X_f^{(g)}) \quad (15)
$$

with boundary conditions $X_f^{(g)}(0) = \mathrm{K}^{-1} P_0$ and $X_f^{(g)}(L) = 0$, and where $F = \mathcal{D}_u( \Gamma^{-1}( \mathcal{D}_u^* Q))$. (*Note that this is just an ODE, not a PDE, because we are not including time)*

Because of the symmetry of the problem, $(15)$ might be relatively easy to solve. Presuming that $\mathrm{K}$ and $\Gamma$ are diagonal, then I think the only non-zero values in $X_f^{(g)}$ is the tangential component. That is, the solution will have to be of the form

$$
X_f^{(g)}(u) = (\theta_1^{(g)}(u)\ 0\ 0\ 0\ 0\ 0)^T \quad (16)
$$

By inspection it would seem that we can solve $(15)$ pretty easily if we substitute in $(16)$. As $\pi^{(g)} = 0$, we have that $D_u = \partial_u$ (see Eq. 38 in the Cartan media paper). You should verify this, but I believe we simply get $\partial_u^2 \theta_1^{(g)} = 0$, with boundary conditions $\theta_1^{(g)}(0) = g/\mathrm{K}_{11} + 1$ and $\theta_1^{(g)}(L) = 1$, which has an analytical solution.

After having found $X_f^{(g)}$, you should then linearise the system around the fixed point configuration, and do some linear stability analysis. That is, you need to compute the Jacobian $J^{(g)}$ of the drift, and analyse its eigenspectrum.

---

What will the fixed point configuration of the rod look like, given a follower force of strength $g$? If I'm correct about $(16)$, then for any $g$ the fixed point configuration $\Phi^{(g)}$ will be a straight rod that is compressed at one end.

Now, for low $g$, you would expect that the *fixed point is also a rest configuration*. That is, you would expect that $X^{(g)}$ is a *stable* fixed point of the dynamics. However, at some *critical $g$*, it should be the case that $X^{(g)}$ turns into an *unstable fixed point*. For $g > g_\text{crit}$, any perturbation $X \to X^{(g)} + \delta X$ should start diverging.

---

I anticipate some further complication once you have done the initial linerisation. Namely, the boundary conditions will induce a constraint on the perturbation $\delta X$. Specifically we must have that $\delta X(0) = \delta X(L)= 0$. 

**Possible strategy 1 (recommended approach):**

In principle it should be possible to solve the linearised system.

$$
\begin{aligned}
\delta \dot{X} & = F(X^{(g)} + \delta X, \partial_u (X^{(g)} + \delta X), \partial_u^2 (X^{(g)} + \delta X)) \\
 & \approx F(X_f^{(g)}, \partial_u X_f^{(g)}, \partial_u^2 X_f^{(g)}) +  \mathcal{A}^{(g)}\delta X + O(\delta X^2) \\
 & = \mathcal{A}^{(g)} \delta X + O(\delta X^2)
\end{aligned}
$$

where $\mathcal{A}^{(g)}$ is a 2nd order differential operator. The linearised PDE is thus

$$
\delta \dot{X} = \mathcal{A}^{(g)} \delta X \quad (17)
$$

with boundary conditions $\delta X(0) = \delta X(L) = 0$. 

$\mathcal{A}^{(g)}$ is a 2nd order differential operator in $u$. By considering its [spectrum](https://en.wikipedia.org/wiki/Spectral_theory_of_ordinary_differential_equations) we can investigate the linear stability of $(17)$, as a function of $g$. That is we find the eigenvalues $\lambda_k^{(g)}$ by solving the equation

$$
\mathcal{A}^{(g)} \psi_k(u) = \lambda_k^{(g)} \psi_k(u) \quad (18)
$$

with the boundary conditions $\psi_k(0) = \psi_k(L) = 0$.

$(18)$ is a linear ODE, so it should be solvable analytically in principle. You should check whether it is possible to put the equations in [Strum-Liouville form](https://en.wikipedia.org/wiki/Sturm%E2%80%93Liouville_theory).

However, you should also be able to find the spectrum using numerical methods. Trefethen's 'Spectral Methods in MATLAB' go through in detail how to solve these kinds of problems.

Once you have the spectrum, it is simple to do the stability analysis. If $\lambda_k^{(g)} < 0$ for all $k$, then the system is stable. If for any $k$ we have that $\lambda_k^{(g)} > 0$, then the system is unstable. For small $g$ we would expect that the system is stable. We want to find the $g$ for which we see the first unstable eigenvalues.

:::info
Side note. If the $(17)$ can be put into Sturm-Lioville form, then it is *self-adjoint*. We can easily find the solution for such systems using its eigenspectrum.

Let's say you want to solve $(17)$ with initial conditions $\delta X_0(u) = \sum_k a_k \psi_k(u)$ expanded in the eigenbasis. Then the solution is

$$
\delta X(u, t) = \sum_k e^{-t \psi_k} a_k \psi_k(u)
$$

if $\mathcal{A}^{(g)}$ is self-adjoint. To see this, expand $\delta X$ in the eigenbasis and plug back into $(17)$. Since $\psi_k$ are orthogonal if $\mathcal{A}^{(g)}$ is self-adjoint, we find the above solution.

:::

**Possible strategy 2:**

Another alternative is to expand $\delta X$ in a functional basis that respect the boundary conditions. For example, if $T_n(u)$ are the [Chebyshev polynomials of the first kind](https://en.wikipedia.org/wiki/Chebyshev_polynomials), then if we define

![image](https://hackmd.io/_uploads/Syy9Qsnaa.png)


then $\phi_n(u)$ satisfy $\phi_n(-1) = \phi_n(1) = 0$. If we now expand

$$
\delta X(u,t) = \sum_{k=2}^\infty \alpha_k(t) \phi_k(u) \quad (18)
$$

then $\delta X$ satisfy the boundary conditions.

By inserting $(18)$ into $(17)$ we can then reformulate the PDE as an ODE in terms of the coefficients $\alpha_k(t)$. You can do this by using the fact that:

![image](https://hackmd.io/_uploads/Skau4jnp6.png)

Note however that though $T_k(u)$ are orthogonal, $\phi_k(u)$ are not orthogonal.

The end result should be an (infinite-dimensional) ODE of the form

$$
\dot{\alpha}_k(t) = \sum_{l=2}^\infty A^{(g)}_{kl} \alpha_l(t)
$$

We can then analyse the linear stability of the system by looking at the spectrum of $A^{(g)}_{kl}$. Numerically you would have to truncate the number of modes to render $A^{(g)}_{kl}$ a finite-dimensional matrix first.

The linear stability analysis should be fairly straightforward. For small $g$ the linear drift coefficient matrix $A^{(g)}$ should be negative definite. At sufficiently large $g$ it should be positive definite. The goal is to find the $g$ at which $A^{(g)}$ undergoes a transition from negative definite to non-negative definite.

<!--
In principle we have

$$
\begin{aligned}
\delta \dot{X} & = F(X^{(g)} + \delta X, \partial_u (X^{(g)} + \delta X), \partial_u^2 (X^{(g)} + \delta X)) \\
 & = F(X_f^{(g)}, \partial_u X_f^{(g)}, \partial_u^2 X_f^{(g)}) +  \int_0^L du'\ J(u,u') \delta X(t, u') + O(\delta X^2) \\
 & =  \int_0^L du'\ J(u,u') \delta X(t, u')
\end{aligned}
$$
-->