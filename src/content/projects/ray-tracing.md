---
title: "Ray Tracing in One Weekend"
description: "A Rust implementation of Peter Shirley's ray tracing tutorial, rendering realistic 3D scenes with lighting, reflections, and materials."
date: 2022-06-01
link: 'https://github.com/ericpko/ray-tracing-in-one-weekend'
image: 'https://raw.githubusercontent.com/ericpko/ray-tracing-in-one-weekend/main/final_render.jpg'
---

A complete implementation of the classic "Ray Tracing in One Weekend" tutorial by Peter Shirley, demonstrating computer graphics fundamentals and physically-based rendering.

![Ray traced scene with spheres showing reflections, materials, and lighting](https://raw.githubusercontent.com/ericpko/ray-tracing-in-one-weekend/main/final_render.jpg)

::link{url="https://github.com/ericpko/ray-tracing-in-one-weekend"}

## About

Ray tracing is a rendering technique that simulates the physical behavior of light to generate photorealistic images. This project follows the well-known "Ray Tracing in One Weekend" tutorial series, implementing a path tracer from scratch that can render scenes with:

- Realistic lighting and shadows
- Reflective and refractive materials
- Anti-aliasing and depth of field effects
- Multiple material types (metal, glass, diffuse)

## Implementation Details

The project is organized with progressive commits aligned to each tutorial chapter, making it easy to follow the development process. The implementation includes:

- **Main branch** - Clean, readable code following the tutorial structure
- **Concurrency branch** - Parallelized version using Rayon for improved performance
- Complete through Chapter 13 of the tutorial

## Features

- **Physically-Based Rendering** - Simulates real light behavior
- **Material System** - Supports diffuse, metallic, and dielectric materials
- **Performance Optimized** - Parallel rendering using Rayon
- **Educational Structure** - Commits aligned with tutorial chapters

## Technologies Used

- **Rust** - System-level performance and memory safety
- **Rayon** - Data parallelism for faster rendering
- **Ray Tracing Algorithm** - Core computer graphics technique
