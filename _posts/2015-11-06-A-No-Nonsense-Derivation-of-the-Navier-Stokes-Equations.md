---
layout: page
title:  "A no-nonsense derivation of the Navier-Stokes equations"
---

Most of what follows are key arguments expounded by Rutherford Aris, Landau and Lifshitz, and Richard Feynman.

The roadmap for the derivation is as follows:

1) Clarify what is meant by "velocity of a fluid at a point in space".

2) Derive the Reynolds Transport Theorem.

3) Develop the form of the stress tensor for a Newtonian Fluid.

Warning: A preliminary understanding - if not appreciation - of vector calculus, including tensors, is required to _get_ whats about to follow. Here are some relevant chapters from Feynman's Lectures:

[Differential Calculus of Vector Fields](http://www.feynmanlectures.caltech.edu/II_02.html)

[Vector Integral Calculus](http://www.feynmanlectures.caltech.edu/II_03.html)

[Tensors](http://www.feynmanlectures.caltech.edu/II_31.html)

-----------------------------------------------------------

We begin with the question, "How does one mathematically describe fluid flow?". Since we have calculus at our disposal, we could describe the motion of Infinitesimal Fluid Packets (henceforth IFPs) and then integrate the resulting equation of motion to get their trajectories. These trajectories will be a function of space and time. There are two ways we can do this:

#View-1 
When looking at a fluid flow, you focus on an IFP and say "This IFP originated from \\(\vec{\xi\_1}\\), this IFP originated from \\(\vec{\xi\_2}\\), this one from \\(\vec{\xi\_3}\\) ..." and so on. At a later time \\(t\\), you'd say something like "The IFP that originated from \\(\vec{\xi\_1}\\) has moved a distance \\(\vec{dr\_1}\\), the IFP that originated from \\(\vec{\xi\_2}\\) has moved a distance \\(\vec{dr\_2}\\), the IFP that originated at \\(\vec{\xi\_3}\\) has moved a distance \\(\vec{dr\_3}\\) ..." and so on. This way, you're keeping track of all the particles , albeit individually, and thus describing the fluid flow evolution in time.

#View-2
The other way to do this is to look at the entire fluid flow at once. Take a snapshot of it. Attach to it some convenient spatial coordinate system. Say that at some \\(\vec{x\_1}\\) the fluid velocity is \\(\vec{v\_1}\\), at some \\(\vec{x\_2}\\) the velocity is \\(\vec{v\_2}\\), at some \\(\vec{x\_3}\\) the velocity is \\(\vec{v\_3}\\) and so on. Then at a later time \\(t\\), you take another snapshot of the same domain, affix the same convenient coordinate system and say something like "at \\(\vec{x\_1}\\) the velocity of the fluid has changed by some \\(\vec{dv\_1}\\), at \\(\vec{x\_2}\\) the velocity of the fluid has changed by some \\(\vec{dv\_2}\\), at \\(\vec{x\_3}\\) the velocity has changed by some \\(\vec{dv\_3}\\)."

-----------------------------------------------------------

View-1 seems to ask "Where is that IFP going?" while View-2 asks "How is this picture of the flow going to change?"[^1]. When studying the dynamics of rigid bodies, we always followed particles around. \\(\vec{F}=m\vec{a}\\) was referring to the acceleration of a particle (View-1), not the position in space at which the velocity was changing (View-2), which is nonsense because the particle can only occupy one point in space (or at most a finite portion of it) at any given time. What velocity and acceleration could we possibly ascribe to empty points in space?! But for fluids, or more generally for continuous media, we don't run into this problem. In our domain of interest, every point in space is *occupied* so every one of these points can be ascribed properties like velocities, accelerations, densities, pressures, temperatures, entropies, concentrations, vorticities, etc. "But how can a point, the teeniest-tinyest imaginable point, have any mass?!" you demand. Indeed, when considering a point in space, chances are that it is occupied more by vacuum than anything else. The points we're considering in the case of fluids are points which are fairly large. Large enough to comprise \\(10^{15}\\) molecules and upwards. Large enough to have a mass per unit volume. Large enough to have a mean temperature. Large enough to have molecules colliding with one another to exert pressure on any area upon which they impinge. If your points are any smaller than this, you are guaranteed nonsense, atleast if you choose to use the framework we're developing. You would be describing regions in space molecules may or may not have arrived at. What we're doing in fluid mechanics is zooming out so that everything looks nice and continuous and not bumpy and discrete. And since we're looking to transform from points in space (View-2) to following IFPs (View-1), our IFPs are also to be thought of as being large enough to contain \\(10^{15}\\) particles, large enough to have a mass per unit volume and so on. Of course, we don't want our points (or IFPs) to be too large either; we'd lose the resolution we desire to examine important phenomena like diffusion! Similar arguments apply to time. We are describing flow over time-scales much larger than the time-scales of thermal equilibration. Only then can we ascribe to our fluid various thermodynamic properties. Probing into timescales shorter than this leads once again to absurdities[^2].

View-1 and View-2 are equivalent. The laws of Fluid Physics should not change depending on which description you choose. But we need both views. View-2 is convenient for calculations, but View-1 is what we've been trained in since high school. So we should learn how to transform all relevant physical quantities from one view to another.

View-1: If \\(\vec{\xi}\\) is the initial position of an IFP, the property \\(\psi\\) of the IFP can be denoted as

$$ \psi = \psi(\vec{\xi},t) $$

Each IFP originates at some \\(\vec{\xi\_i}\\) where \\(i\\) can take values from 1 to \\(\infty\\)! That's what our continuum approximation entails. Finite domain; Infinite number of IFPs. That's where the I in IFP comes from. Since the initial position of any particle is a continuous function of space, we can write

$$ \vec{\xi} = \vec{\xi}(\vec{x},t) $$

This simply says that all initial positions of IFPs belong somewhere. Remember that functions are always answers to questions. Here the question goes something like "which IFP is located at position \\(\vec{x}\\) and time \\(t\\)?". Answer: "\\(\vec{\xi}\\)!" You must think of \\(\vec{\xi}\\) as taking on an infinite number of values! That isn't a problem as long as we can associate each of these values to a position in space. Analytically, this means the transformation matrix (also called the Jacobian matrix \\(\tilde{J}\\)) is non-singular everywhere:

$$ \vec{dx} = \tilde{J}\vec{d\xi} $$

This matrix \\(\tilde{J}\\) maps every initial position of an ISP to every point on the domain uniquely.

View-2: Every point in space is occupied by some IFP. Therefore every point in space can be ascribed a property \\(\psi\\) such that

$$ \psi = \psi(\vec{x},t) $$

So \\(\psi\\) is a function of space and time! At a given point in space and time, this \\(\psi\\) had better be equal to the \\(\psi\\) we would get in View-1, i.e. the value of a property at some point is equal to the value of the property of the IFP at that point!

$$ \psi(\vec{x},t) = \psi[\vec{\xi}(\vec{x},t),t] $$

The converse is equally true:

$$ \psi(\vec{\xi},t) = \psi[\vec{x}(\vec{\xi},t),t] $$

We're finally in a position to say what we mean by a time derivative. Let's reserve unique symbols for each case first: Let \\(\frac{d}{dt}\\) be the time derivative of a quanitity keeping \\(\vec{\xi}\\) constant. Let \\(\frac{\partial}{\partial t}\\) be the time derivative of a quanitity keeping \\(\vec{x}\\) constant.

Lo and behold, the velocity of an IFP:

$$ \vec{u} = \frac{d\vec{x}}{dt} $$

It's worth repeating what this means! By keeping \\(\vec{\xi}\\) constant while taking the derivative of the location \\(\vec{x}\\) of the IFP with respect to time, we're making sure that we're tracking that IFP and that IFP alone!

Now, since we know
$$ \psi(\vec{\xi},t) = \psi[\vec{x}(\vec{\xi},t),t] $$
to be true, we proceed taking time derivatives as follows:

$$ \frac{d\psi}{dt}(\vec{\xi},t) = \frac{\partial\psi}{\partial t}[\vec{x}(\vec{\xi},t),t] $$
Apply the chain rule:
$$ \frac{d\psi}{dt} = \frac{d\vec{x}}{dt}\cdot\nabla\psi+ \frac{\partial\psi}\{\partial t} $$
$$ \frac{d\psi}{dt} = \vec{u}\cdot\nabla\psi+ \frac{\partial\psi}\{\partial t} $$

This was the transformation rule we've been trying to articulate. This is just what we need to derive a very important theorem due to Reynolds. Note that \\(\nabla\\) is the gradient operator. \\(\nabla\psi\\) is a vector and each component is its derivative in its corresponding direction. 

Onward.

-----------------------------------------------------------

#The Transport Theorem of Reynolds

Imagine an IFP located initially at some \\(\vec\{\xi}\\). Let's say this IFP moves to some location \\(\vec{x}\\) over the course of some small time \\(dt\\). This IFP's volume, initially \\(V\_0\\), is given by the cross-product \\(|d\vec{\xi\_1}\times d\vec{\xi\_2}\times d\vec{\xi\_3}|\\). At a later time, this IFP's volume could have changed owing to some compression, expansion or concentration change. This volume \\(dV\\) is given by \\(|d\vec{x\_1}\times d\vec{x\_2}\times d\vec{x\_3}|\\). We've already seen that 

$$ \vec{d\xi} = \tilde{J}\vec{dx} $$

Therefore the relationship between the old and new volumes is

$$ dV = |\tilde{J}|dV\_0 $$
where \\(|\tilde{J}|\\) is the determinant of the Jacobian Matrix. Now, how does this ratio of volumes change in time; what is \\(\frac\{d|\tilde{J}|}{dt}\\)?

The determinant \\(|\tilde{J}|\\) looks like this:
$$ \begin{vmatrix}
\frac{\partial x\_1}{\partial \xi\_1}  & \frac{\partial x\_1}{\partial \xi\_2} & \frac{\partial x\_1}{\partial \xi\_3} \\\ 
\frac{\partial x\_2}{\partial \xi\_1}  & \frac{\partial x\_2}{\partial \xi\_2} & \frac{\partial x\_2}{\partial \xi\_3} \\\
\frac{\partial x\_3}{\partial \xi\_1}  & \frac{\partial x\_3}{\partial \xi\_2} & \frac{\partial x\_3}{\partial \xi\_3}
\end{vmatrix} $$

While taking its time derivative, keep two things in mind:

1) $$ \frac{d}{dt}\frac{\partial x\_i}{\partial\xi\_i} = \frac{\partial}{\partial \xi\_i}\frac{dx\_i}{dt} = \frac{\partial u\_i}{\partial\xi\_i} $$
We were able to interchange the derivatives because \\(\frac{d}{dt}\\) keeps \\(\vec{\xi}\\) constant.

2) Since \\(\vec{u}\\) is a function of \\(\vec{x}\\), we can write
$$ \frac{\partial u\_i}{\partial\xi\_j} = \frac{\partial u\_i}{\partial x\_1}\frac{\partial x\_1}{\partial\xi\_j} +
					  \frac{\partial u\_i}{\partial x\_2}\frac{\partial x\_2}{\partial\xi\_j} +
					  \frac{\partial u\_i}{\partial x\_3}\frac{\partial x\_3}{\partial\xi\_j} $$

We then get

$$ \frac{d|\tilde{J}|}{dt} = |\tilde{J}|\nabla\cdot\vec{u} $$
or
$$ \nabla\cdot\vec{u} = \frac{dln(|(\tilde{J}|)}{dt} $$

Hence, we find that the divergence of the velocity tells us how much an IFP is changing volume. When it is zero, we say the flow is incompressible. 

Now we're ready to derive the indispensable Reynolds Transport Theorem. We wish to find the time derivative of an integral this time. Namely

$$ \Psi(t) = \oint\_{V(t)} \psi(\vec{x},t) dV $$

Here, we've integrated over a bunch of IFPs whose volumes are allowed to change in time. How are we to take the time derivative \\(\frac{d}{dt}\\) (keeping \\(\vec{\xi}\\) constant) of this? We're not allowed to bring the derivative inside the integral since \\(dV\\) itself changes with time. But, as luck may have it...


$$ \frac{d\Psi}{dt} = \frac{d}{dt}\oint\_{V(t)}\psi(\vec{x},t) dV $$
$$	           = \frac{d}{dt}\oint\_{V(t)}\psi |\tilde{J}|dV\_0 $$
$$	           = \oint\_{V(t)}\frac{d}{dt} (\psi |\tilde{J}|) dV\_0 $$
$$	           = \oint\_{V(t)}\left(|\tilde{J}|\frac{d}{dt}\psi + \psi\frac{d}{dt}|\tilde{J}|\right)dV\_0 $$
$$	           = \oint\_{V(t)}\left(\frac{d}{dt}\psi + \psi\nabla\cdot\vec{u}\right)|\tilde{J}|dV\_0 $$
$$	           = \oint\_{V(t)}\left(\vec{u}\cdot\nabla\psi+ \frac{\partial\psi}\{\partial t} + \psi\nabla\cdot\vec{u}\right)|\tilde{J}|dV\_0 $$
$$	           = \oint\_{V(t)}\left(\frac{\partial\psi}\{\partial t} + \nabla\cdot\psi\vec{u}\right)dV $$

This result is useful as it stands, but we can do better and express this in terms of fluxes. Apply Green's Theorem on the divergence term to get:

$$ \frac{d}{dt}\oint\_{V(t)} \psi(\vec{x},t) dV  = \oint\_{V(t)} \frac{\partial\psi}{\partial t} dV + \oint\_{S(t)}\psi\vec{u}\cdot\hat{n}dS $$

There it is. And like most things simple, it is very powerful. In words, it says that the rate of change of the volume integral of a quantity (i.e. an integral over some continuum of IFPs), is equal to the volume integral of how quickly that quantity is changing in time and the surface integral of the rate at which the quanitity is entering said IFPs (we call this _flux_). Here \\(S(t)\\) is the instantaneous surface area of the volume considered and \\(\hat{n}\\) is a local unit normal vector to the infinitesimal surface element \\(dS\\). Having integral relationships between quanitites is useful because they're more generally applicable. Sometimes, the local details of a phenomenon might remain elusive; for instance, the events in a shock wave. Even if our continuum assumptions, i.e. our differential equations break down at the shock wave, our integral relations will still hold!

As a first application of the theorem, we can derive the conservation of mass. If \\(\rho\\) is the density of an IFP,

$$ \frac{d}{dt}\oint\_{V} \rho(\vec{x},t) dV  = \oint\_{V} \frac{\partial\rho}{\partial t} dV + \oint\_{S(t)}\rho\vec{u}\cdot\hat{n}dS = 0$$
$$	           \oint\_{V}\left(\frac{\partial\rho}\{\partial t} + \nabla\cdot\rho\vec{u}\right)dV  = 0 $$

If an integral is necessarily zero everywhere, it is sufficient if its integrand is zero everywhere as well. Therefore,
$$	           \frac{\partial\rho}\{\partial t} + \nabla\cdot\rho\vec{u}  = 0 $$

The Reynolds Transport Theorem has set us on the right track. We will henceforth think of rates of change exclusively in terms of fluxes and volume integrals. If we feel the need for a differential equation, we'll apply Green's theorem to convert fluxes to divergences.

-----------------------------------------------------------

#The Stress Tensor

For a continuum of IFPs, we can apply Newton's second law like so:

Rate of change of momentum = Body Forces + Surface Forces

Body forces are volumetric things and act on the mass of the fluid. Like gravity, or if the fluid is charged, electric fields. We always define such forces per unit volume. Surface forces act on surfaces and we define them per unit area. We call them stresses. Their origin is in the actions of molecules (duh, everything is!). Pressure for instance is the rate of momentum transferred to a unit area via molecular collisions in a gas. Shear stress, microscopically, is fast molecules transferring momentum to slow molecules via molecular collisions. Whenever an IFP deforms, mechanical forces (pressure) and thermal forces (viscosity) tend to "reform" the IFP, i.e. restore it to equilibrium. The equation of words written above can be written symbolically as:

$$ \frac{d}{dt}\oint\_{V(t)} \rho\vec{u} dV  = \oint\_{V(t)} \rho\vec{f} dV + \oint\_{S(t)}\vec{t\_{(n)}}dS $$

This is not Reynolds' Transport Theorem! This is just Newton's second law! Something important emerges immediately when it is written this way. If you shrink the volume of the continuum over which the integrals are taken down to that of an IFP, the surface integral goes to zero for a \\(d^2\\) vs \\(d^3\\) related reason. This means that the surface forces are in local equilibrium for an IFP. This is another way to say that our idealized IFPs correspond to a volume of fluid in real life whose size is so small, that the forces acting on its surface are in mechanical equilibrium. We can make use of this fact in deriving the so called _stress tensor_.

For the time-being, imagine a 2-dimensional square shaped IFP (because it's easier to draw). If we cut this square across the diagonal, we have a nice right angled triangle with three edges. There is a force acting on each of these edges, but they must all add up to zero. If \\(dl\\) is the length of the hypotenuse, and \\(dl\_1\\) and \\(dl\_2\\) are the lengths of the perpendicular edges, and the force per unit length or _length_ stress is \\(vec{t}\\),

$$ \vec{t\_{(n)}}dl - \vec{t\_1}dl\_1 - \vec{t\_2}dl\_2  = 0 $$

<img src = "{{ site.url }}/public/images/triangle_vectors.png"\>

Here, the signs of the forces are an artefact of the coordinate system. You should get the right signs as long as you're consistent with the directions of your forces relative to the surface normals. Here, all forces are pointing outside the triangle. To be more precise, since the ratios of the the length of a perpendicular to the hypotenuse is a component of the normal vector to the hypotenuse, we can write 

$$ \vec{t\_{(n)}} = \vec{t\_1}|n\_1| + \vec{t\_2}|n\_2|  $$

Remember that \\(\vec{t\_1}\\) and \\(\vec{t\_2}\\) are vectors which are, in general,  allowed to point in any direction (we've only constrained what their sum must be). It would make sense to resolve the components of these vectors in the \\(\hat{n\_1}\\) and \\(\hat{n\_2}\\) directions. If \\(t\_{n\_1}\\) and \\(t\_{n\_2}\\) are the components of the left hand side force in these directions, we can write:

$$ \begin{pmatrix}
t\_{n\_1} \\\
t\_{n\_2}
\end{pmatrix}  = 
\begin{pmatrix}
T\_{11} & T\_{12} \\\
T\_{21} & T\_{22} \\\
\end{pmatrix} 
\begin{pmatrix}
n\_1 \\\
n\_2
\end{pmatrix} 
$$

The right hand side is the dot product between a tensor and a vector so we can write the above more compactly as

$$ \vec{t\_{(n)}} = \tilde{T}\cdot\vec{n} $$

 or - even better - in index notation[^3] as

$$ t\_i = T\_{ij}n\_j $$

We can forget about the triangle we cut from our 2d square shaped IFP now! Everything we've written is coordinate system independent! The left hand side comprises the components of an arbitrary stress over an arbitrary area of an IFP. The right hand side is a linear combination of the components of the normal vector to this area. The weights appearing in this linear combination are the components of a tensor. All this generalizes easily to the three dimensional case, where \\(\tilde{T}\\) becomes a nine-component tensor. This makes sense; in order to express the components of a force acting per unit area of an IFP (cube shaped), and keeping in mind that that force must be related to the forces over the other areas of the cube because the IFP must be in mechanical equilibrium, the total number of components in the tensor is nine (the cube has nine surfaces).

$$ \begin{pmatrix}
t\_{n\_1} \\\
t\_{n\_2} \\\
t\_{n\_3}
\end{pmatrix}  = 
\begin{pmatrix}
T\_{11} & T\_{12}  & T\_{13} \\\
T\_{21} & T\_{22}  & T\_{23} \\\
T\_{31} & T\_{32}  & T\_{33} \\\
\end{pmatrix} 
\begin{pmatrix}
n\_1 \\\
n\_2 \\\
n\_3
\end{pmatrix} 
$$

There is a compelling reason for why this stress tensor needs to be symmetric. Consider any two perpendicular surfaces of our IFP, say surfaces with normals \\(\hat{n\_1}\\) and \\(\hat{n\_2}\\). Then, the forces on the two surfaces are respectively

$$ T\_{11}\hat{n\_1} + T\_{12}\hat{n\_2} + T\_{13}\hat{n\_3} $$
$$ T\_{21}\hat{n\_1} + T\_{22}\hat{n\_2} + T\_{23}\hat{n\_3} $$

If \\(T\_{12}\\) is not equal to \\(T\_{21}\\), our IFP should begin to spin due to the torque set up by these imbalanced forces. Although we stated that the sum of the forces had to equal zero to assure mechanical equilibrium, that wasn't entirely true; the sum of the torques need to equal zero as well! If not, our IFPs would all be spinning, infinitely fast in fact, because if even the slightest torque were set up, the moment of inertia, being zero for an IFP, would be compensated for by an infinite angular acceleration. Since we're staying clear of such ridiculousness, we must insist that the torque set up by the surface forces on the IFP is zero [^4]. This information is contained in the fact that the stress tensor is symmetric. This does not mean that our IFP cannot have a vorticity which is defined as \\(\nabla\times\vec{u}\\). Newton's second law for our IFP in terms of the stress tensor looks like:

$$ \frac{d}{dt}\oint\_{V(t)} \rho\vec{u} dV  = \oint\_{V(t)} \rho\vec{f} dV + \oint\_{S(t)}\tilde{T}\cdot\hat{n}dS $$

Using the Reynolds Transport Theorem, it becomes

$$ \oint\_{V(t)} \frac{\partial(\rho\vec{u})}{\partial t}dV  \oint\_{S(t)}\rho\vec{u}\otimes\vec{u}\cdot\hat{n}dS = \oint\_{V(t)} \rho\vec{f} dV + \oint\_{V(t)}\nabla\cdot\tilde{T}dV $$

Upon applying Green's Theorem,

$$ \oint\_{V(t)} \left(\frac{\partial}{\partial t}\rho\vec{u} + \nabla\cdot(\rho\vec{u}\otimes\vec{u})\right) dV  = \oint\_{V(t)} \rho\vec{f} dV + \oint\_{V(t)}\nabla\cdot\tilde{T}dV $$

Which means,

$$ \frac{\partial}{\partial t}\rho\vec{u} + \nabla\cdot(\rho\vec{u}\otimes\vec{u}) = \rho\vec{f} + \nabla\cdot\tilde{T} $$

We need to express the components of the stress tensor in terms of the velocity field to close the problem. The concepts are directly inspired by studies in solid mechanics. There, a solid experiences stress only if it is strained, i.e. somehow deformed from its equilibrium configuration. In fluid mechanics, an IFP is strained when different portions of it are moving at different velocities, thus causing deformation. We accounted for deformation already by insisting that \\(dV = |\tilde{J}|dV\_0\\). But this deformation will set up internal stress in the fluid; IFPs will feel surface forces due to this deformation. Let's first consider the simple case in which there is no velocity, i.e. the fluid is static. In that case, whatever \\(\nabla\cdot\tilde{T}\\) is, it is balanced by the body forces:

$$ \nabla\cdot\tilde{T} = -\rho\vec{f} $$

The stress tensor has to be isotropic, i.e. its components must not change if we rotate our coordinate system. The components of the body forces certainly change for they have directionality associated with them. The stress tensor however doesn't because all it is allowed to depend on are the velocities, which are zero everywhere! So it ought to look like this:

$$ T\_{ij} = -P\delta\_{ij} $$

\\(\delta\_{ij}\\) is trivially isotropic. In matrix notation, it is the identity matrix:

$$ \tilde{\delta} = 
\begin{pmatrix}
1 & 0 & 0 \\\
0 & 1 & 0 \\\
0 & 0 & 1 \\\
\end{pmatrix}
$$

\\(P\\) is what we call _pressure_ and it is a scalar. The minus sign we've stuck in front of it is only a convenience. Therefore, our force law for hydrostatics becomes:

$$ \nabla P = \rho\vec{f} $$

If \\(\vec{f}\\) is the acceleration due to gravity \\(\vec{g}\\), we get the familiar looking relationship between pressure and height. Assuming our coordinate system's z axis lines up with the direction of \\(\vec{g}\\), we integrate once to get

$$ P = P\_{0} + \rho g h $$

What about the case in which the velocities are non-zero? Here we make the following hypotheses:

1) The stress tensor should be modified by adding to another tensor to the one derived above. We do this so that in the limiting case of no velocities, we get the right expression back. So,

$$ T\_{ij} = -P\delta\_{ij} + \sigma\_{ij} $$

2) \\(\sigma\_{ij}\\) must depend on first derivatives of velocity. This is a statement in phenomenology. Since the deformation of IFPs is caused by velocity gradients, it is quite reasonable to express the stresses as being proportional to these. There are parallels beyond those in solid mechanics. In the subject of heat transfer, we learn that the energy flux is proportional to the gradient of the temperature. In mass transfer, the species flux is proportional to the gradient of the concentration. If we keep with this linear themed phenomenology, we will require the momentum flux to be proportional to the velocity gradient as well.

3) The dependence on velocity gradients cannot be arbitrary but must occur as exactly two possible combinations: \\(\frac{\partial u\_{i} }{\partial x\_{j} } + \frac{\partial u\_{j}}{\partial x\_{i}}\\) and \\(\frac{\partial u\_l}{\partial x\_l}\\). Let's discuss the sum first. Consider a 2-d plane in which an IFP is moving. Suppose it is rotating about some axis such that its speed is proportional to its distance from the axis \\(\vec\{r}\\), we can say that it is rotating like a rigid body. The condition \\(\vec{u}=\vec{r}\times\vec{\omega}\\) is derived specifically under the constraint that no part of the body deforms. Hence the descriptive "rigid". So if our IFP is undergoing rigid body rotation, it must not deform. If it does not deform, it is not stressed. The combination \\(\frac{\partial u\_{i} }{\partial x\_{j} } + \frac{\partial u\_{j}}{\partial x\_{i}}\\) reduces to zero in just such a case.  The second combination \\(\frac{\partial u\_i}{\partial x\_i}\\) is the only other possible combination left. Therefore,

$$ \sigma\_{ij} = a \left(\frac{\partial u\_{i} }{\partial x\_{j} } + \frac{\partial u\_{j}}{\partial x\_{i}}\right) + b\frac{\partial u\_l}{\partial x\_l}\delta\{ij} $$

4) To figure out what how a and b are, we invoke a rather controversial hypothesis made by Stokes. The components of the stress tensor \\(T\_{11}\\), \\(T\_{22}\\), and \\(T\_{33}\\) are quite significant. The trace, which is the sum of these three components, is an invariant of the tensor, meaning that under any coordinate system rotation, the trace of the transformed tensor will remain unchanged. The trace is denoted \\(T\_{ii}\\). The mean stress is therefore given by

