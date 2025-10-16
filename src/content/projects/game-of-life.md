---
title: "Conway's Game of Life"
description: 'A WebAssembly implementation of the classic cellular automaton simulation, built with Rust.'
date: 2024-06-01
link: 'https://ericpko.github.io/wasm-game-of-life/'
---

An interactive implementation of Conway's Game of Life, demonstrating high-performance browser-based computation using Rust compiled to WebAssembly.

<iframe src="https://ericpko.github.io/wasm-game-of-life/" title="Conway's Game of Life - Interactive Demo" loading="lazy" allowfullscreen style="height: 550px"></iframe>

::link{url="https://ericpko.github.io/wasm-game-of-life/"}

## About

Conway's Game of Life is a cellular automaton where cells evolve based on simple rules:
- Any live cell with 2-3 neighbors survives
- Any dead cell with exactly 3 neighbors becomes alive
- All other cells die or stay dead

Despite these simple rules, the Game of Life produces complex emergent patterns and behaviors.

## Features

- **High Performance** - Rust compiled to WASM for efficient computation
- **Interactive Simulation** - Real-time visualization in the browser
- **Cellular Automaton Engine** - Implements classic Conway's rules
- **Browser-Based** - No installation required, runs entirely in the browser

## Technologies Used

- **Rust** - Core simulation logic and performance-critical code
- **WebAssembly** - Compiles Rust to browser-executable format
- **JavaScript** - Frontend interaction and rendering
- **HTML/CSS** - User interface and controls
