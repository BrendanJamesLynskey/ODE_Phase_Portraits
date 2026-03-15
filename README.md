# ODE Phase Portraits

An interactive, browser-based tool for exploring the phase portraits of two-dimensional ordinary differential equations. Visualise vector fields, nullclines, trajectories, and fixed-point classifications in real time — no installation required.

### [Launch App](https://brendanjameslynskey.github.io/ODE_Phase_Portraits/)

---

## What is this?

A **phase portrait** is the geometric picture of all possible trajectories of a two-dimensional autonomous system dx/dt = f(x, y), dy/dt = g(x, y). Instead of solving the equations analytically — which is rarely possible for nonlinear systems — phase portraits let you read off the qualitative behaviour at a glance: where solutions converge, where they diverge, whether oscillations are sustained or transient, and how the topology of the flow changes as you vary a parameter.

This application renders the **vector field** as a grid of arrows whose direction and length encode the instantaneous velocity (f, g) at each point. Superimposed on the field are the **nullclines**: the curve where dx/dt = 0 (shown in pink) and the curve where dy/dt = 0 (shown in green). These curves partition the phase plane into regions of qualitatively distinct motion — in each region, the signs of dx/dt and dy/dt are constant, so trajectories flow in a predictable diagonal direction. The intersections of the two nullclines are the **fixed points** (equilibria) of the system, the only locations where the velocity is exactly zero.

At each fixed point, the app computes the **Jacobian matrix** of partial derivatives and extracts its **eigenvalues** to classify the local behaviour. Real, negative eigenvalues produce a **stable node** (all nearby trajectories converge); real eigenvalues of opposite sign produce a **saddle point** (attracting along one axis, repelling along another); complex eigenvalues with negative real part produce a **stable spiral** (damped oscillation); and purely imaginary eigenvalues produce a **centre** (closed orbits, no damping). This eigenvalue classification — the heart of **linearisation theory** — is displayed on-screen for every equilibrium, so you can immediately connect the algebra to the geometry.

The systems included span classical mechanics (harmonic oscillator, pendulum), nonlinear dynamics (Van der Pol, Duffing), mathematical biology (Lotka–Volterra predator–prey), computational neuroscience (FitzHugh–Nagumo), and bifurcation theory (saddle-node and Hopf bifurcations). Together they illustrate the major qualitative phenomena of planar dynamical systems: limit cycles, bistability, excitability, hysteresis, and the creation and destruction of equilibria.

## Dynamical Systems

