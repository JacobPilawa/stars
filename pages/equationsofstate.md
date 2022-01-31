# Virial Theorem and the Equation of State

## Virial Theorem

* This is basically the energy form of hydrostatic equilibrium:

$$
\frac{dP}{dr} = -\frac{Gm(r) \rho(r)}{r^2}
$$

We will multiply by $\frac43 \pi r^3$ and integrate:

$$
\int \frac43 \pi r^3 \frac{dP}{dr} \mathrm{d}r = -\int \frac{Gm(r)\rho(r)}{r^2} \frac43 \pi r^3 \, \mathrm{d}r
$$

What do we integrate? Pressures on the left, and radii on the right.


$$
\int_{P_{center}}^{P_{surface}} \frac43 \pi r^3 \frac{dP}{dr} \mathrm{d}r = -\int_{0}^{R} \frac{Gm(r)\rho(r)}{r^2} \frac43 \pi r^3 \, \mathrm{d}r
$$

Replacing $dm$ Integrating the right hand side:

$$
\mathrm{d}m = 4\pi r^2 \, \mathrm{d}r \rho(r)
$$
$$
-\frac{1}{3}\int  \frac{GM}{r}\mathrm{d}m  = \frac13 \Omega, 
$$

**where $\Omega$ is the gravitational potential energy.** Note that we absorbed the negative sign based on the definition of gravitational potential.  

What about the left hand side? We need to consider the pressure at the center and the surface. We have with integration by parts:

$$
\frac43 \pi r^3 P\Bigg|_{center}^{surface} - \int_0^R P \cdot \frac43 \pi r^2 \mathrm{d}r
$$


What does this equation mean? We have a volume times a pressure in the first term, and this whole term (either pressure or volume) causes this term to go to zero. The second term is the same thing as a volume integral of pressure:

$$
-\int_0^{V_{surface}} P \mathrm{d}V \equiv -\langle P \rangle V
$$

We can now combine the left and right hand sides:

$$
-\frac13 \Omega = -\langle P \rangle V \rightarrow \boxed{\Omega = -3 \langle P \rangle V}
$$

We often see the virial theorem written as:

$$
\boxed{\Omega = -2K}
$$
It is really easy to measure the kinetic energy of systems, making this equation really powerful! 


There are some things to remember:

* $\Omega < 0$.
* Total Energy is composed of $E_{tot} = K + \Omega$ 



#### Application of the Virial Theorem

##### Problem 1

Problem: A gas cloud (assume Jeans unstable). What happens when the cloud radiates a bit of heat away?

Assume equilibrium:

$$
\frac13 \Omega = -P V 
$$

Since we are not losing mass, the gravitationa pressure increases. The cloud tries to restore equilibirum. To do this, the internal temperature has to increase. 

$$
U = -\frac35 \frac{GM^2}{R}
$$

Basically, the sequence goes as follows: 

1. Lose energy: $L$ gets radiated away. This causes the total energy to decrease, and the absolute value of energy increases. 
2. As a result, $K$ has to increase, and thus so does $T$. 
3. We then loop around, and we keep gaining temperture until $T$ gets hot for fusion.


##### Problem 2

What is the difference between a bomb and a star?

1. For stars, $M$ is big enough.
2. Remember that gravitational potentail energy is negative, so the radius is increasing until the temperature settles back down. 
3. For a bomb, the everything happens so quickly that it overcomes the potential energy holding the bomb togther. 
4. Beforehand, we were viralized. After, we are super virialized, and we have an explosion!

##### Problem 3

How do we estimate the temperature of the center of a star?

$$ 
\boxed{T = \frac{GMm_p}{Rk} }
$$


## Equations of State

### Radiation Dominated Example

What if we are out of the ideal gas regime? Let's examine some non-ideal equations of state!

1\. Blackbody Photon Energy Density $\mathcal{E}$: 

$$
\mathcal{E} = a T^{4} 
$$

From the virial theorem:
$$
P = \frac13 \mathcal{E} 
$$

Let's assume hydrostatic equilibrium:

$$
P_{rad} = -\frac13 \frac{\Omega}{V} \rightarrow  P = \frac13 \frac{GM}{r } \rho
$$

If our pressure is dominated by photons, we can equate these pressures. 

$$
aT^4 = \frac{1}{3} \frac{GM}{r} \rho
$$

Also remember:

$$
\frac{kT}{\mu m_P} = \frac{GM}{3R} \rightarrow \boxed{T = \frac{GM \mu m_p}{3k_bR}}
$$

Pluggin this in just as we become super virial, we have:

$$
a \left(\frac{GM \mu m_p}{3k_bR}\right)^{4} \geq \frac{GM^2}{R^4}
$$

Solving this for $M$:

$$
M^2 = \frac{k^4}{aG^3 \left(\mu m_p\right)^{4}}\rightarrow \boxed{M \approx 100M_\odot}
$$

**We become radiation dominated around M>$100M_\odot$ **

A more accurate treatment gives you something like $M\sim 50M_\odot$. In this regime, stars respond fundamentally in a different way and must be treated as such. But, remember, different parts of the star can have different forms of pressure dominated. 

