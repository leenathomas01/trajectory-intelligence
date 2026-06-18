# Open Question: Quantifying Adaptive Capacity Non-Invasively

## The Question

How can a model calculate an accurate Recovery Gradient if the system cannot be safely or ethically subjected to an explicit physical stressor?

## Why It Matters

Recovery Gradient is the framework's strongest predictive signal. But its canonical measurement requires perturbation: stress the system, observe the return trajectory, characterize the recovery dynamics.

Many systems cannot be deliberately stressed. You cannot ethically induce cardiac stress to measure a patient's recovery trajectory. You cannot deliberately crash a financial market to assess its resilience. You cannot fire an organization's key employees to test institutional robustness.

If Recovery Gradient can only be measured through deliberate perturbation, the framework's applicability is severely limited to domains where controlled stress testing is feasible and acceptable.

## Potential Approaches

- **Natural perturbation exploitation**: Using ambient stressors (daily activity cycles, seasonal variation, routine operational fluctuations) as natural probes. If Recovery Gradient can be estimated from the system's response to normal environmental variation, deliberate perturbation becomes unnecessary.
- **Transfer from proxy systems**: Measuring Recovery Gradient on a simplified model or subsystem and extrapolating to the full system.
- **Inference from trajectory geometry**: Deriving Recovery Gradient from the shape of the World-Line near attractor basins without requiring explicit perturbation — using curvature, oscillation characteristics, and variance structure as indirect indicators.
- **Digital twin stress testing**: Building a sufficiently accurate simulation of the system and stress-testing the simulation rather than the real system.

## Research Directions

- Empirical validation of natural perturbation methods: do Recovery Gradients estimated from ambient stressors correlate with those measured from controlled stress tests?
- Theoretical characterization of the minimum perturbation magnitude required for reliable Recovery Gradient estimation.
- Development of inference methods that estimate basin depth from trajectory curvature without explicit perturbation.
