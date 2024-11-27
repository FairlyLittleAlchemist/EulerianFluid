# Simulation Project

This repository contains a physics-based fluid simulation implemented in C++. It models the behavior of fluid flow and smoke dynamics using numerical techniques. The simulation leverages a staggered grid approach to handle velocity, pressure, and scalar fields, enabling a realistic and efficient representation of incompressible fluid dynamics.

## Features

- **Staggered Grid Representation**: Efficient handling of velocities and scalar fields on a grid.
- **Incompressible Fluid Simulation**: Implements divergence-free velocity fields for realistic fluid behavior.
- **Smoke Advection**: Models smoke transport and interaction with fluid flow.
- **Boundary Conditions**: Handles boundaries with zero and unit scalar values.
- **Interactive Dynamics**: Adjusts gravity, density, and other parameters to influence fluid behavior.
- **Numerical Techniques**: Uses semi-Lagrangian advection, pressure projection, and extrapolation to maintain fluid properties.

## Code Overview

### Key Classes and Methods

- **`Simulation` Constructor**: Initializes the simulation grid and scalar fields.
- **`initializeS`**: Sets up the scalar field, defining boundaries and active regions.
- **`integrate`**: Updates velocity fields based on forces like gravity.
- **`solveIncompressibility`**: Ensures divergence-free velocity fields using iterative pressure projection.
- **`extrapolate`**: Applies velocity extrapolation for stability at boundaries.
- **`sampleField`**: Interpolates field values at arbitrary locations using bilinear interpolation.
- **`advectVel`**: Moves velocity fields across the grid using semi-Lagrangian advection.
- **`advectSmoke`**: Updates smoke density based on velocity field transport.
- **`copyVector`**: Utility for efficient vector copying.

## Dependencies

The project relies on:

- **C++ Standard Library**: For data structures and utilities like `std::vector` and `std::memcpy`.
- **Mathematical Functions**: Includes `std::min`, `std::floor`, and other numeric utilities.

## How It Works



- Initialization: The grid is set up with scalar and velocity fields.
- Time Step Integration:
    Gravity is applied to velocity fields.
    Smoke and velocities are advected using a semi-Lagrangian scheme.
- Incompressibility Solve: Iteratively adjusts pressure to maintain divergence-free velocities.
- Boundary Handling: Enforces zero and extrapolated boundary conditions for stability.