$$ \langle T\rangle  = \frac{1}{3}T\_{ii} $$
$$  	  = -P + \frac{1}{3}\sigma\_{ii} $$
$$	 = -P + \frac{1}{3}\left(2a\frac{\partial u\_i}{\partial x\_i} + 3b\frac{\partial u\_l}{\partial x\_l}\right) $$
$$	 = -P +\left(\frac{2}{3}a + 3b\right)\frac{\partial u\_l}{\partial x\_l} $$

Stokes hypothesized that the mean stress experienced by an IFP must only be proportional to \\(P\\) and nothing else. He is saying that the average force felt by any unit area of an IFP is solely due to the local thermodynamic pressure. In such a case,

$$ \frac{2}{3}a + b = 0 $$
or
$$ b = -\frac{2}{3}a $$

We replace '\\(a\\)' with \\(\mu\\) and call it the _dynamic viscosity_. It must always be positive to guarantee entropy increase. Thus

$$ \sigma\_{ij} = \mu \left(\frac{\partial u\_{i} }{\partial x\_{j} } + \frac{\partial u\_{j}}{\partial x\_{i}} -\frac{2}{3}\frac{\partial u\_l}{\partial x\_l}\delta\_{ij} \right)$$

It has been shown in many experiments that the hypothesis of Stokes breaks down when acoustic phenomena like sound absorption, or the high velocity divergence that accompanies hypersonic flows are significant. We therefore remedy this by correcting the hypothesis like so

