

<!--

---

Consider a Cartan media configuration $q : M \to \mathbb{X}$ and a virtual displacement field $v : M \to T \mathbb{X}$.

$$
\int_M \mathcal{T}(v) dV+
\int_{\partial M} \mathcal{P}(v) dS =
\int_M \mathcal{Q}(d v) dV +
\int_M \mathcal{S}(v) dV
$$

where $\mathcal{T}, \mathcal{S} : T q(M) \to \mathbb{R}$ is the generalised body force and  momentum respectively, and $\mathcal{P} : T \partial q(M) \to \mathbb{R}$ is the generalised surface traction. $\mathcal{Q}$ is the generalised stress, that maps $d v : TM \to TT q(M)$ to $\mathbb{R}$.


$$
\int_M \mathcal{T}(\delta q) dV+
\int_{\partial M} \mathcal{P}(\delta q) dS =
\int_M \mathcal{Q}(\delta d q) dV +
\int_M \mathcal{S}(\delta q) dV
$$

Now one must derive some kind of compatability condition, since $\delta q$ and $\delta dq$ are not independent. It is likely that we have $\delta (dq) = \mathcal{L}_{\delta q} d q$

---

We have

$$
\int_M \mathcal{T}(\delta q) dV+
\int_{\partial M} \mathcal{P}(\delta q) dS =
\int_M \mathcal{Q}(\delta (d q) ) dV +
\int_M \mathcal{S}(\delta q) dV
$$

where $\delta q = v$ and $\delta (dq) = \mathcal{L}_v dq$.

---

$$
\int_M \mathcal{T}(\delta q)+
\int_{\partial M} \mathcal{P}(\delta q) =
\int_M \mathcal{Q}(\delta (d q) ) +
\int_M \mathcal{S}(\delta q)
$$

$\delta (dq) = \delta \chi_\alpha du^\alpha$ so $\delta (dq) : TM \to TT \mathbb{X}$ and $\delta \chi_\alpha : M \to TT \mathbb{X}$.

$$
\mathcal{Q}(\delta (dq)) = \sum_\alpha \mathcal{Q}^\alpha( \delta \chi_\alpha )\ dV
$$

---

You need a metric to define the Hodge dual, but I don't know if we need to go to that length. Let $\omega$ be a volume form on $M$, and let $\alpha \in \Omega^k(M)$. Let $\beta \in \Omega^{d-k}(M)$ be such that $\omega = \alpha \wedge \beta$. Surely $\beta$ is uniquely defined?

All of this is quite coordinate dependent. But that might be fine. The only requirement is that $Q(\delta \xi)$ is a volume form. Once you have defined coordinates, you've commited in a way to those coordinates.

So if I have $\alpha = du^1$, then $\beta = |J| du^2 \wedge \dots \wedge du^d$. I guess it doesn't even have to be a unique choice. If you do have the Hodge dual, then there's a nice way to construct $\beta$, but it doesn't have to be unique.

Let $dV = du^1 \wedge \dots \wedge du^d$, and 
$$
d\bar{u}^\alpha = du^1 \wedge \dots \wedge du^{\alpha-1} \wedge \dots \wedge du^{\alpha+1} \wedge \dots \wedge du^d$$
Then $d \bar{u}^\alpha \wedge d u^\alpha$ is equal to $dV$ up to sign. So absorb that sign into $d \bar{u}^\alpha$ such that $d \bar{u}^\alpha \wedge d u^\alpha = d V$. Now let

$$
Q = Q^\alpha d \bar{u}^\alpha
$$

and it acts like

$$
Q(\delta \xi) = \sum_\alpha \langle \delta X_\alpha, Q^\alpha \rangle\ d \bar{u}^\alpha \wedge du^\alpha
$$

correspondingly, at the $M\to\mathbb{X}$ level, we may have

$$
\mathcal{Q}= \mathcal{Q}^\alpha d \bar{u}^\alpha
$$

$$
\mathcal{Q}(\delta (dq)) = \sum_\alpha \mathcal{Q}^\alpha(\delta \chi_\alpha)\ d \bar{u}^\alpha \wedge du^\alpha
$$

where $\mathcal{Q}^\alpha : TT\mathbb{X} \to \mathbb{R}$. 

Remember that you had this

