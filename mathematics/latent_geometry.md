# Latent Geometry

## Foundations

The latent manifold is the space in which system trajectories are represented and analyzed. Its geometry — dimensionality, curvature, metric structure — determines what trajectory properties can be computed and what transitions can be detected.

## State Space

A system's state at time $t$ is a vector in a high-dimensional observation space:

$$\mathbf{X}(t) \in \mathbb{R}^D$$

In practice, the raw observation space $\mathbb{R}^D$ is too high-dimensional and too noisy for direct trajectory analysis. A learned embedding function $\phi$ maps observations into a lower-dimensional latent manifold $\mathcal{M}$:

$$\mathbf{z}(t) = \phi(\mathbf{X}(t)) \in \mathcal{M} \subset \mathbb{R}^d, \quad d \ll D$$

The trajectory is then analyzed as a curve on $\mathcal{M}$.

## Trajectory as Parameterized Curve

The World-Line is a parameterized curve on the manifold:

$$\gamma: [t_0, t_n] \rightarrow \mathcal{M}$$
$$\gamma(t) = \mathbf{z}(t)$$

### Intrinsic Properties

- **Tangent vector** (velocity): $\dot{\gamma}(t) = \frac{d\mathbf{z}}{dt}$
- **Acceleration**: $\ddot{\gamma}(t) = \frac{d^2\mathbf{z}}{dt^2}$
- **Arc length** (total displacement): $L = \int_{t_0}^{t_n} \|\dot{\gamma}(t)\| \, dt$
- **Curvature**: $\kappa(t) = \frac{\|\dot{\gamma} \times \ddot{\gamma}\|}{\|\dot{\gamma}\|^3}$

## Metric Structure

The manifold $\mathcal{M}$ is equipped with a Riemannian metric $g$ that defines distances and angles. The choice of metric determines which trajectories are considered "nearby" and how intervention costs are measured:

$$d(\mathbf{z}_1, \mathbf{z}_2) = \inf_{\gamma} \int_0^1 \sqrt{g_{\gamma(s)}(\dot{\gamma}(s), \dot{\gamma}(s))} \, ds$$

where the infimum is taken over all paths $\gamma$ connecting $\mathbf{z}_1$ and $\mathbf{z}_2$.

## The Six-Axis Decomposition

The six-axis framework (Homeostatic Regret, Viscoelastic Impedance, Metabolic Flux, Morphological Integrity, Chronobiological Velocity, Recovery Gradient) defines a structured decomposition of $\mathcal{M}$ into interpretable subspaces:

$$\mathcal{M} = \mathcal{M}_1 \times \mathcal{M}_2 \times \mathcal{M}_3 \times \mathcal{M}_4 \times \mathcal{M}_5 \times \mathcal{M}_6$$

This decomposition is illustrative rather than prescriptive. Different domains may require different axis structures, but the principle holds: the manifold should be factored into dimensions that carry distinct physical or operational meaning.

## Connection to Other Mathematical Structures

- [Attractor Basins](attractor_basins.md) are defined as regions of $\mathcal{M}$ with specific stability properties.
- [Reachability Cones](reachability_cones.md) are subsets of $\mathcal{M}$ defined by dynamics and control constraints.
- [Intervention Vectors](intervention_vectors.md) are tangent vectors on $\mathcal{M}$ that induce desired trajectory changes.
