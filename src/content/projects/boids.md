---
title: "Boids Flocking Simulation"
description: "A flocking simulation implementing the classic Boids algorithm with three behavioral rules, built with Rust and ggez."
date: 2024-03-01
link: 'https://ericpko.github.io/projects/boids/'
---

A visual simulation of flocking behavior using the Boids algorithm, demonstrating how complex emergent patterns arise from simple rules.

![Boids simulation showing flocking behavior](https://raw.githubusercontent.com/ericpko/boids/main/resources/boids.gif)

::link{url="https://ericpko.github.io/projects/boids/"}

## About

The Boids algorithm simulates the flocking behavior observed in birds, fish, and other animals. Despite using only three simple rules, the simulation produces remarkably realistic collective motion patterns.

## The Three Rules

1. **Separation** - Avoid crowding nearby boids (steer to avoid collisions)
2. **Alignment** - Steer towards the average heading of nearby boids
3. **Cohesion** - Steer towards the average position of nearby boids

These simple rules create emergent flocking behavior without any central coordination.

## Features

- **Real-time Simulation** - Interactive visualization of flocking dynamics
- **Emergent Behavior** - Complex patterns from simple rules
- **Visual Demonstration** - Watch boids interact and form flocks naturally
- **Written in Rust** - Performance-optimized implementation

## Technologies Used

- **Rust** - Core simulation logic and performance
- **ggez** - Graphics and game engine library
- **Boids Algorithm** - Classic flocking simulation technique
