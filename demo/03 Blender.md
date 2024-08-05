# Chapter 3: Blender
Using Blender 4.2 (maybe 4.3 depending on when that comes out :p)

## Blender Basic Controls
- Select Object: LMB
- Context Menu: RMB
- Rotate Camera: MMB
- Translate Camera: Shift + MMB
- Zoom Camera: Scroll wheel

- Grab (Move) Selected: G
- Scale Selected: S
- Rotate Selected: R
- Fill Selected: F

- Switch Mode: Tab

## Basic Modelling
Models are made up from points/vertexes in 3d space that are connected by edges and filled to become faces.

> Creating models is a lot of trial and error,  you will end up developing your own workflow. It will also get a lot easier the more you use the software and learn keyboard shortcuts.

In edit mode using 1,2,3 on your keyboard allows you to select 1: Vertecies, 2: Edges or, 3: Faces.

## Normals & Face Direction
Unlike a piece of paper which although flat, can be seen from both sides. Game engines need to be told which face is the front and which is the back. This is so that the engine doesn't render faces that are not needed to be rendered as the player can't see them.

Top right corner of the 3d window, icon where 2 circles overlap, check box "Face Orientation".
Then selecting each face and pressing Alt+n will bring up the Normals & Face Direction context menu.

## Materials
Materials are handled in the inspector window located by default in the bottom right. With an object selected a red sphere near the bottom of the tab list will appear. Clicking on this will reveal the material panel.

The material panel will allow you to change basic properties such as Base Colour, Metalness and Roughness. This is part of the PBR rendering workflow.

> Physically Based Rendering (PBR) is common place in modern computer graphics, the goal of PBR is to make shaders that accurately represent how light interacts with surfaces in the computer compared to real life. E.g. Metal reflects more specular than diffuse light, Carpet appears rough to the touch, Wood contains a grain direction identifiable more than just surface colour.

PBR materials use different maps to display different materials:
- Base Colour
- Normal
	- Height/Displacement
	- Bump
- Metallic
- Roughness/Smoothness
- Ambient Occlusion
- Sub Surface Scattering
	- Transmission
	- Colour

## UVMapping
UVMapping is described by how a texture is mapped to a model in UV Space. The easiest examples given to describe this process is like peeling an orange skin, or like christmas chocolate santas. It is a texture that gets wrapped around an object.

![Tux, the Linux mascot](demo/images/03_UV_Mapping_Santa.jpg)
> Source: https://x.com/xxivips/status/938366852039888896/photo/1

The UV editor will allow you to choose where each vertex samples its texture coordinate from. The goal of this is to reduce distortion on tiling textures (textures which can be infinitely tiled) and to sample texture positions.