# Energy Transport in Stars


## Radiation Transport

Consider a hot material (say, inside a star), with some boundary, and more gas on the other side of the boundary. The gas interior emits photons, some of which crossing the boundary. The gas outside the boundary is slightly cooler, and still emitting photons.

How do we describe the photons and where they go? Because we have a temperature gradient, the photons are flowing from interior to exterior the boundary. We can think of this movement as a diffusion – in reality, **it is not the same photon random walking, but we will treat it as such.**

### Radiative Transfer Refresher

We care about two basic properties of the photons and the material:

* Intensity of the radiation
* Matter opacity (absorbativity/transparency).

We can define our specific intensity $I(\theta)\mathrm{d}\theta$, where $\theta$ is the direction of radiation and $\mathrm{d}\Omega$ is the solid angle over which the photon is emitted:

$$
I(\theta) = \frac{\text{erg}}{\text{s cm}^2 \text{ str Hz}}
$$

We want to relate our flux to our specific intensity:


$$
F = \int I \cos\theta \mathrm{d}\Omega = \int_0^{2\pi} \int_{0}^{\pi} I(\theta, \phi)\cos\theta \cdot \sin\theta \mathrm{d}\theta\mathrm{d}\phi
$$

#### Absorption

What we really care about is the actually observed flux, and we must account for the opacity $\kappa$:

$$
\kappa = \frac{\text{cm}^2}{g}
$$

You can think of this as a **per-mass cross section.**

We can write our equation of radiative transfer thus us:

$$
\mathrm{d}I = -I \kappa \rho \mathrm{d}s
$$

The initial intensity is modulated by the opacity and the thickness.

We can solve:

$$
\boxed{I = I_0 e^{-\kappa \rho s}}
$$

We will commonly see something called $\tau \equiv \kappa \rho s$, which is the **optical depth**. 


#### Emission

What happens if our slab is actually emitting more than it absorbs? We have some slab emission rate $j_\nu$. Note that:

$$
[j_\nu] = \frac{\text{ergs}}{\text{s cm}^3 \text{ sr Hz}}
$$

This modifies our radiation equation and we instead have:

$$
\frac{\mathrm{d}I}{\mathrm{d}s} = - I \kappa \rho + j
$$

Often, we see:

$$
\boxed{\frac{dI}{d\tau} = - I + S \text{ where } j_\nu \equiv \frac{j}{\kappa \rho}}
$$

## A Treatment of Stars

We are now talking about slabs at a radius $r$ from the center of the star in the direction $\hat z$. The slab thickness is thus $dz$. We have:

$$
\frac{dI(z,\theta)}{ds} = \frac{\cos\theta \cdot \mathrm{d}I(z,\theta)}{\mathrm{d}z}
$$

Note we are implicitly assuming that the density is constant here, which in exotic cases, is not true. 

So....how the hell do we progress?  Let's

* Assume a blackbody at tempertature $T \rightarrow$ we can say that the source function is uniform in all directions (locally). Note that the lower the mass, and the cooler the star, the more this assumption breaks down. This gives us, where $S(T)$ is the Planck Fucntion, that:

$$
I(z,\theta) = S(T) - \frac{\cos\theta}{\kappa \rho}\frac{\mathrm{d}I(z,\theta)}{\mathrm{d}z}
$$

* Note that we can solve this equation by assuming that $I(z,\theta) = B(T) + \underbrace{\epsilon I(z,\theta)}_\text{small perturbation}$. Fundamentally, after treating this as a perturbation, we end up with:

$$
H_\nu = \int I(z,\theta)\cos\theta \mathrm{d}\Omega = \int \left(B(T) - \frac{\cos\theta}{\kappa \rho} \frac{dB(T)}{dz}\cos\theta \right)\mathrm{d}\Omega
$$

$$
H_\nu = \int \left(\underbrace{B(T)}_\text{integral goes to 0} - \frac{\cos\theta}{\kappa \rho} \frac{dB(T)}{dz}\cos\theta \right)\mathrm{d}\Omega
$$
$$
H_\nu = -\frac{2\pi}{\kappa \rho} \frac{dB(T)}{dz}\int_0^\pi \cos^2\theta \sin\theta \mathrm{d}\theta
$$


This becomes:

$$
H_\nu = -\frac{4\pi}{3\kappa \rho} \frac{dB(T)}{dz} = -\frac{4\pi}{3\kappa\rho}\frac{\partial B}{\partial T}\frac{\partial T}{\partial z}
$$


And the total flux is thus:

$$
H = -\frac{4\pi}{3\rho} \frac{\partial T}{\partial z} \int_0^\infty \frac{1}{\kappa}\frac{\partial B(T)}{\partial T}\mathrm{d}\nu
$$

Note that the integral is **nasty.** The opacity is a **WILD FUNCTION** of quantum mechanics, resonances, etc. Almost always, things like MESA hide the complexity of microphysics in the integral. 

We want to hide this nastiness, and how do we make this tractable? Let's define a quantity called the **Rosseland Mean Opacity** $\kappa_R$ such that:

$$
\frac{1}{\kappa_R} \equiv \frac{\int_0^\infty \frac{1}{\kappa}\frac{\partial B(T)}{\partial T}\mathrm{d}\nu}{\int_0^{\infty} \frac{\partial B(T)}{\partial T} \mathrm{d}\nu} = \frac{\pi}{4\sigma T^3}\int_0^\infty \frac{1}{\kappa}\frac{\partial B(T)}{\partial T}\mathrm{d}\nu
$$

This can be thought of as a mean transparency, or so, and often ignore the complex treatments underneath. This is normally fine for stuctures, but not for specific spectra in atmospheres. When we do this, we can go back to the **total flux per unit area of a shell from a star**:

$$
\boxed{H = -\frac{16\sigma T^3}{3\kappa_R \rho}\frac{\partial T}{\partial z}}
$$
What we actually observe is integrated over the full sphere:

$$
\boxed{L(r) = -4\pi r^2 \frac{16 \sigma T^3}{3\kappa_R \rho}\frac{dT}{dz}}
$$

