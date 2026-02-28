---
title: CUDA Thread Visualizer
colorFrom: green
colorTo: blue
sdk: static
pinned: false
license: mit
short_description: A 3D visualizer for CUDA grid/block/thread hierarchy
---

# CUDA Thread Visualizer

An interactive 3D visualizer that helps you understand how CUDA organizes threads into blocks and grids. See exactly how `blockIdx`, `threadIdx`, `blockDim`, and `gridDim` map to each individual thread — and how global indices are computed.

Built as a single HTML file with zero dependencies. Just open it in a browser.

## Why

When learning CUDA programming, one of the first hurdles is understanding the thread hierarchy: how a kernel launch like `kernel<<<dim3(2,2,1), dim3(4,4,1)>>>()` maps to actual thread coordinates. This tool makes that mapping visual and interactive.

## Features

- **3D visualization** of every thread as a colored cube, with blocks distinguished by color and spacing
- **Full `dim3` control** — configure `gridDim(x,y,z)` and `blockDim(x,y,z)` with real-time updates
- **Click any thread** to inspect its `blockIdx`, `threadIdx`, and see the global index formula using CUDA built-in variables
- **NVIDIA-standard coordinate system** — X→right, Y→down, Z→depth, matching the official CUDA Programming Guide
- **Auto-fit zoom** — the view automatically scales to fit any grid configuration
- **Presets** for common patterns: 1D, 2D, 3D, and GEMM-style layouts
- **Live kernel launch bar** showing the corresponding `kernel<<<grid, block>>>()` syntax
- **Axis compass** that stays on screen so you always know the orientation
- **Touch support** — works on mobile with pinch-to-zoom and drag-to-rotate

## Controls

| Action | Mouse | Touch |
|--------|-------|-------|
| Rotate | Left drag | One-finger drag |
| Pan | Right drag | — |
| Zoom | Scroll wheel | Two-finger pinch |
| Select thread | Click | Tap |

## Tech

Single HTML file (~900 lines), SVG-based 3D rendering with perspective projection, zero external dependencies.

## License

MIT