# Phase Transitions

## Core Idea

A Phase Transition is the moment a system undergoes a sudden, often irreversible shift from one mode of operation to another. In the Trajectory Intelligence framework, detecting these transitions *before they occur* is the most critical capability — and the primary justification for trajectory-level modeling.

Phase transitions are dangerous precisely because they are discontinuous. A system can operate within normal parameters for an extended period, showing no degradation in snapshot-based metrics, and then collapse abruptly. The transition itself is fast; the approach to the transition is slow and geometrically detectable.

## Critical Slowing Down

The universal precursor signature of phase transitions is Critical Slowing Down: as a system approaches a tipping point, its ability to recover from perturbation degrades progressively.

Observable indicators:

- **Recovery time increases**: The system takes longer and longer to return to baseline after disturbance (Recovery Gradient → 0).
- **Variance increases**: Fluctuations around the baseline grow wider and more erratic.
- **Autocorrelation increases**: The system's state becomes increasingly correlated with its recent past — it loses the ability to "forget" perturbations.
- **Oscillation amplitude grows**: The system begins swinging through wider arcs, overshooting baseline on both sides.

These indicators are mathematically identical whether the system is biological, financial, organizational, or physical. The topology of approach-to-collapse is domain-invariant.

## The Mathematical Signature

Near a tipping point, the dominant eigenvalue of the system's Jacobian approaches zero. In trajectory terms:

- The attractor basin becomes shallower (weaker restoring force).
- The system's trajectory takes longer to curve back toward the attractor center.
- The curvature $\kappa$ of the World-Line near the attractor decreases.
- The Reachability Cone contracts asymmetrically, with recovery pathways narrowing faster than degradation pathways.

## Why Snapshots Miss Phase Transitions

A snapshot-based system monitors whether current values are within normal ranges. But the *values* are often the last thing to change before a phase transition. What changes first is the *dynamics*: recovery slows, variance grows, correlations shift. These are trajectory-level properties that are structurally invisible to any single-observation classifier.

## Cross-Domain Examples

| Domain | Phase Transition | Precursor Signal |
|---|---|---|
| Biology | Cardiac fibrillation | Progressive lengthening of QT recovery intervals |
| Markets | Flash crash | Widening bid-ask spreads, increasing autocorrelation in price movements |
| Ecology | Ecosystem desertification | Slower vegetation recovery after drought, increasing spatial correlation |
| Organizations | Institutional failure | Increasing response time to incidents, growing variance in delivery timelines |
| AI Systems | Mode collapse during training | Declining gradient diversity, increasing weight autocorrelation |

## Connection to Other Concepts

- Phase transitions are detected through changes in [World-Line](world_lines.md) geometry — specifically, declining curvature near attractor centers and increasing trajectory divergence.
- The [Recovery Gradient](recovery_gradient.md) approaching zero is the primary quantitative indicator of an approaching phase transition.
- Phase transitions represent the sudden, discontinuous contraction of [Reachability](reachability.md) — the moment when entire classes of future states become permanently inaccessible.
- [Trajectory Compression](trajectory_compression.md) must be designed to preserve the subtle variance and autocorrelation changes that constitute phase transition precursors.

## Open Questions

- Are there universal topological signatures that precede phase transitions across all complex systems, or are precursor patterns domain-specific?
- Can phase transition precursors be detected in systems where the underlying dynamics are not stationary?
- What is the theoretical earliest detection horizon — how far in advance of a transition can Critical Slowing Down be reliably distinguished from noise?
- Can intervention vectors be computed that not only steer away from tipping points but actively deepen attractor basins to increase distance from future transitions?
