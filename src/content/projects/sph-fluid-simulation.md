---
title: "SPH Fluid Simulation"
description: "A particle-based fluid simulation using Smoothed Particle Hydrodynamics, implemented in Rust with ggez."
date: 2021-06-01
link: 'https://ericpko.github.io/projects/sph-sim/'
image: 'https://raw.githubusercontent.com/ericpko/sph-fluid-simulation/main/resources/sph-sim.gif'
---

An interactive real-time fluid simulation using Smoothed Particle Hydrodynamics (SPH), a particle-based approach to simulating fluid dynamics.

![SPH fluid simulation showing particle interactions and fluid behavior](https://raw.githubusercontent.com/ericpko/sph-fluid-simulation/main/resources/sph-sim.gif)

::link{url="https://ericpko.github.io/projects/sph-sim/"}

## About

SPH (Smoothed Particle Hydrodynamics) is a computational method for simulating fluids using particles instead of traditional grid-based approaches. Each particle represents a small volume of fluid, and the simulation calculates forces between nearby particles to model realistic fluid behavior including:

- Pressure forces
- Viscosity
- Surface tension
- Gravity and external forces

This implementation is based on the seminal paper "Particle-Based Fluid Simulation for Interactive Applications" by Matthias Müller, David Charypar, and Markus Gross, which made real-time fluid simulation accessible for games and interactive applications.

## Features

- **Real-Time Simulation** - Interactive particle-based fluid dynamics
- **Physics Accuracy** - Based on peer-reviewed research
- **Particle-Based Approach** - More flexible than grid-based methods
- **Visual Feedback** - Watch fluid particles interact in real-time

## Technical Details

The simulation uses SPH kernels to approximate fluid properties at each particle's location by weighted averaging of nearby particles. This allows for:

- Natural handling of free surfaces
- Conservation of mass
- Adaptive resolution (more particles = higher detail)
- Efficient computation for interactive rates

## Technologies Used

- **Rust** - High-performance systems programming
- **ggez** - Game engine for graphics and interaction
- **SPH Algorithm** - Particle-based fluid dynamics
- **Physics Simulation** - Navier-Stokes equations approximation