### Microphysics of the Equations of State

```{admonition} Equation of State

The microphysical properties of a material that tells us how to relate density $\rho$, temperture $T$, compositions $X_i$, and more, to the pressure $P(\rho, T, X_i, ...)$ and internal energy $U = U(\rho, T, X_i, ...)$. 

Given $P$ and $U$, we can determine the specific heats $C_V$ and $C_P$, adiabatic exponents $\gamma_{ad}$, adiabatic temperature gradient $\nabla_{ad}$ (convective versus radiative transport), and more. 

```


#### An Example: Ideal Gas

The equation of state we use most frequently:
$$
\boxed{P = nkT  = \frac{\rho}{\mu m_p} kT} 
$$


But, where does this come from? We must know the answer to find out when this does not apply. Everything we will cover here is in the Phillips textbook, in Chapter 2. 

### Kinetic Theory of Pressure

Where does the ideal gas equation come from? Formally, we can say (with $p$ as momentum state, $n_p(p)$ is the distribution of momenta, $\epsilon_p$ is the kinetic enegy of a particle, and $v_p$ is the velocity of the particle) the number density is:

$$
n = \int_0^\infty n_p(p) \,\mathrm{d}p
$$


The internal energy density is:

$$
U = \int n_p(p) \epsilon_p \,\mathrm{d}p = n \langle \epsilon_p \rangle
$$


The pressure is:

$$
P = \frac13 \int p v_p n_p(p) \, \mathrm{d}p
$$

$$
P = \frac13 n \langle p v_p \rangle
$$



We now need to discuss relativity! Recall that we can relate $v_p$, $p$, and $\epsilon_p$ with special relativity. The total energy $\epsilon^2$ is:

$$
\epsilon^2 = p^2 c^2 + m^2 c^4 
$$
The kinetic energy piece is:

$$
\epsilon_p = \epsilon - mc^2
$$

The velocity $v_p$ is:

$$
v_p = \frac{\partial \epsilon}{\partial p} = \frac{pc^2}{\epsilon}
$$

**The Non-Relativitic Case: **

$$
p \ll mc
$$

In this case, we have:

$$
\epsilon_p = \frac12 \frac{p^2}{m}
$$

Plugging this expression into our equations for pressure:

$$
P = \frac13 n \langle  pv \rangle  \rightarrow \langle  pv \rangle = \langle \frac{p^2}{m} \rangle = 2\langle\epsilon_p\rangle 
$$

Thus, we have:

$$
\boxed{P = \frac{2}{3} U = \frac{2}{3}\frac{u}{\rho}}
$$

where $u$ can be the internal energy per particle, whereas $U$ is the internal energy for the whole system. $U$ has units of energy per volume, whereas $u$ has units of energy per unit mass. 

---

**The Extremely-Relativistic Case:**


Here, 


$$
p \gg mc
$$

Now, we have: 

$$
\epsilon_p = pc \rightarrow v_p = c
$$

Our nasty term $\langle pv \rangle \rightarrow \langle pc \rangle$. This is the same as $\epsilon_p$. Pushing this back through, we have:


$$
\boxed{P = \frac{1}{3} U = \frac{1}{3}\rho u}
$$
We already have a factor of $2$ difference in pressure between the non-relativistic and relativistic case. 

Where do we see extremely relativistic conditions?

* Anytime we are radiation dominated, the most appropriate equation of state to use is the relativist case! 
* It turns out this is the case for both photon pressure and electron pressure. Also surprisingly true when we have ions supporting the pressure. 
* Most of the time, however, we use $P = \frac23 U$ for the equation of state. 


---


**Classical, Ideal Gas Case**

For a classical, ideal gas in **local thermodynamic equilibrium**, we can write down the Maxwell-Boltzmann distribution:

$$
n(p) \mathrm{d}p = \frac{n}{\left(2\pi mkT\right)^{3/2}} \underbrace{e^{\frac{-p^2}{2mkT}}}_{=e^{-\epsilon_p/kT}} \cdot 4\pi p^2 \mathrm{d}p
$$


The last term is the volume in momentum phase space. The first term is a normalization constant. This can also be thought of as an equilibrium state of a gas! 

This is a totally nasty equation, so how do we arrive at the ideal gas law? We plug in the non-relativistic equations we found above:

$$
v = \frac{p}{m}
$$


Plugging this in and integrating the pressure, we find:

$$
P = \frac13 \frac{1}{(2\pi m kT)^{3/2}} \int e^{-\frac{p^2}{2mkT}} 4\pi p^2 \,\mathrm{d}p
$$

Integrating, we find:

$$
\boxed{P = nkT}
$$

When is this valid?

* For non-relativistic cases. Also, however, true for "classical" relativistic particles. 

We also will typically used the mixed species equation, which is:

$$
\boxed{P = \frac{\rho}{\mu m_p} kT}
$$


---


### Quantum Treatment


#### Fermions

The limit on the number of states is set by the Pauli exclusion principle. Let's start with the fermion case (electrons, nucleons). Here, we care about the fraction of particles at energy $\mathcal{E_p}$. This leads to the **Fermi-Dirac distribution**:

