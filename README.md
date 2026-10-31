# 3D Software Renderer

Computer Graphics homework: a 3D renderer written from scratch in JavaScript,
without WebGL or any graphics library. Every pixel is drawn by my own code.

**Live demo:** https://reem601.github.io/3d-software-renderer/

## Features

- OBJ file parser (`v` and `f` lines, polygons split into triangles)
- Triangle rasterizer using barycentric coordinates
- Z-buffer for hidden surface removal
- Camera class with View matrix and Projection matrix (perspective)
- Phong lighting (ambient + diffuse + specular) with smooth per-pixel normals
- Buttons to move the camera

## Files

- `index.html` - the whole renderer
- `african_head.obj` - the 3D model

## How it works

1. Load the model from the OBJ file.
2. Transform each vertex: `Projection * View * vertex`, divide by w, convert to screen pixels.
3. For each triangle, test every pixel in its bounding box with barycentric coordinates.
4. Use the Z-buffer to keep only the closest pixel.
5. Interpolate the vertex normals inside the triangle and compute Phong lighting.

## TODO

- Texturing (bonus)