$$ \frac{2}{3}\mu + b = \kappa $$
or
$$ b = \kappa - \frac{2}{3}\mu$$

This \\(\kappa\\) is called the bulk viscosity. It too is confined to positive values for the sake of the second law of Thermodynamics.

-----------------------------------------------------------

We can now write the full Navier-Stokes Equations. In index notation they are written as,

$$ \frac{\partial(\rho u\_i)}{\partial t} + \frac{\partial(\rho u\_i u\_j)}{\partial x\_j} = \rho f\_i + \frac{\partial (T\_{ij})}{\partial x\_j} $$
where
$$ T\_{ij} = -P\delta\_{ij} + \mu \left(\frac{\partial u\_{i} }{\partial x\_{j} } + \frac{\partial u\_{j}}{\partial x\_{i}} -\frac{2}{3}\frac{\partial u\_l}{\partial x\_l}\delta\_{ij} \right) + \kappa\frac{\partial u\_l}{\partial x\_l}\delta\_{ij} $$

In vector notation,

$$ \frac{\partial}{\partial t}\rho\vec{u} + \nabla\cdot(\rho\vec{u}\otimes\vec{u}) = \rho\vec{f} + \nabla\cdot\tilde{T} $$
where

$$ \tilde{T} = -P\tilde{\delta} + \mu\left((\nabla\vec{u}) + (\nabla\vec{u})^T - \frac{2}{3}\nabla\cdot\vec{u}\right) + \kappa\nabla\cdot\vec{u} $$

