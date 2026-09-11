# 2D-Advection-Diffusion-Borehole-Heat-Transfer
# 2D Heat Transport Around Boreholes Using Finite Difference Methods

This repository contains the numerical implementation of Project 3 for ENE418.

The project investigates transient two-dimensional heat transport around boreholes using finite-difference methods. The governing models include pure diffusion, pure advection, combined advection-diffusion, time-varying heat sources, and multiple interacting boreholes.

## Project Tasks

### Task 1 — Pure Diffusion
- 2D finite-difference solution of the heat diffusion equation
- Temperature fields at 2000, 5000, and 10000 s
- Analytical diffusion-length comparison
- Thermal diffusivity sensitivity
- Source-strength sensitivity
- Numerical plume-radius detection
- Grid refinement study
- Time-step convergence

### Task 2 — Pure Advection
- Group-specific groundwater velocity field
- Upwind finite-difference advection solver
- Plume trajectory analysis
- Time-step sensitivity
- CFL stability analysis
- Upwind vs central scheme comparison

### Task 3 — Advection + Diffusion
- Coupled 2D advection-diffusion model
- Plume trajectory and directional behaviour
- Comparison with Tasks 1 and 2
- Time-step sensitivity
- Péclet number analysis
- Thermal-mass calculation

### Task 4 — Time-Varying Source
- Periodic Group-3 heat source
- Temporal plume evolution
- Plume size and peak-temperature analysis
- Plume-center tracking
- Time-step sensitivity

### Task 5 — Multiple Boreholes
- Four-borehole simulation
- Thermal interference analysis
- Borehole-pair interaction comparison
- Superposition test

## Group-Specific Parameters

This implementation uses Group 3.

The velocity field is:

vx = -0.02(y - 40)

vy = 0.02(x - 40)

The time-varying source is:

Q(t) = 0.15 if (t mod 1500) < 200  
Q(t) = 0 otherwise

## Main Numerical Parameters

- Domain: 60 m × 60 m
- Grid: 200 × 200
- Time step: 0.1 s
- Final time: 10000 s
- Thermal diffusivity: 5 × 10^-3 m²/s
- Initial temperature: 10 °C
- Constant source for Tasks 1–3: 0.2 °C/s

## Numerical Methods

The simulations use explicit finite-difference methods.

- Diffusion: second-order central difference
- Advection: first-order upwind scheme
- Time integration: explicit forward Euler
- Boundary condition: zero-gradient / no-flux approximation

Numerical stability is evaluated using the Fourier number for diffusion and the CFL condition for advection.

## Repository Structure

```text
notebooks/   Main Jupyter notebook
src/         Task-wise Python scripts
figures/     Simulation figures
report/      Final report
docs/        Assignment description
