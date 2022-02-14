# Polytropes

## The Polytopic Relation

We will assume that the entropy $S$ is constant in our polytope. When this is the case, we can write down:

$$
P = K \rho^\gamma
$$

Different $\gamma$ will approximate different stellar opacities. $K$ is a constant at all radii. We will plug these in (in gory detail) to our equations. 

Recall:

```{admonition} Hydrostatic Equilibrium

$$
\frac{dP}{dr} = -\rho \frac{GM}{r^2}
$$

```

```{admonition} Mass Continuity

$$
\frac{dM_r}{dr} = 4\pi r^2 \rho 
$$

```

We will now play some mathematical tricks. Going to HE:

$$
\frac{r^2}{\rho} \frac{dP}{dr} = -G M_r
$$

Differentiate both sides:

$$
\frac{d}{dr}\left(\frac{r^2}{\rho}\frac{dP}{dr}\right) = - 4\pi G r^2 \rho
$$

We have two unknowns in this equation, and so we invoke the polytope:

$$
P = K \rho^\gamma = K \rho^{1+1/n}
$$

where $n$ is the **polytopic index.** 

##### A side note

We have done this before! A **relativistic, Fermi gas** (Neutron stars, WDs), we have $n=3$ and $\gamma=\frac43$. Similarly, **non-relativistic, Fermi gas** has $n=\frac32$ and $\gamma =\frac53$ (fully convective stars, giant planets). 


##### Back to Polytropes


Let's define dimensionless variables:

$$
\boxed{\rho = \rho_c \theta^n}
$$

$$
\boxed{P = P_c \theta^{n+1}}
$$
$$
\boxed{r = \alpha \xi}
$$

Here, $\rho_c$ is the central density, $P_c$ is the central pressure, $\alpha$ is some length constant, and $\xi$ is a dimensionless radius-like quantity. Note that:

$$
\boxed{\alpha^2 = \frac{K(n+1) \rho_c^{\frac{1-n}{n}}}{4\pi G}}
$$

We can thus re-write our polytrope differential equations in these dimensionless units, giving us the **Lane-Emden equation**:

$$
\frac{1}{r^2}\frac{d}{dr}\left(\frac{r^2}{\rho}\frac{dP}{dr}\right) = -4\pi G\rho \rightarrow \boxed{\frac{1}{\xi^2}\frac{d}{d\xi}\left(\xi^2 \frac{d\theta}{d\xi}\right) = - \theta^{n}}
$$

We will solve this for $\theta(\xi)$, and thus we need boundary conditions to solve this. What are these boundary conditions?


#### Boundary Conditions

* $\theta\vert_{\xi=0} = 1$. (central pressure is the central pressure)
* $\frac{d\theta}{d\xi}\vert_{\xi=0} = 0$. (continuity across the core)


#### Solving The Equation

There are only three analytic solutions to this equation.


```{admonition} n = 0

$$
\theta(\xi) = 1 - \frac{\xi^2}{6}
$$

where $\xi_{max} = \sqrt{6}$.

Here, we assume that the pressure is not related to the density -- an incompressible fluid! We find this where $\rho = \rho_c$, or things like Earth's interior. 

```

```{admonition} n = 1

$$
\theta(\xi) = \frac{\sin\xi}{\xi}
$$

where $\xi_{max}=\pi$. 

```

```{admonition} n = 5

$$
\theta(\xi) = \left(1+\frac{\xi^2}{3}\right)^{-1/2}
$$


where $\xi_{max} = \infty$.

```

Any time that $n>5$, $\xi_{max} = \infty$.  Stars tend to live in between $n=1$ and $n=5$. 


#### Numerical Solutions

A solution for $n=1.5$ is a pretty good approximation for a fully convective star. The Sun is most closely approximated by $n=3$ polytopes. 

For a given $n$, we need two constants:

* $K$ and $\rho_c$.

If we are given those two things, polytopes allow us to give you back $M$, $R$, $\rho(r)$, $L(r)$, $T(r)$, etc. 


#### Other Useful Polytope Information

Here are some useful relations coming from the Lane-Emden equation.

$$
R = \alpha \xi_{max} = \left(\frac{K(n+1)}{4\pi G}\right)^{1/2} \rho_c^{\frac{1-n}{2n}}\xi_{max}
$$

$$
M = \int_0^{R} 4\pi r^2 \rho(r) \, \mathrm{d}r = 4\pi \alpha^3 \rho_c \int_0^{\xi_{max}} \xi^2 \theta^n \mathrm{d}\xi = 4\pi \left(\frac{K(n+1)}{4\pi G}\right)^{3/2} \rho_c^{\frac{3-n}{2n}} \left(-\xi^2 \frac{d\theta}{d\xi}\right)\Bigg\vert_{\xi_{max}}
$$

We can combine the two equations (with something like $R^{(3-n)/n} \cdot M^\frac{n-1}{n}$):

$$
R^{\frac{3-n}{n}} M^{\frac{n-1}{n}} = \underbrace{\frac{K}{GN_n}}_\text{const} \rightarrow \boxed{M \propto R^{\frac{n-3}{n-1}}}
$$



Let's examine our two reference points.

1\. $n=1.5$ Polytrope: A Fully Convective Star

$$
RM^{1/3} = \frac{K}{0.42 G}
$$


2\. $n=3$ Polytrope: The Sun

$$
M = \frac{K}{0.36 G}
$$



We can thus get other quantities, like the **central density**:

$$
\rho_c = \frac{3M}{4\pi R^3} a_n \text{ where } a_n\equiv \frac{-\xi}{3\left(\frac{d\theta}{d\xi}\vert_{\xi=\xi_{max}}\right)}
$$

The **central pressure**:

$$
P_c = \frac{4\pi G \rho_c^2 \alpha^2}{n+1} = c_n \frac{GM^2}{R^4}
$$

And, lastly, $T_c$, for an ideal gas:

$$
T_c = \frac{\mu}{\mathcal{R}}\frac{P_c}{\rho_c} = b_n \frac{\mu}{\mathcal{R}}\frac{GM}{R}
$$

note that $a_n$, $b_n$, and $c_n$ are constants where tables exist!


#### An Example

Can we write $L$ and $T_{eff}$ for a polytrope?

We should get:

$$
T_{eff} \propto M^{1/7} R^{1/49}
$$

(weakly radius dependendent) for a modified H- opacity. If we do luminosity, we find:

$$
L = M^{4/7} R^{102/49}
$$

**Plugging in with numbers, we find, for a fully convective star:**:

$$
T_{eff} = 2400 \text{ K } \left(\frac{M}{M_\odot}\right)^{1/7} \left(\frac{R}{R_\odot}\right)^{1/49}
$$