$$
\langle \delta \xi \wedge i_\Gamma \omega \rangle =
 \langle \delta N, S \rangle dt \wedge dV -
\langle \delta X_\alpha, Q^\alpha \rangle dt \wedge dV
$$


---

Perhaps the best way to tease this out is by formifying this:

$$
\int_\mathcal{Q} \mathbf{b} \cdot \delta \mathbf{u}\ dv
 +\int_{\partial \mathcal{Q}} \mathbf{t} \cdot \delta \mathbf{u}\ ds
 =\int_{\mathcal{Q}} \sigma : \nabla \delta \mathbf{u}\ dv
 +\int_{\mathcal{Q}} \rho \ddot{\mathbf{u}} \cdot \delta \mathbf{u}\ dv
$$

We have $q : M \to \mathbb{E}^3$. We have a virtual displacement field $v : M \to T \mathbb{E}^3$. 

-->

### Classical continuum mechanics

We consider a virtual displacement field $\delta \mathbf{u}$. The virtual work is

$$
\int_\mathcal{Q} \mathbf{b} \cdot \delta \mathbf{u}\ dv
 +\int_{\partial \mathcal{Q}} \mathbf{t} \cdot \delta \mathbf{u}\ ds
 =\int_{\mathcal{Q}} \sigma : \nabla \delta \mathbf{u}\ dv
 +\int_{\mathcal{Q}} \rho \ddot{\mathbf{u}} \cdot \delta \mathbf{u}\ dv
$$

where $\mathbf{b}$ is the body force, $\mathbf{t}$ is the surface traction, $\sigma$ is the Cauchy stress tensor and $\rho$ is the mass density and $\mathcal{Q}$ is the current configuration.

I think the stress term ends up with an opposite sign to the body force term because it is a reactive force. This can probably be motivated by reading the section in Landau-Lifschitz where they define the stress tensor.

We do integration-by-parts to put it in the form

$$ \tag{1}
\int_\mathcal{Q} \mathbf{b} \cdot \delta \mathbf{u}\ dv
 +\int_{\partial \mathcal{Q}} \mathbf{t} \cdot \delta \mathbf{u}\ ds
 =\int_{\mathcal{Q}} \sigma : \nabla \delta \mathbf{u}\ dv -
 \int_{\mathcal{Q}} \rho \dot{\mathbf{u}} \cdot \delta \dot{\mathbf{u}}\ dv
$$

