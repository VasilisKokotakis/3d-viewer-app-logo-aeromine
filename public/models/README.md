# Place Your GLTF Models Here

This is where you should put your 3D model files.

## Example structure:

```
models/
├── robot.gltf
├── robot.bin
├── car.glb
└── textures/
    ├── robot_diffuse.png
    ├── robot_normal.png
    └── car_texture.jpg
```

## Supported Formats:

- **.gltf** - JSON format (with separate .bin and texture files)
- **.glb** - Binary format (all-in-one file, recommended for web)

## File Organization Tips:

1. **Keep it organized**: One folder per model if you have multiple
2. **Use relative paths**: GLTF files reference textures with relative paths
3. **Optimize textures**: Use compressed formats (JPG for photos, PNG for graphics)
4. **Test your models**: Use https://gltf-viewer.donmccurdy.com/ to verify files work

## Free Model Resources:

- Sketchfab: https://sketchfab.com/features/gltf
- Three.js Samples: https://github.com/mrdoob/three.js/tree/dev/examples/models/gltf
- Poly Haven: https://polyhaven.com/models

---

**Quick tip**: GLB format is usually better for web because it's a single file!
