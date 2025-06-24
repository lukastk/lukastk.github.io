

Start with

$$
\begin{aligned}
\dot{X} & = \mathcal{D}_u N \\
\mathcal{D}^*_t S & = \mathcal{D}^*_u Q - \Gamma N
\end{aligned} \quad (1)
$$

Set $\mathcal{D}^*_t S = 0$ so that $N = \Gamma^{-1} \mathcal{D}^*_u Q$. Substituting, you get

$$
\dot{X} = F(X, X', X'') = \mathcal{D}_u(\Gamma^{-1}\mathcal{D}^*_u Q)
$$

Now $X_f : [0,L] \to \mathfrak{g}$ satsifies $F(X_f, X_f', X_f'') = 0$  for all $u$. That is, $X_f$ is a fixed point of $F$. Recall that the stress itself is of the form $Q = \mathrm{K}(X - X_0)$. Where $X_0 = (1\ 0\ 0\ 0\ 0\ 0)^T$.

We write $Q$ as

$$
Q = \mathrm{K} (\delta X + X_f -X_0)
$$

where $\delta X = X - X_f$. In general $\mathrm{K}$ would be $u$-dependent, but we will assume it is not. If we consider small perturbations $|\delta X| \ll 1$, then any term of order $\delta X_i \delta X_j$ can be discarded.

Now recall that $\mathcal{D}_u = \partial_u + \text{ad}_{X}$. So we have that

$$
\mathcal{D}_u = \partial_u + \text{ad}_{\delta X} + \text{ad}_{X_f}
$$

Similarly, we have that 

$$
\mathcal{D}^*_u = \partial_u + \text{ad}^*_{\delta X} + \text{ad}^*_{X_f}
$$

<b>Note: Actually, I'm not sure if $\text{ad}^*_{A + B} = \text{ad}^*_A + \text{ad}^*_B$. Can you check this? Perhaps your index formula for the dual adjoint will help to do this.</b>

Inserting all of this, we get

$$
\delta \dot{X} = (\partial_u + \text{ad}_{\delta X} + \text{ad}_{X_f})\Gamma^{-1}(\partial_u + \text{ad}^*_{\delta X} + \text{ad}^*_{X_f}) \mathrm{K} \delta X
$$




We can clearly see that no terms involving $\text{ad}_{\delta X}$ can survive, since $\text{ad}_{\delta X} \delta X \approx 0$, so we have

$$
\delta \dot{X} = (\partial_u + \text{ad}_{X_f})\Gamma^{-1}(\partial_u + \text{ad}^*_{X_f}) \mathrm{K} \delta X
$$

After having computed all terms, you'll get something that looks like

$$
\begin{aligned}
\delta \dot{X}(u,t) & = C(u) + A_0(u)\delta X(u,t) + A_1(u) \partial_u \delta X(u,t) + A_2(u) \partial_u^2 \delta X(u,t)
\end{aligned}
$$

However, the $C(u)$ term should vanish, if we impose that $F(X_f, X_f', X_f'') = 0$.

We can then neatly write the equation as

$$
\delta \dot{X} = \mathcal{A}^{(g)} \delta X \quad (2)
$$

where $\mathcal{A}^{(g)}$ is a $u$-dependent 2nd-order  differential operator

$$
\mathcal{A}^{(g)}  = A_0(u) + A_1(u) \partial_u  + A_2(u) \partial_u^2 
$$

and where the superscript signifies the dependence on the amplitude of the follower force.

The key thing now is to find the spectrum

$$
\mathcal{A}^{(g)} \psi_k^{(g)}(u) = \lambda_k^{(g)} \psi_k^{(g)}(u) \quad (3)
$$

Hopefully, since (3) is linear, this should be fairly straightforward. You will probably have to do some massaging though.

To simplify the problem, you may for now assume that $\mathrm{K}$ is diagonal. This should simplify equation (2) and (3) quite a lot.

---

In a previous [note](https://hackmd.io/wH2NQDNbTu-1CfqAajY2qQ), we found that

$$
X_f^{(g)}(u) = (\theta_1^{(g)}(u)\ 0\ 0\ 0\ 0\ 0)^T \quad (4)
$$

where $\partial_u^2 \theta_1^{(g)} = 0$, with boundary conditions $\theta_1^{(g)}(0) = g/\mathrm{K}_{11} + 1$ and $\theta_1^{(g)}(L) = 1$.

---

If it is more convenient, you may also repeat the above derivation but explicitly for the translational and rotational parts of the Cosserat rod. So start with

$$
\begin{aligned}
D_t \boldsymbol{\theta} & = D_u \mathbf{V} \\
\dot{\boldsymbol{\pi}} & = D_u \boldsymbol{\Omega} \\
D_t \mathbf{P} & = D_u \mathbf{F} - \gamma \mathbf{V} \\
D_t \mathbf{L} & = D_u \mathbf{M} + \boldsymbol{\theta} \times \mathbf{F} - \gamma^R \boldsymbol{\Omega}
\end{aligned}
$$

Following the same steps as above, setting $D_t \mathbf{P} =0$ and $D_t \mathbf{L} = 0$, should leave you with a set of equations analogous to (2) but for the translational and rotational parts separately.

Note, we have

$$
\begin{aligned}
\boldsymbol{\theta}_f & = (\theta_1^{(g)}\ 0\ 0)^T \\
\boldsymbol{\pi}_f & = (0\ 0\ 0)^T 
\end{aligned}
$$

and $\delta \boldsymbol{\theta} = \boldsymbol{\theta} - \boldsymbol{\theta}_f$ and $\delta \boldsymbol{\pi} =  \boldsymbol{\pi}$.

---