[Reference](https://pkel015.connect.amazon.auckland.ac.nz/SolidMechanicsBooks/Part_III/Chapter_3_Stress_Mass_Momentum/Stress_Balance_Principles_09_Virtual_Work.pdf)

In classical continuum mechanics, the strain tensor is found by symmetrising $\nabla \delta \mathbf{u}$. That is $\epsilon = (\nabla \delta \mathbf{u} + \nabla \delta \mathbf{u}^T)/2$. The $+$ there is basically the group action of the translation group. So is there a way to generalise this to a general group $G$? 

### Generalised continuum mechanics

We consider a Cartan media configuration $q : M \to \mathbb{X}$. To generalise the virtual work principle, we consider the "response" of a virtual displacement field $\delta q : M \to T \mathbb{X}$ and its differential $d \delta q : TM \to TT \mathbb{X}$ and time-derivative $\delta \dot{q} : TW \to TT \mathbb{X}$, similarly to how $\delta \mathbf{u}$, $\nabla \delta \mathbf{u}$ and $\delta \dot{\mathbf{u}}$ appeared in (1).

Let $\left(, \right)$ denote the contraction of a covector and a vector. So if we have $v : M \to T\mathbb{X}$ and $\alpha : M \to T^* \mathbb{X}$, then $\left( \alpha, v \right)$ is a scalar on $M$ (that is, it is a map $M \to \mathbb{R}$). This goes for vectors and covectors in the double tangent and codouble tangent bundles as well. So if $w : M \to TT\mathbb{X}$ and $\beta : M \to T^* T\mathbb{X}$, then $\left( \beta, w \right)$ is a scalar.

Let $\mathcal{T}$ be a $T^* \mathbb{X}$-valued volume form on $M$, we extend the notation so that for any $v : M \to T \mathbb{X}$ we have that $\left( \mathcal{T}, v\right)$ is an $\mathbb{R}$ volume form on $M$. If we introduce coordinates $u^\alpha : M \to \mathbb{R}$ on $M$, then we may write $\mathcal{T}$ as

$$
\mathcal{T} = \mathcal{T}^0 dV
$$

where $\mathcal{T}^0 : M \to T^* \mathbb{X}$, which transforms as a scalar density of weight $1$ and $dV = du^1 \wedge \dots \wedge du^d$, which transforms as a tensor density of weight $-1$. We then have that

$$
\left( \mathcal{T}, v \right) = \left( \mathcal{T}^0, v \right) dV
$$

Now, let $\mathcal{Q}$ be a $T^* T \mathbb{X}$-valued $(d-1)$-form on $M$, and let

$$
d\bar{u}^\alpha = du^1 \wedge \dots \wedge du^{\alpha-1} \wedge \dots \wedge du^{\alpha+1} \wedge \dots \wedge du^d
$$

then $d \bar{u}^\alpha \wedge d u^\alpha$ is equal to $dV$ up to sign. So absorb that sign into $d \bar{u}^\alpha$ such that $d \bar{u}^\alpha \wedge d u^\alpha = d V$.

In coordinates, let

$$
\mathcal{Q} = \mathcal{Q}^\alpha d\bar{u}^\alpha
$$

Now, let $w$ be a $TT \mathbb{X}$-valued $1$-form on $M$. In coordinates we write it as $w = w_\alpha d u^\alpha$. We then define the wedge contraction as

$$
\left( \mathcal{Q} \wedge w \right) = \left( \mathcal{Q}^\alpha, w_\alpha \right) d \bar{u}^\alpha \wedge du^\alpha
$$

We can then finally write down a generalisd virtual work principle

$$
\int_M \left( \mathcal{T}, \delta q \right)  = 
\int_M \left( \mathcal{Q} \wedge d(\delta q) \right) -
\int_M \left( \mathcal{S} , \delta \dot{q} \right)
$$

where we have ommitted the generalised surface traction for now.

### The lift

Let $\eta : M \to \mathfrak{g}$ such that $\delta q = \eta q$. So we have that $\left( \mathcal{T}^0, \delta q \right) = \left( \mathcal{T}^0, \eta q \right)$. We thus have a map $\mathfrak{g} \to \mathbb{R}$, defined by $\eta \mapsto \left( \mathcal{T}^0, \eta q \right)$. This is a dual Lie algebra field $T : M \to \mathfrak{g}^*$. We can thus write the contraction of $T$ and $\eta$ as 

$$
\langle T, \eta \rangle = \left( \mathcal{T}^0, \eta q \right)
$$

We define the corresponding $\mathfrak{g}^*$-valued volume-form as $\bar{T} = T dV$.

In a [previous note](https://hackmd.io/JFZVFPmFRDud6W2AbdyMsw) we saw that $dq = \xi^R q$. We thus have that $d (\delta q) = \delta \xi^R q$. So

$$
(\mathcal{Q} \wedge d(\delta q)) = \langle \bar{Q}^R \wedge \delta \xi^R \rangle
$$

Now, let $\delta \xi^R = \text{Ad}_\Phi \delta \xi^L$ and $\bar{Q}^R = \text{Ad}^*_\Phi \bar{Q}^L$. Since $\langle A, Y \rangle = \langle \text{Ad}^*_g A, \text{Ad}_g Y \rangle$ we can write

$$
(\mathcal{Q} \wedge d(\delta q)) = \langle \bar{Q}^L \wedge \delta \xi^L \rangle
$$

Similarly, as $\delta \dot{q} = \delta N^R q$ we have that

$$
(\mathcal{S}, \delta \dot{q}) = \langle \bar{S}^R, \delta N^R \rangle = \langle \bar{S}^L, \delta N^L \rangle
$$

We thus have

$$
\int_M \langle \bar{T}, \eta \rangle = \int_M \langle \bar{Q}^L \wedge \delta \xi^L \rangle - \int_M \langle \bar{S}^L, \delta N^L \rangle
$$

Dropping the L's we have

$$
\int_M \langle \bar{T}, \eta \rangle = \int_M \langle \bar{Q} \wedge \delta \xi \rangle - \int_M \langle \bar{S}, \delta N \rangle
$$

:::warning
Note that $\xi$ here is not defined over the kinematic base space $W = [0,T] \times M$, but rather just $M$.
:::

In components, we can write

$$
\begin{aligned}
\bar{Q} & = Q^\alpha d\bar{u}^\alpha \\
\xi & = X_\alpha du^\alpha
\end{aligned}
$$

We then have

$$
\int_M \langle T, \eta \rangle dV = \int_M \langle Q^\alpha , \delta X_\alpha \rangle dV - \int_M \langle S, \delta N \rangle dV
$$

Compare this to the expression we have in the paper

![image](https://hackmd.io/_uploads/SybRdBpJ0.png)


### Cosserat systems

We have $\mathbf{r} : M \to \mathbb{E}^3$ and $\mathbf{e}_i : M \to T \mathbb{E}^3$. We also write $q = (\mathbf{r}, E) : M \to OF(\mathbb{E}^3)$, where $OF(\mathbb{E}^3)$ is the orthonormal frame bundle.

Consider virtual displacement fields $\delta \mathbf{r} : M \to T\mathbb{E}^3$ and $\delta \mathbf{e}_i : M \to TT \mathbb{E}^3$. Collectively, we have that $\delta q : M \to TOF(\mathbb{E}^3)$.

Each of the virtual displacements will give rise to a generalised body force volume form, generalised stress $(d-1)$-form, as well as a generalised momentum volume form. Each of these will act on the virtual displacements to form a scalar volume form on $M$.

Let us first consider the body force. Let $\boldsymbol{\mathcal{f}}$ be a $T^* \mathbb{E}^3$-valued volume form on $M$, then $\boldsymbol{\mathcal{f}} \cdot \delta \mathbf{r}$, where $\cdot$ is the Euclidean inner product, is a scalar volume form on $M$.

Let $\boldsymbol{\mathcal{m}}$ be a $T^*T \mathbb{E}^3$-valued volume-form on $M$. Then $\boldsymbol{\mathcal{m}} \cdot \delta \mathbf{e}_i$ is a scalar volume form on $M$ for each $i$.

Now we move on to the stress. We need a $(d-1)$-form $\boldsymbol{\mathcal{F}}$ that contracts and wedges with $\delta \mathbf{r}$ to get a scalar volume form on $M$. In coordinates, we may write

$$
\boldsymbol{\mathcal{F}} = \boldsymbol{\mathcal{F}}^\alpha d\bar{u}^\alpha
$$

where $d\bar{u}^\alpha$ is defined such that $d\bar{u}^\alpha \wedge du^\alpha = dV$, and where $dV = du^1 \wedge \dots \wedge du^d$. We also write

$$
d(\delta \mathbf{r}) = \delta \boldsymbol{\theta}^s_\alpha du^\alpha
$$

We can then define the wedge inner product

$$
\boldsymbol{\mathcal{F}}\ \hat{\cdot}\ d(\delta \mathbf{r}) = \boldsymbol{\mathcal{F}}^\alpha \cdot \delta \boldsymbol{\theta}_\alpha d \bar{u}^\alpha \wedge d u^\alpha = \boldsymbol{\mathcal{F}}^\alpha \cdot \delta \boldsymbol{\theta}_\alpha dV
$$

Similarly, let $\boldsymbol{\mathcal{M}}$ be a $(d-1)$-form that contracts and wedges with $\delta \mathbf{e}_i$ to get a scalar volume form $\boldsymbol{\mathcal{M}}\ \hat{\cdot}\ \delta \mathbf{e}_i$ on $M$, for each $i$. 

Finally, let $\boldsymbol{\mathcal{P}}$ and $\boldsymbol{\mathcal{L}}$ be volume forms on $M$ that contracts with $\delta \dot{\mathbf{r}}$ and $\delta \dot{\mathbf{e}}_i$ to form scalar volume forms on $M$.

We can now write down the virtual work principle

$$
\begin{aligned}
\int_M \boldsymbol{\mathcal{f}} \cdot \delta \mathbf{r} + \sum_i
\int_M \boldsymbol{\mathcal{m}} \cdot \delta \mathbf{e}_i =
\int_M \boldsymbol{\mathcal{F}}\ \hat{\cdot}\ d\delta \mathbf{r} + 
\sum_i \int_M \boldsymbol{\mathcal{M}}\ \hat{\cdot}\ d\delta \mathbf{e}_i \\
-\int_M \boldsymbol{\mathcal{P}} \cdot \delta \dot{\mathbf{r}} - 
\sum_i \int_M \boldsymbol{\mathcal{L}} \cdot \delta \dot{\mathbf{e}}_i
\end{aligned}
$$


### Note about vector-valued forms

Let $E$ a vector-bundle with base-space $M$ and $\pi : E \to M$. We denote the space of $E$-valued $p$-forms as $\Omega^p(M, E)$.

Though a seemingly obscure object, the vector-valued $p$-form is fairly easy to understand. For each $x \in M$, a regular $1$-form on $M$ yields a linear map $T_x M \to \mathbb{R}$. An $E$-valued $1$-form on $M$ correspondingly yields a map $T_xM \to F_x$, where $F_x = \pi^{-1}(x)$ is the fiber at $x \in M$. A vector-valued $p$-form yields an antisymmetric linear map $T_x M \times \underbrace{\dots}_{p \text{ times}} \times T_x M \to E$ at each $x \in M$.

If the vector bundle is trivial, as is the case for Cartan media, the situation is simpler still. Cartan media configurations are sections on the fiber bundle $M \times \mathbb{X}$. Velocities and deformation fields on Cartan media are sections on $M \times T \mathbb{X}$. Body forces are sections on $M \times T^* \mathbb{X}$.

:::info
$M \times T \mathbb{X}$ is the *vertical bundle* of the trivial fiber buncle $M \times \mathbb{X}$, which which we write as $V(M \times \mathbb{X}) = M \times T \mathbb{X}$.
:::

Now, consider a $T \mathbb{X}$-valued $1$-form $\omega$ on $M$. At each $x \in M$, $\omega_x$ is a linear map $\omega_x : TM \to T \mathbb{X}$. If $u^\alpha$ are coordinates on $M$ then we can expand it as
$$
\omega = \omega_\alpha du^\alpha
$$

where $\omega_\alpha : M \to T \mathbb{X}$ are sections on $M \times T \mathbb{X}$. For any vector-field $v = v^\alpha \frac{\partial}{\partial u^\alpha}$ on $M$, we have

$$
\omega(v) = \omega_\alpha v^\beta du^\alpha( \frac{\partial}{\partial u^\beta}) = \omega_\alpha v^\beta \delta^\alpha_\beta = \omega_\alpha v^\beta
$$


where $\omega_\alpha v^\beta$ is now a section on $M \times T \mathbb{X}$.


#### The wedge product

Let us go back to the vector bundle $E$. The wedge product of a $E$-valued $p$-form with a $E$-valued $q$-form is a  $E \otimes E$-valued $(p+q)$-form.

So $p=q=1$ for example, and we have $\omega = \omega_\alpha du^\alpha$ and $\upsilon = \upsilon_\alpha du^\alpha$, then

$$
\omega \wedge \upsilon = (\omega_\alpha \otimes \upsilon_\beta) du^\alpha \wedge du^\beta
$$

#### The wedge contraction

In the virtual work principle, we need to wedge and then contract covector-valued $(d-1)$-forms with vector-valued $1$-forms.

Consider a $T^* \mathbb{X}$-valued $1$-form $\omega$ and a $T \mathbb{X}$-valued $1$-form $\upsilon$. Their wedge product is 

$$
\omega \wedge \upsilon = (\omega_\alpha \otimes \upsilon_\beta) du^\alpha \wedge du^\beta
$$

For each $\alpha,\beta$, we have that $\omega_\alpha \otimes \upsilon_\beta$ is a rank-$2$ tensor. That is, for each $x \in M$ we have a map $(\omega_\alpha \otimes \upsilon_\beta)_x : T \mathbb{X} \times T^* \mathbb{X} \to \mathbb{R}$. The $(1,1)$-contraction of this tensor, which yields a scalar on $M$, is given by $(\omega_\alpha, \upsilon_\beta) \in C^\infty(M)$.

So this leads us to define the wedge contraction

$$
(\omega \wedge \upsilon) = (\omega_\alpha, \upsilon_\beta) du^\alpha \wedge du^\beta
$$

such that $(\omega \wedge \upsilon)$ is now a regular $\mathbb{R}$-valued $2$-form on $M$.