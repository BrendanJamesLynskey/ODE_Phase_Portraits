# ODE Phase Portraits

Interactive phase portraits for 2D dynamical systems — vector fields, trajectories, and bifurcations.

### [Launch App](https://brendanjameslynskey.github.io/ODE_Phase_Portraits/)

---

## What is this?

A single-page interactive tool for visualising the phase portraits of two-dimensional ordinary differential equations. Select a dynamical system, adjust its parameters with sliders, and click anywhere on the phase plane to launch trajectories from that initial condition.

The vector field shows the direction and magnitude of flow at each point. Nullclines mark where one component of the velocity is zero, and their intersections reveal the fixed points. Each fixed point is classified by eigenvalue analysis of the Jacobian — stable attractors are shown as filled dots, unstable points as hollow circles.

## Systems

| Category | System | Key behaviour |
|----------|--------|---------------|
| **Linear** | Simple harmonic oscillator | Center (closed orbits) |
| **Linear** | Damped oscillator | Stable spiral / node |
| **Nonlinear** | Van der Pol oscillator | Limit cycle |
| **Nonlinear** | Lotka-Volterra (predator-prey) | Periodic orbits |
| **Nonlinear** | Damped pendulum | Multiple equilibria |
| **Nonlinear** | Duffing oscillator | Double well, saddle |
| **Neuroscience** | FitzHugh-Nagumo | Excitable dynamics |
| **Bifurcation** | Saddle node | Saddle-node bifurcation |
| **Bifurcation** | Hopf bifurcation | Supercritical Hopf |
| **Nonlinear** | Double well potential | Bistability |

## Features

- **10 dynamical systems** with adjustable parameters via sliders
- **Vector field** rendered as arrows on the phase plane
- **Click to add trajectories** — integrated forward with RK4
- **Nullclines** shown as coloured dashed lines (pink = dx/dt = 0, green = dy/dt = 0)
- **Fixed points** found numerically and marked on the plot
- **Eigenvalue classification** displayed for each fixed point (node, spiral, saddle, center)
- **Time series plot** showing x(t) and y(t) for the most recent trajectory
- **Pan, zoom, and scroll** on all plots (Plotly.js)
- **Dark theme** UI, fully responsive

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive plotting
- Vanilla HTML/CSS/JS — no build step, no dependencies to install
