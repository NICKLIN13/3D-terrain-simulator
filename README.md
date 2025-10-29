# 3D Terrain Simulator

A WebGL2-based 3D terrain simulator featuring procedural terrain generation, heightmap manipulation, and interactive camera control.

---

## Features

- Procedural terrain generation using randomized faults and height normalization
- Triangle rasterization with per-vertex normals for shading
- Real-time lighting with Lambertian and Blinn-Phong reflection models
- Z-buffer (depth test) ensures correct rendering of overlapping geometry
- Interactive camera controls:
  - `W` / `S` → move forward/backward
  - `A` / `D` → move left/right
  - Arrow keys → pan and pitch
- Responsive full-screen canvas

---

## Tech Stack

- JavaScript
- WebGL2
- GLSL shaders (vertex and fragment)

---

## File Structure

- `3D_terrain_simulator.html` – main HTML file containing shaders and JavaScript code
- `math.js` – helper math functions (vectors, matrices, etc.)

---

## How It Works

1. Generate a random terrain grid and apply faults to create elevation variations
2. Normalize heights for visualization
3. Create geometry (triangles and vertex attributes) and upload to GPU buffers
4. Vertex and fragment shaders handle 3D transformations and lighting
5. Use a Vertex Array Object (VAO) to organize vertex data for rendering
6. Depth testing (Z-buffer) ensures correct occlusion between terrain surfaces
7. Interactive camera allows exploration of the terrain in real time

---

## Keyboard Controls

| Key           | Action                        |
|---------------|-------------------------------|
| `W` / `S`     | Move forward / backward       |
| `A` / `D`     | Move left / right             |
| `Arrow Keys`  | Pan and pitch                 |

---

## Key Functions

- `compileShader(vs_source, fs_source)` – compiles vertex and fragment shaders and links them into a WebGL program
- `supplyDataBuffer(data, loc, mode)` – uploads per-vertex data to the GPU
- `setupGeomery(geom)` – creates a VAO with triangles and vertex attributes
- `generateGrid(gridsize)` – initializes the height grid
- `faulting(faults)` – applies procedural faults to the terrain
- `normalizeHeights(faults)` – normalizes terrain heights
- `generateGeom()` – generates geometry from height data
- `addNormals(geom)` – calculates per-vertex normals for lighting

---

## How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/NICKLIN13/3D-terrain-simulator.git
    cd 3D_terrain_simulator
    ```
2. Open 3D_terrain_simulator.html in a WebGL2-capable browser (Chrome, Firefox, Edge, etc.)
3. Use the keyboard controls to explore the terrain