There we have it! There is much to comment on these equations, but I'll leave that for another post. 

I've heard many call the NS equations ugly. I think they're particularly beautiful. Look at all the considerations that had to be made so we could mathematically articulate fluid flow! Isn't the result inspiring? It sure is to me! 

#Footnotes

[^1]: View-1 is popularly known as the "Lagrangian" view point. View-2 is called "Eulerian" everywhere. These names obstruct understanding, which is why I have avoided using them. No disrespect intended of course.

[^2]: Such arguments are formally made in the subject of statistical mechanics where the name of the game is to basically prove the laws of thermodynamics, those undeniable constraints on all macroscopic phenomena, by combining the properties of atoms and the laws of microscopic motion via some sexy results from probability theory. Beholding its results truly takes the breath away!

[^3]: If you're unfamilair with index notation, I strongly insist that you learn it. Two rules to never forget:1) Conservation of indices: All free indices that appear on the left hand side must appear on the right hand side. 2) Repeated indices denote taking a product and summing over all permissable values of the index. In 2d for instance \\(a\_ib\_i = a\_1b\_1 + a\_2b\_2\\).

[^4]: All this only applies to Newtonian non-polar fluids. If the fluid is non-polar, there can be an internal angular momentum set up and we will need to supplement our equations with the conservation of angular momentum. The NS equations don't apply to these.