| System | Equations | Description |
|--------|-----------|-------------|
| **Simple Harmonic Oscillator** | dx/dt = y, dy/dt = −ω²x | The prototype conservative system. All trajectories are closed ellipses encircling a **centre** at the origin. Energy is conserved; there is no damping and no limit cycle — just perpetual oscillation whose frequency is set by ω. |
| **Damped Oscillator** | dx/dt = y, dy/dt = −2ζω y − ω²x | Adds linear dissipation (ζ > 0) to the harmonic oscillator. The centre becomes a **stable spiral** for underdamped motion (ζ < 1) or a **stable node** for overdamped motion (ζ > 1). The critical case ζ = 1 is the boundary between oscillatory and monotone decay. |
| **Van der Pol Oscillator** | dx/dt = y, dy/dt = μ(1 − x²)y − x | A nonlinear oscillator with amplitude-dependent damping: trajectories far from the origin are damped inward, while those near the origin are pumped outward. The result is a **stable limit cycle** — a unique closed orbit that attracts all non-equilibrium initial conditions. As μ increases, the limit cycle develops sharp corners and the system exhibits **relaxation oscillations**. |
| **Lotka–Volterra** | dx/dt = αx − βxy, dy/dt = δxy − γy | The classical **predator–prey** model. Prey (x) grow exponentially in isolation; predators (y) decline without prey. Their interaction produces a family of closed orbits (a nonlinear centre) around the coexistence equilibrium at (γ/δ, α/β). The origin is a saddle, reflecting the instability of the extinction state when either population is absent. |
| **Damped Pendulum** | dθ/dt = ω, dω/dt = −(g/L) sin θ − bω | A rigid pendulum with viscous friction. The downward rest position (θ = 0) is a **stable spiral** (or node); the inverted position (θ = ±π) is a **saddle**. The separatrices of the saddle divide phase space into basins of attraction — initial conditions inside converge to the downward equilibrium, while those outside correspond to full rotations that eventually settle. |
| **Duffing Oscillator** | dx/dt = y, dy/dt = x − x³ − δy | A particle in a **double-well potential** V(x) = −x²/2 + x⁴/4. Two stable minima at x = ±1 are separated by an unstable maximum at x = 0. The origin is a **saddle**; the points (±1, 0) are **stable spirals** (or nodes). The separatrices of the saddle form the boundary between the two basins of attraction — the system exhibits **bistability**. |
| **FitzHugh–Nagumo** | dv/dt = v − v³/3 − w + I, dw/dt = ε(v + a − bw) | A simplified model of neuronal excitability. The cubic v-nullcline and linear w-nullcline intersect at one or three points depending on the applied current I. For low I, the unique fixed point is a stable node and the system is **excitable**: small perturbations return quickly, but perturbations beyond a threshold trigger a large action-potential-like excursion. As I increases through a **Hopf bifurcation**, the fixed point destabilises and the neuron fires repetitively. The parameter ε controls the timescale separation between the fast voltage and slow recovery variables. |
| **Saddle-Node Bifurcation** | dx/dt = μ + x², dy/dt = −y | The normal form for a **saddle-node (fold) bifurcation**. When μ < 0, two fixed points exist on the x-axis: a stable node at x = −√(−μ) and a saddle at x = +√(−μ). As μ increases toward zero, the two equilibria approach each other, coalesce at the origin when μ = 0, and **annihilate** — for μ > 0 no fixed points remain and all trajectories escape to the right. This is the generic mechanism by which equilibria are created or destroyed in one-parameter families. |
| **Hopf Bifurcation** | dx/dt = μx − y − x(x² + y²), dy/dt = x + μy − y(x² + y²) | The normal form for a **supercritical Hopf bifurcation**. When μ < 0, the origin is a stable spiral and all trajectories spiral inward. At μ = 0 the linearisation has purely imaginary eigenvalues (a centre). For μ > 0, the origin becomes an unstable spiral and a **stable limit cycle** of radius √μ is born — a small-amplitude periodic orbit that grows continuously from zero. This is the principal route from steady state to oscillation in physical, chemical, and biological systems. |
| **Double Well Potential** | dx/dt = y, dy/dt = x − x³ − δy | Equivalent to the Duffing system, modelling a particle moving in the potential V(x) = −x²/2 + x⁴/4 with damping δ. The two potential minima at x = ±1 are **stable equilibria** (spirals or nodes depending on δ), and the local maximum at x = 0 is a **saddle**. The saddle's stable and unstable manifolds form a heteroclinic-like structure that divides the phase plane into two **basins of attraction**, illustrating bistability and the role of initial conditions in selecting the final state. |

## Features

- **10 dynamical systems** spanning linear, nonlinear, neuroscience, and bifurcation categories, each with real-time adjustable parameters via sliders
- **Vector field** rendered as a grid of scaled arrows, showing the direction and relative magnitude of the flow (f, g) at every point on the phase plane
- **Nullclines** drawn as dashed curves — pink for dx/dt = 0, green for dy/dt = 0 — making it easy to locate fixed points (intersections) and read off the sign structure of the flow in each region
- **Fixed-point detection** performed numerically via Newton's method, with automatic deduplication; each equilibrium is plotted as a filled circle (stable) or hollow circle (unstable/saddle)
- **Eigenvalue classification** of every fixed point via the Jacobian: stable node, unstable node, saddle, stable spiral, unstable spiral, or centre — displayed on-screen with the computed eigenvalue(s)
- **Click-to-launch trajectories** integrated forward in time using a 4th-order Runge–Kutta (RK4) scheme with adaptive step limiting and divergence detection
- **Time series panel** showing x(t) and y(t) for the most recently launched trajectory
- **Pan, zoom, and scroll** on both the phase plane and time series plots (Plotly.js interactive mode)
- **Dark-themed UI** with a responsive layout that adapts from desktop to mobile
- **Zero installation** — pure client-side HTML/CSS/JS, hosted on GitHub Pages

## Built with

- [Plotly.js](https://plotly.com/javascript/) — interactive, publication-quality plotting
- Vanilla HTML, CSS, and JavaScript — no build step, no frameworks, no server, no dependencies to install
