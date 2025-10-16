---
title: "Raytracer - UofT CS Project"
description: "A Rust re-implementation of a University of Toronto Computer Graphics course raytracer with JSON-based scene configuration."
date: 2021-09-01
link: 'https://github.com/ericpko/raytracer'
image: 'https://raw.githubusercontent.com/ericpko/raytracer/main/readme-png/creative.png'
---

A raytracer originally from the University of Toronto Computer Graphics course, re-implemented in Rust with support for custom scene configuration through JSON files.

![Ray traced scene with multiple geometric primitives](https://raw.githubusercontent.com/ericpko/raytracer/main/readme-png/creative.png)

::link{url="https://github.com/ericpko/raytracer"}

## About

This project is a Rust implementation of a raytracer from the Computer Graphics course at the University of Toronto (taught by Alec Jacobson). Rather than following the original course implementation language, I chose to rebuild it in Rust to explore systems programming and learn Rust's ownership model while working with graphics algorithms.

The raytracer emphasizes flexibility through JSON-based scene configuration, allowing users to define complex scenes with multiple geometric primitives and render them programmatically.

## Features

- **JSON Scene Configuration** - Define scenes with custom camera positions, lights, and objects
- **Geometric Primitives** - Support for spheres, planes, and triangles
- **Scene Composition** - Build complex scenes from simple geometric elements
- **Custom Rendering** - Configure render parameters through JSON
- **Educational Foundation** - Based on structured CS curriculum

## Technologies Used

- **Rust** - Memory-safe systems programming with zero-cost abstractions
- **JSON** - Declarative scene description format
- **Ray Tracing** - Classic computer graphics rendering technique
- **Geometric Algorithms** - Intersection tests and shading computations

## Example Scenes

The repository includes multiple example scenes demonstrating different geometric configurations:
- Sphere packing arrangements
- Plane and sphere combinations
- Creative geometric compositions
