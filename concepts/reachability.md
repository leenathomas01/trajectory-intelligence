# Reachability

## Core Idea

Reachability is the central optimization quantity of Trajectory Intelligence. It answers the question: *given where this system is and how it's moving, what futures are still physically accessible?*

Formally, the Reachable State Space is:

$$\mathcal{R}(\mathbf{X}(t_0), \Delta t) = \{\mathbf{X}(t_0 + \Delta t) \mid \mathbf{X}(t_0 + \Delta t) \text{ is achievable given system dynamics and available inputs}\}$$

This is not a prediction. It is a map of possibilities — a cone of futures, some desirable, some catastrophic, all constrained by the system's current momentum, structural limits, and available intervention surfaces.

## Why Reachability, Not Prediction

Prediction asks: *where will this system go?*

Reachability asks: *where can this system still go?*

The distinction matters because prediction collapses a distribution of futures into a single expected trajectory, discarding the very information that matters most: whether recovery pathways remain open, whether the system retains the option to change course, and how quickly those options are narrowing.

A system can have a favorable predicted trajectory while its reachability cone is collapsing — meaning it's on a good path, but has lost the ability to correct if anything changes. That's a fragile system masquerading as a healthy one.

## The Reachability Cone

```
                  /---> Future State A (Collapse Zone)
                 /
  Current Path  o-----> Future State B (Degraded Basin)
                 \
                  \---> Future State C (Optimal Valley)
             [ Reachable Future State Space ]
```

The geometry of this cone encodes several critical properties:

- **Width**: How many distinct futures remain accessible. Wide = resilient. Narrow = fragile.
- **Asymmetry**: Whether the cone is biased toward degradation or recovery. Symmetric cones indicate a system with balanced options.
- **Rate of contraction**: How quickly the cone is narrowing over time. Rapid contraction signals approaching irreversibility.
- **Boundary proximity**: How close the current trajectory is to the edge of the cone. Systems near the boundary are one perturbation away from losing entire classes of futures.

## Reachability Collapse

The most dangerous condition a system can enter is reachability collapse — the progressive elimination of recovery pathways until only degradation futures remain. This can occur gradually (a slow narrowing of the cone over months or years) or suddenly (a phase transition that eliminates an entire region of future state space).

Critically, reachability collapse is often invisible to state-based monitoring. The system's current metrics may look normal. Its predicted trajectory may look stable. But its reachability cone has already contracted to the point where no intervention can redirect it.

## Cross-Domain Examples

| Domain | What Reachability Collapse Looks Like |
|---|---|
| Biology | Organ function within normal range, but recovery capacity so degraded that any acute stressor leads to irreversible failure |
| Markets | Portfolio returns stable, but correlation structure so concentrated that any sector shock cascades system-wide |
| Organizations | KPIs on target, but institutional knowledge so depleted that any key departure triggers capability collapse |
| Infrastructure | Grid operating within spec, but redundancy margins so thin that any node failure cascades |

## Connection to Other Concepts

- Reachability is computed from [World-Line](world_lines.md) geometry — the trajectory's velocity and curvature determine which futures are kinematically accessible.
- The [Recovery Gradient](recovery_gradient.md) is a proxy measure of reachability depth — high recovery gradient implies a wide, deep reachability cone.
- [Phase Transitions](phase_transitions.md) are the events where reachability undergoes sudden, discontinuous contraction.
- [Trajectory Compression](trajectory_compression.md) must preserve reachability-relevant structure, or the entire framework loses its computational foundation.

## Open Questions

- Can reachability be computed efficiently in very high-dimensional manifolds, or does it require dimensionality reduction that risks discarding critical structure?
- What is the relationship between reachability cone geometry and information-theoretic entropy of the system?
- Can reachability loss functions be made differentiable for end-to-end optimization in neural architectures?
