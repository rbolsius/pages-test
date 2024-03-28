# Blender

## Overlays

  - Face normals
      - Settings - make front overlay completely transparent, back overlay low
        opacity so that the overlay is more subtle and can be enabled always

## Viewport Display

  - Set color for objects in the viewport under object metadata
  - `Ctrl-B` - Define a bounding box for rendering

## Area Lights

  - Spread setting - controls how close to the light source before the shadows
    become diffused

## Objects

  - Visibility section - useful to control whether a light or object appears
    in viewport or renders
      - Ray Visibility - Uncheck Glossy, Transmision if you don't want the
        light or object to appear in reflections or refractions

## Modifiers

  - Bevel - add beveled edges to simple meshes to catch highlights
      - Optionally check Harden Normals in the Bevel Modifier and enable Auto
        Smooth in the mesh properties for a rounded bevel

## Snapping

  - Hold `Shift` when selecting the snap mode to select multiple modes (e.g.,
    snap to vertices, edges, and faces)

## Material Nodes

  - MixRGB - tone down a map by mixing a solid color
  - Light Path node - Mix Shader to choose different materials or adjustments
    for different ray types (diffuse, reflections, etc.)

## Assets

  - iMeshh.com - Some free Archviz materials, models, etc. ($75 per year for
    1800 furniture and Archviz models)
      - Also provides an asset manager add-on for quick access to iMeshh
        assets and some HDRI settings
  - PolyHaven.com - Textures and materials for Blender or other tools with
    BSDF shaders
  - HDRI Haven

## Add-Ons

  - **Node: Node Wrangler** - allows some workflow improvements inside the node
    editor
      - Preview the output of a particular node by selecting the node with
        `Ctrl+Shift+LMB`
      - Disconnect nodes by drawing a line that cuts through the connection
      - Quickly create texture mapping node graphs as input to other nodes

  - **Mesh: LoopTools** - Convert loops to circles, evenly space points along
    an edge, flatten crooked faces and curves, etc.

  - **Mesh: F2** - create geometry in open space with a single key (good for
    speeding up workflows that involve building a mesh one face at a time)

## Tutorials

### Archviz

  - Blender Archviz MASTERCLASS | Archvix Tutorial #3 | iMeshh.com Guide

  - Performance tips
      - Blender Path Guiding - new feature, may make light portals obsolete
      - Area Lights for windows
          - Check Portal in the Physical Light section of the object metadata
      - Glass - make material 100% transparent for shadow and diffuse rays
          - Light Path node (Is Shadow Ray/Is Diffuse Ray) -> Add -> Mix
            Shader
              - Mix BSDF and Tansparent BSDF shaders
          - Shadow and diffuse rays will not be attenuated by the glass
            material, which will speed up calculations considerably without
            making much difference
      - Simplify section of Render tab
          - Set Texture Limit to 2K to speed up render speed and reduce
            graphics RAM usage
      - Background objects - remove unnecessary textures (diffuse map may be
        enough)

      - Render at 200% of final resolution and reduce max samples by factor of
        4
          - Higher resolution is better for denoise algorithm

      - Add Denoise node to the compositing nodetree instead of checking
        denoise object in render tab since you can choose how much of the
        denoised image to mix with the noisy image

      - Max Bounces
          - Transparent bounces - increase to 50 if there are transparent
            materials that contain black specks in the render

      - Clamping
          - Set to 0 to not reduce the light level from direct or indirect
            light (more realistic)
          - Setting to 0 can cause fireflies. So, increase to 3 or 10 if
            having problems with that, but the 2x resolution and increased
            samples should also avoid that

      - Film
          - Pixel Filter
              - Type Blackman Harris
              - Width - lower value (e.g. 1.1px) is sharper but can cause aliasing
              - 
      - Performance
          - Final Render - check Persistent Data - reuse data from previous
            renders to speed up final renders from multiple cameras

      - Color management
          - Filmic or newer AGx

      - Render Passes for post processing (under Scene tab)
          - Combined - fully mixed output
          - Denoising Data - for input to the denoise compositing node
          - Light passes - glossy indirect, Ambient occlusion
          - Light groups - allows mixing different light sources in post
            production


  - ArchViz Tutorial #2
      - Goes into more detail into render passes


## Keyboard Shortcuts

| Blender       | Industry Standard | Command                                                                                   |
| ------------- | ----------------- | ----------------------------------------------------------------------------------------- |
| `Shift-N`     |                   | Make face normals consistent                                                              |
| `Alt-N`       |                   | Flip face normals                                                                         |
| `W` ?         |                   | Walk mode                                                                                 |
| `Ctrl-R`      |                   | Add a loop                                                                                |
| `G`           |                   | Grab                                                                                      |
| `X`, `Y`, `Z` |                   | Restrict movement to one axis (type a number afterward to move by that many units)        |
| `K`           |                   | Cut tool                                                                                  |
| `E`           |                   | Extrude                                                                                   |
| `Shift-D`     |                   | Duplicate                                                                                 |
| `Alt-D`       |                   | Duplicate as an instance (useful for lights so that light parameters can be changed once) |
| `F`           |                   | Fill loop with face                                                                       |
| `A`           |                   | Select all                                                                                |
| `Tab`         |                   | Search for command                                                                        |
| `Shift+Tab`   |                   | Quick menu                                                                                |
| `Ctrl`        |                   | Snap to increment while `Ctrl` is held                                                    |
| `Shift`       |                   | Move, rotate, scale more precisely while `Shift` is held                                  |
| `Shift-A`     |                   | Add an object                                                                             |
|               | `X`               | Toggle snapping                                                                           |
| `1`           | `1`               | Vertex mode                                                                               |
| `2`           | `2`               | Edge mode                                                                                 |
| `3`           | `3`               | Face mode                                                                                 |
| `4`           | `4`               | Object mode                                                                               |
| `5`           | `5`               | ?                                                                                         |
| `Numpad 0`    |                   | View from camera's perspective                                                            |
| `Numpad .`    |                   | Reveal selected object in the scene tree                                                  |
| `M`           |                   | Move selected objects to a new collection (like a layer)                                  |
| `U`           |                   | Unwrap selected faces (choose Smart UV Project for quick unwrap)                          |
| `Z` ?         |                   | Ring menu to change viewport style (wire, solid, rendered, etc.                           |
| `O`           |                   | Proportional editing (mouse wheel to adjust radius)                                       |