$$
f_{FD}(\mathcal{E}_p): = \frac{1}{e^{\frac{\epsilon_p - \epsilon}{kT}} + 1} \leq 1
$$

where $\epsilon$ is the **"chemical potential"**. What does this  look like:


```{image} ../figures/fd.png
:alt: fig9
:width: 600px
:align: center
```



#### Bosons (photons)

Here, we have a similar result, the **Bose-Einstein distribution**:

$$
f_{BE}(\mathcal{E}_p): = \frac{1}{e^{\frac{\epsilon_p - \epsilon}{kT}} - 1} \leq 1
$$


To go from $\epsilon_p$ to $p$ is: $f_{BE} \cdot N_{allowed states}$. We start with the maximum allowed number of quantum states per volume (where $g_s$ is the max number of states per particle):

$$
\text{max number of quantum states per volume}  = g(p)\,\mathrm{d}p = g_s \frac{V}{h^3} 4\pi p^2 \, \mathrm{d}p
$$



#### Degenerate , Non-Relativistic Electron Gas

Here, we have fermions with two states (spin-up and spin-down), so $g_s = 2$. We also have fully degernate case:

$$
N_{e,p} = \frac{2V}{h^3} 4\pi p^2 \mathrm{d}p
$$

$$
n(p) \mathrm{d}p = \frac{2}{h^3} 4\pi p^2 \mathrm{d}p 
$$

$$
n = \int_0^{p_F} n(p) \mathrm{d}p = n_e
$$

where $p_F$ is the maximum allowed momentum for a fermion. Turns out that:

$$
p_F = h\left(\frac{3}{8\pi} n_e\right)^{1/3}
$$

which we can use as our integration bound.

We also want to compute the pressure. We have to do non-relativistic and relativistic here, where $v = \frac{p}{m}$:

$$
P = \frac13 \int p v n(p) \mathrm{d}p
$$

After all the algebra, we have the equation of state for a degenerate gas of electrons (fully):

$$
\boxed{P = \mathcal{K}_{NR} \left(\frac{\rho}{\mu_e}\right)^{5/3} \text{ where } n_e \equiv \frac{\rho}{\mu_e m_p}}
$$

where $\mathcal{K} = 1.0036\times 10^{13} \frac{\text{dyne}}{\text{cm}^2} \left(\frac{g}{cm^3}\right)^{-5/3}$. **This is the presure for a non-relativistic, degenerate electron gas**. The only way that we get a truly, boxy FD distribution is for $T=0$, so this is not an exact result. 


```{note}

In a normal star, we can use ideal gases. It is only at really high densities (white dwarf, neutron star, molecular parts of outer stars, SN explosions) do we have degenerate behavior/quantum behavior. 

```

#### Degenerate, Relativistic Electron Case

This is all the same, but we have to plug in $v=c$.

This gives:

$$
P_{e} = \mathcal{K}_{ER} \left(\frac{\rho}{\mu_e}\right)^{4/3}
$$

where  $\mathcal{K}_{ER} = 1.24\times 10^{15} \frac{\text{dyne}}{\text{cm}^2} \left(\frac{g}{cm^3}\right)^{-4/3}$ . 



### Plot

```{image} ../figures/eos.png
:alt: fig10
:width: 600px
:align: center
```



#### Relativistic Transition 

How do we identify the transition point between cases? Let's try to calculate $\rho$ where $p \approx m_e c \sim h \left(\frac{3}{8\pi} n_e\right)^{1/3}$ . This gives:

$$
\rho_{trans} \sim \mu_e m_p \frac{8\pi}{3} \left(\frac{m_e c}{h}\right)^{3}
$$

$$
\boxed{\frac{\rho_{trans}}{\mu_e} = 0.3\left(\frac{T}{10^{7} \text{ K}}\right)\frac{\text{g}}{\text{cm}^3}}
$$

When we are working this degenerate gas, it depends on if we have a hot or cool object! Thus, for NSs and WDs, the transition region is very different as a function of age. 




#### Degeneracy Transition FOR ELECTRONS

How do we determine the transition point from degenerate to non-degenerate? Crudely, we have:


$$
P_e = max\left(\underbrace{\frac{\rho kT}{\mu_e m_p}}_\text{thermal pressure}, \underbrace{\mathcal{K}_{NR} \left(\frac{\rho}{\mu_e}\right)^{5/3}}_\text{degeneracy pressure}\right)
$$

The  transition point is when these are both $\sim$ equal. Doing this and solving for $\rho$:

$$
\frac{\rho}{\mu_e} = \frac{\mathcal{R}}{\mathcal{K}_{NR} T}^{3/2}
$$

where $\mathcal{R} \equiv \frac{k}{m_p}$. Plugging in numbers, we have:

$$
\frac{\rho}{\mu_e} \approx 750 \frac{\text{g}}{\text{cm}^3} \left(\frac{T}{10^7 \text{ K}}\right)^{3/2}
$$
We can add this to our diagram, with an example of where WDs might fall:

```{image} ../figures/wd_eos_example.png
:alt: fig11
:width: 600px
:align: center
```



