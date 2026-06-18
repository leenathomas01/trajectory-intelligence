# Attractor Basins

## Definition

An attractor basin $\mathcal{A} \subset \mathcal{M}$ is a region of the latent manifold toward which trajectories converge under the system's natural dynamics. A system displaced from the attractor center experiences a restoring force — quantified by the Recovery Gradient — that pulls it back.

## Formal Properties

An attractor basin is characterized by:

- **Center** $\mathbf{z}^*$: The equilibrium point where the system is at rest (or in a stable limit cycle).
- **Depth**: The magnitude of the restoring force at a given displacement from center. Deeper basins produce stronger Recovery Gradients.
- **Width**: The range of displacements from which the system can still return to center. Defines the basin of attraction boundary.
- **Symmetry**: Whether the restoring force is uniform in all directions or asymmetric (e.g., stronger resistance to degradation in one dimension than another).

## Basin Geometry and Stability

The Jacobian matrix $\mathbf{J}$ of the system dynamics evaluated at $\mathbf{z}^*$ determines local basin geometry:

$$\mathbf{J} = \frac{\partial \mathbf{f}}{\partial \mathbf{z}}\bigg|_{\mathbf{z}^*}$$

- All eigenvalues of $\mathbf{J}$ with negative real parts → stable attractor (system returns after perturbation).
- Any eigenvalue approaching zero → basin is shallowing in that direction → approaching phase transition.
- Eigenvalue crossing zero → bifurcation — the attractor may split, disappear, or become unstable.

## Homeostatic Regret

The Homeostatic Regret axis measures the distance $\mathcal{D}$ between the system's current state and its attractor center:

$$\mathcal{D}(t) = d(\mathbf{z}(t), \mathbf{z}^*)$$

Critically, this is measured against the system's *personal* historical optimum, not a population average. Two systems may have different attractor centers — what matters is each system's distance from its own.

## Basin Transitions

When a system crosses the boundary of one attractor basin and enters another, it undergoes a phase transition — a potentially irreversible shift to a new operating regime. The trajectory will now converge toward a different center, and the original attractor may no longer be reachable.

This is why Reachability analysis focuses on attractor basin boundaries: ensuring the system's trajectory remains well within its current basin, with intervention vectors available to counteract drift toward the boundary.

## Open Problems

- How can attractor basin geometry be estimated from trajectory data alone, without access to the system's governing equations?
- Can basin depth and width be estimated non-invasively from Recovery Gradient measurements?
- How should multi-scale attractor structures (basins within basins) be represented and navigated?
