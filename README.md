# ReflectiveMaterial

**A new material for [Three.js](https://threejs.org/) that provides distorted normal map–based reflections**

ReflectiveMaterial is a custom material designed to simulate textured reflections on surfaces like floors by distorting reflection data using a normal map. It enhances realism by merging reflection logic with geometry surface detail, producing convincing surface-aware reflections.

[View Live Demo](https://projects.chriscarruthers.co.uk/showroom/)
---

## ✨ Features

- Integrates seamlessly with `MeshStandardMaterial` properties
- Adds reflection with normal map–based distortion
- Supports adjustable distortion intensity and reflection strength
- Optimized for performance with configurable reflection resolution

---

## 🛠️ Installation

Clone or download the material and import it into your Three.js project:

```js
import { ReflectiveMaterial } from './ReflectiveMaterial.js'

```js
const reflectiveSurfaceMaterial = new ReflectiveMaterial({

  // MeshStandardMaterial Properties
  color: 0xffffff,
  metalness: 0.3,
  roughness: 0.1,

  // Additional ReflectiveMaterial Properties
  reflectionStrength: 0.5,
  distortionMap: distortionMap,      // THREE.Texture (normal map)
  distortionScale: 0.5,              // Controls distortion intensity
  reflectionResolution: 1024         // Power-of-two preferred (e.g. 512, 1024)

}, floorSurface) // Pass in the geometry or mesh to reflect


## 🧩 Parameters

| Property              | Type            | Description                                          |
|-----------------------|-----------------|------------------------------------------------------|
| `distortionMap`       | `THREE.Texture` | Normal map that distorts the reflection              |
| `distortionScale`     | `Number`        | Strength of the distortion effect                    |
| `reflectionStrength`  | `Number`        | Blend factor of reflection (0 = none, 1 = full)      |
| `reflectionResolution`| `Number`        | Resolution of internal reflection render target      |

All standard `MeshStandardMaterial` parameters are supported.

## 🧪 Notes

Works best with horizontal or mildly curved surfaces (e.g. floors, ground).

Internally renders the reflected scene using a mirror camera.

Uses a render target and may impact performance on lower-end devices.

