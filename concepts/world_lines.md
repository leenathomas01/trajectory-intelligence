# World-Lines

## Core Idea

A World-Line is the continuous path traced by a system as it evolves through a high-dimensional latent manifold over time. Borrowed from relativistic physics (where it describes the trajectory of an object through spacetime), the concept is generalized here to represent any complex system's evolution through its state space.

## Why World-Lines, Not Time Series

Traditional time-series analysis treats sequential observations as a list of values indexed by time. A World-Line treats the same data as a geometric object — a curve with intrinsic properties:

- **Velocity** ($\mathbf{v}_{latent} = \frac{d\mathbf{X}}{dt}$): How fast and in what direction the system's internal state is shifting.
- **Acceleration** ($\mathbf{a}_{latent} = \frac{d^2\mathbf{X}}{dt^2}$): Whether the rate of change is itself changing — revealing forces or stressors before they manifest in observable outputs.
- **Curvature** ($\kappa$): How sharply the trajectory bends, indicating the strength of attractor pull or the onset of instability.
- **Divergence** ($\nabla \cdot \mathbf{\Gamma}$): Whether nearby trajectories are spreading apart (instability) or converging (stability).

The shift from "list of values" to "geometric curve with physics" is what makes trajectory-level reasoning possible.

## The Representation

Let a system's state at time $t$ be:

$$\mathbf{X}(t) \in \mathbb{R}^D$$

The World-Line is the parameterized curve:

$$\mathbf{\Gamma} = \{\mathbf{X}(t) \mid t \in [t_0, t_n]\}$$

This curve lives in a latent manifold — typically a learned embedding space where proximity encodes functional similarity, not just spatial adjacency.

## Cross-Domain Instantiation

| Domain | What the World-Line Tracks |
|---|---|
| Biology | Tissue compliance, vascular flow, metabolic state evolving across months/years |
| Markets | Portfolio exposure, liquidity depth, and correlation structure shifting through economic cycles |
| Organizations | Team velocity, communication topology, and decision latency drifting over quarters |
| Infrastructure | Material stress, vibrational modes, and thermal profiles evolving under load |
| AI Training | Weight distributions, internal activations, and capability profiles across training steps |

## Connection to Other Concepts

- A World-Line's **curvature** near an attractor basin connects to [Reachability](reachability.md) — tighter curvature means stronger pull toward a particular future.
- The **velocity** of a World-Line under stress connects to [Recovery Gradient](recovery_gradient.md) — faster snap-back velocity after perturbation signals higher adaptive capacity.
- **Divergence** between parallel World-Lines is the precursor signal for [Phase Transitions](phase_transitions.md).
- The challenge of representing World-Lines efficiently is the subject of [Trajectory Compression](trajectory_compression.md).

## Open Questions

- What is the minimum sampling frequency required to reconstruct World-Line curvature with sufficient fidelity for phase transition detection?
- Can World-Lines from different domains be embedded into a shared manifold, enabling cross-domain transfer of trajectory patterns?
- How should World-Lines be tokenized for consumption by transformer architectures?
