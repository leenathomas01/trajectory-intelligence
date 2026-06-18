# Intervention Vectors

## Definition

An intervention vector $\mathbf{I}$ is an input applied to a system that modifies its trajectory through the latent manifold. Inverse Intervention Modeling computes the minimal such vector required to redirect a trajectory from its current path toward a target destination.

## Formal Statement

Given a current trajectory $\mathbf{\Gamma}_{actual}$ and a target trajectory $\mathbf{\Gamma}_{target}$, the optimal intervention is:

$$\mathbf{I}_{min} = \arg\min_{\mathbf{I}} \|\mathbf{I}\| \quad \text{subject to} \quad \mathbf{\Gamma}_{actual} + \mathbf{I} \rightarrow \mathbf{\Gamma}_{target}$$

The norm $\|\mathbf{I}\|$ encodes intervention cost — which may reflect energy expenditure, financial cost, organizational disruption, or side-effect magnitude depending on domain.

## Control Surfaces

Not all dimensions of a system's state are controllable. Control surfaces are the subset of variables or pathways within the system that are receptive to external input. The effective intervention space is constrained to the tangent directions accessible through these surfaces:

$$\mathbf{I} \in \mathcal{C} \subseteq T_{\mathbf{z}}\mathcal{M}$$

where $\mathcal{C}$ is the control-accessible subspace of the tangent space at the current state.

## Properties of Good Interventions

- **Minimal magnitude**: Smallest input that achieves the desired trajectory correction.
- **Non-disruptive**: Does not destabilize other system dimensions or trigger unintended phase transitions.
- **Timely**: Applied when the system is still in a reversible state space with sufficient reachability.
- **Targeted**: Acts on specific control surfaces rather than blanket system-wide adjustments.

## The Inverse Problem

Traditional forward modeling asks: given intervention $\mathbf{I}$, what trajectory results?

Inverse Intervention Modeling reverses this: given a desired trajectory change, what intervention achieves it?

This is generally ill-posed — multiple interventions may achieve similar trajectory corrections. The minimality constraint selects the least costly among them. Additional constraints (smoothness, bounded rate of change, compatibility with system physics) further regularize the solution.

## Open Problems

- How should the cost norm $\|\mathbf{I}\|$ be defined across domains where intervention costs are heterogeneous and non-commensurable?
- Can intervention vectors be composed — applying multiple small interventions sequentially rather than one large intervention?
- How should uncertainty in the system model propagate to uncertainty in the computed intervention vector?
