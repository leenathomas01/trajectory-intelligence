# Reachability Cones

## Definition

The Reachable State Space from state $\mathbf{z}(t_0)$ over time horizon $\Delta t$ is:

$$\mathcal{R}(\mathbf{z}(t_0), \Delta t) = \{ \mathbf{z}(t_0 + \Delta t) \mid \mathbf{z}(t_0 + \Delta t) \text{ is achievable under system dynamics and available controls} \}$$

This set forms a cone-like structure in the latent manifold, expanding forward in time from the current state. Its geometry encodes the system's future possibilities.

## Cone Geometry

The reachability cone has several critical geometric properties:

### Width (Option Density)
The volume of $\mathcal{R}$ at a given time horizon. A wide cone means many distinct futures remain accessible. A narrow cone means the system's options are constrained.

### Asymmetry (Directional Bias)
Whether the cone extends equally toward recovery and degradation futures, or is biased. Asymmetric cones — wide toward degradation, narrow toward recovery — indicate a system that can easily get worse but struggles to improve.

### Contraction Rate
How quickly $\text{vol}(\mathcal{R}(\mathbf{z}, \Delta t))$ changes as the system evolves:

$$\frac{d}{dt}\text{vol}(\mathcal{R}) < 0 \implies \text{reachability collapse in progress}$$

Rapid contraction is the system-level signature of approaching irreversibility.

### Boundary Distance
The minimum distance from the current trajectory to the edge of the cone. Systems near the boundary are one perturbation away from losing entire classes of futures.

## Computation

Exact reachability computation is generally intractable in high dimensions. Practical approaches include:

- **Linearized approximation**: Propagate the reachability set using the linearized system dynamics (Jacobian), producing an ellipsoidal approximation.
- **Sampling-based**: Monte Carlo sampling of trajectories under different intervention strategies, estimating the reachable set empirically.
- **Hamilton-Jacobi methods**: Level-set approaches that compute reachable set boundaries by solving a partial differential equation backward in time.

## Connection to Resilience

The volume and geometry of the reachability cone formalize the intuitive concept of resilience:

- **Resilient system**: Wide cone, symmetric, slow contraction, trajectory far from boundaries.
- **Fragile system**: Narrow cone, asymmetric toward degradation, rapid contraction, trajectory near boundaries.
- **Collapsing system**: Cone degenerating to a single trajectory — the system has lost all options and is locked into a deterministic path.

## Open Problems

- What are efficient approximation methods for reachability cone computation in high-dimensional learned manifolds?
- Can reachability cone geometry be made differentiable for integration into gradient-based optimization (reachability loss functions)?
- How should reachability cones be computed for systems with stochastic dynamics, where the boundary is probabilistic rather than deterministic?
