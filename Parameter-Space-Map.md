# NUCLEUS Parameter Space Map

## Overview

The parameter space map defines the mathematical foundation of NUCLEUS, mapping the relationships between inputs (controls) and outputs (visual patterns). This document outlines the core functions, parameters, and their interconnections that form the foundation of NUCLEUS's generative capabilities.

## Core Pattern Generators

Each generator represents a fundamental algorithm that produces a specific family of patterns.

| Generator | Description | Mathematical Basis | Visual Characteristics |
|-----------|-------------|-------------------|------------------------|
| `WaveformGenerator` | Produces oscillating patterns based on sine, square, or sawtooth waves | Trigonometric functions | Smooth flowing lines, ripples, waves |
| `FractalGenerator` | Creates self-similar iterative patterns | Julia sets, Mandelbrot, L-systems | Complex, recursive structures with infinite detail |
| `CellularGenerator` | Simulates cellular automata rules | Conway's Game of Life, reaction-diffusion | Organic, evolving patterns with emergent behavior |
| `NoiseGenerator` | Generates various noise types | Perlin, Simplex, Worley noise functions | Textural elements, natural randomness |
| `GeometricGenerator` | Creates patterns based on geometric primitives | Euclidean/non-Euclidean geometry | Precise, architectural forms with clear structure |
| `FlowFieldGenerator` | Simulates particle movement through vector fields | Curl noise, fluid dynamics | Flowing, directional motion patterns |
| `GlitchGenerator` | Produces digital distortion effects | Data manipulation, buffer errors | Corrupted, broken graphical artifacts |

## Parameter Types

Parameters are categorized by their function in the system:

### Primary Parameters
Direct controls that fundamentally change the output pattern.

| Parameter | Range | Effect | Applied To |
|-----------|-------|--------|------------|
| `frequency` | 0.01-100 | Controls oscillation speed/density | Waveform, Fractal |
| `amplitude` | 0-1.0 | Controls intensity/size of elements | Waveform, Flow Field |
| `iterations` | 1-20 | Controls recursion depth | Fractal, Cellular |
| `density` | 0.01-1.0 | Controls element distribution | Noise, Geometric |
| `resolution` | 4-1024 | Controls grid/sampling resolution | All generators |
| `seed` | 0-99999 | Initial state for deterministic randomness | All generators |

### Modifiers
Parameters that transform or combine other parameters.

| Modifier | Function | Effect | 
|----------|----------|--------|
| `LFO` (Low Frequency Oscillator) | `sin(time * rate) * depth` | Cyclical modulation of target parameter |
| `Envelope` | Multi-stage value progression | Timed evolution of parameter values |
| `RandomWalk` | Brownian motion on parameter value | Organic variation of parameters over time |
| `QuantizeModifier` | Rounds values to specific steps | Creates discrete rather than continuous changes |
| `CurveModifier` | Applies easing functions | Changes the acceleration of parameter changes |

### Transformations
Operations applied to the entire pattern after generation.

| Transformation | Description | Controls |
|----------------|-------------|----------|
| `ColorMapping` | Maps pattern values to color space | Palette, distribution, contrast |
| `Displacement` | Shifts elements based on a map | Intensity, direction, turbulence |
| `Feedback` | Feeds output back as input | Delay, blend, iterations |
| `Symmetry` | Creates mirrored/rotational copies | Axis, count, blend mode |
| `Bloom` | Creates glow effects | Radius, intensity, threshold |
| `Pixelate` | Reduces resolution in specific ways | Cell size, shape, dithering |

## Parameter Relationships 

### Dimension Mappings
How parameters map to visual dimensions:

- **X-axis**: Horizontal position, typically mapped to time or angle
- **Y-axis**: Vertical position, typically mapped to amplitude or value
- **Z-axis** (in 3D mode): Depth, mapped to layer, intensity, or third parameter
- **Time dimension**: Animation progression, mapped to frame count or elapsed time
- **Color dimension**: Value mapping to selected color palette

### Sweet Spots and Emergent Behaviors

Specific parameter combinations that yield interesting results:

| Name | Parameters | Description | Visual Result |
|------|------------|-------------|---------------|
| "Quantum Tunnel" | `WaveformGenerator` with high frequency + feedback | Creates recursive tunneling effect | Nested rippling portals with depth |
| "Cellular Collapse" | `CellularGenerator` with specific rule set + symmetry | Produces stable but complex patterns | Mandala-like organic structures |
| "Harmonic Convergence" | Multiple `WaveformGenerator`s with related frequencies | Creates moiré and interference patterns | Complex overlapping wave forms |
| "Digital Decay" | `GlitchGenerator` + gradual parameter shifts | Simulates degrading digital media | Evolving corruption that follows coherent progression |
| "Fractal Bloom" | `FractalGenerator` with specific iteration depth + bloom | Creates soft fractal landscapes | Glowing mathematical structures with depth |

## Parameter Space Visualization

The parameter space can be visualized as an n-dimensional manifold where:

1. Each generator defines its own sub-space with specific dimensions
2. Parameters form axes within these spaces
3. Sweet spots exist as regions of interest 
4. Transitions between regions create interesting animation paths

![Parameter Space Conceptual Diagram]

## Implementation Notes

1. All parameters should support:
   - Real-time modification
   - Modulation by other parameters
   - Animation along predetermined paths
   - Saving/loading of specific states

2. The system should track "interesting" outputs based on:
   - User interaction/dwell time
   - Complexity metrics
   - Novelty detection

3. Performance considerations:
   - Progressive rendering for complex patterns
   - Parameter-dependent level of detail
   - Intelligent caching of repeatable elements
