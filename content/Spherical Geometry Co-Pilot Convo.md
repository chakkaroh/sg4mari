---
title: Example Title
draft: false
tags:
  - example-tag
---
## Introduction

In this document I will be attempting to figure out what the fuck Kevin is talking about with multiple conversations with Co-Pilot and in general Google-ing. It will be an in depth dive into every word Kevin has mentioned in order to apply it in Blender using Geometry Nodes. Please do assist in adding more relevant info that you stumble upon because god knows we need help.

## Kevin’s Email
[[Previous Emails]]
Latest Email -
>By 'Environmental Scan' I mean a 3D scan to get actual geometry, a photosphere won't work because every vertex needs to be able to move and warp, which can't be done from just a photo.  That is, unless the actual environment really is flat without much depth like some grass, carpet or floor.  If the entire thing is flat there's a simpler technique that can be used, but it wouldn't look as visually interesting as 3D objects do, like the house or fence from the video.
>
>The full transformation is like this by the way:
>
>1. Start with each mesh in a unit volume 1x1x1
 >   
>2. Rescale to convert the Unit volume to Klein coordinates (this is just a scale factor depending on the curvature)
 >   
>3. Transform Klein Coordinates to Poincare Coordinates (a simple formula to apply in a geometry node)
>    
>4. New vertex is rotated (with a Möbius transform) depending on which of the 6 sides of the hypercube the floor is on (a geometry node again).
 >   
>5. All vertices now rotate (with a Möbius transform) based on the camera's position/rotation  (a geometry node again).
  >  
>6. Scene can be rendered at this point.


Words that I don’t understand -

1. Klein coordinates -  
    These are a way to represent points in hyperbolic space. Rescaling to Klein coordinates involves applying a scale factor depending on the curvature of the space.
    
2. Poincare Coordinates -  
    Another type of coordinate system used in hyperbolic geometry. Transforming from Klein to Poincaré coordinates can be done using a simple formula.
    
3. Möbius transform -  
    A type of function used in complex analysis. In this context, it's used to rotate vertices based on certain conditions, like the position of the camera or the side of the hypercube.
    
4. Hypercube -  
    A geometric shape that extends the concept of a square (in 2D) or a cube (in 3D) into higher dimensions.
    

## Co-Pilot Convo

Let’s break down each step:
### Step 1
#### Start with each mesh in a unit volume 1x1x1:
This means that you start with a 3D model (or mesh) that fits within a cube of side length 1. This is a common practice in 3D modeling to ensure that the model will scale correctly in different scenes.  

### Step 2
#### Rescale to convert the Unit volume to Klein coordinates:
Klein coordinates are used in the context of hyperbolic geometry1](https://en.wikipedia.org/wiki/Beltrami%E2%80%93Klein_model). Rescaling the unit volume to Klein coordinates involves applying a scale factor that depends on the curvature of the space. This could be achieved in Blender by applying a scale transformation to the mesh.  
  
Here’s a step-by-step guide on how to rescale a unit volume to Klein coordinates in Blender:


1. Open Blender: Start by opening Blender and importing or creating the 3D model you want to work with.

2. Select the Object: Click on the object you want to rescale. [You can do this by right-clicking on the object in the 3D view1](https://blender.stackexchange.com/questions/210601/blender-scale-and-unit-problem-how-to-fix).

3. [Apply the Scale of the Object: Press Ctrl + A to bring up the apply menu, then select Scale to apply the current scale of the object1](https://blender.stackexchange.com/questions/210601/blender-scale-and-unit-problem-how-to-fix)[2](https://blenderbasecamp.com/how-to-change-my-unit-measurements-in-blender/).

4. Adjust the Dimensions: In the <font color="#00b050">N</font> panel, there is an additional box named Dimensions right under the Scale values. [That displays the bounding box size of the active object](https://blender.stackexchange.com/questions/210601/blender-scale-and-unit-problem-how-to-fix)[3](https://www.youtube.com/watch?v=UgvNa-mJkjo). [You can directly enter your values there, which changes the scale](https://blender.stackexchange.com/questions/210601/blender-scale-and-unit-problem-how-to-fix)[3](https://www.youtube.com/watch?v=UgvNa-mJkjo).

5. Calculate the [[Scale Factor]]: The scale factor depends on the curvature of the space in hyperbolic geometry. Once you have this value, you can use it to rescale your object.  

6. [Rescale the Object: Press S for scaling, then type in the scale factor into the number pad and hit Enter](https://blender.stackexchange.com/questions/210601/blender-scale-and-unit-problem-how-to-fix)[4](https://blender.stackexchange.com/questions/159562/how-do-i-rescale-an-object-to-be-a-specified-cm-in-length-and-have-the-rest-of-t). This will rescale your object to Klein coordinates.  

### Step 3
#### Transform Klein Coordinates to Poincare Coordinates:
[Poincaré coordinates are another type of coordinate system used in hyperbolic geometry2](https://en.wikipedia.org/wiki/Coordinate_systems_for_the_hyperbolic_plane). The transformation from Klein to Poincaré coordinates can be done using a simple formula, which can be implemented in a geometry node in Blender.
To transform environment photoscans into a non-Euclidean spherical geometry, you'll need to define a Möbius transformation that maps points from your original Euclidean space to the desired non-Euclidean spherical space. Here's a general approach to defining such a transformation:

1. **Understand the Euclidean and Spherical Geometry**: Before defining the transformation, it's essential to understand the differences between Euclidean and spherical geometries. In Euclidean geometry, the familiar geometry of flat surfaces like planes and cubes applies, while in spherical geometry, the geometry of the surface of a sphere applies, where lines are great circles and angles may be different.

2. **Choose a Projection**: Decide on a specific projection method to map points from the Euclidean space of your environment photoscans to the non-Euclidean spherical space. Common choices include:

   - Stereographic Projection: Maps points from a plane to a sphere by projecting from a point (the "North Pole") onto the sphere's surface.
   - Gnomonic Projection: Maps points from a plane to a sphere by projecting from the sphere's center onto its surface.
   - Mercator Projection: A cylindrical map projection that can be adapted to create a spherical effect.

3. **[[Implement the Transformation]]**: Once you have the transformation equation, you can implement it in your software environment, such as Blender. This might involve creating custom shaders or scripts to apply the transformation to your environment photoscans.

Keep in mind that the specific transformation equation may vary depending on factors like the chosen projection method and the characteristics of your environment photoscans. Additionally, adjusting parameters such as the position of the "North Pole" or the scale of the transformation may be necessary to achieve the desired result.
### Step 4
#### New vertex is rotated (with a Möbius transform) depending on which of the 6 sides of the hypercube the floor is on:
A Möbius transformation is a type of function used in complex analysis that has interesting properties, such as preserving angles and transforming circles and lines into other circles or lines3](https://en.wikipedia.org/wiki/M%C3%B6bius_transformation). In this step, each vertex of the mesh is rotated based on which side of the hypercube it’s on. This can be done using a geometry node in Blender that applies the appropriate Möbius transformation.  
  
Here’s a step-by-step guide on how to rotate a vertex with a Möbius transformation in Blender:


1. Open Blender: Start by opening Blender and importing or creating the 3D model you want to work with.

2. Create a Geometry Node: In the Geometry Node Editor, create a new geometry node for your object.

3. Add an Attribute Node: In the geometry node, add an Attribute node. This will allow you to create a new attribute for your object that will store the rotated coordinates.

4. Define the Möbius Transformation: 
   A Möbius transformation is a complex function that can be defined using rotation matrices. You will need to create two rotation matrices: one for the major axis and one for the minor axis. The rotation along the major axis can be defined as 
   rot_theta = Matrix.Rotation(theta, 3, [0, 0, 1]) 
   and the rotation along the minor axis can be defined as
   rot_phi = Matrix.Rotation(phi, 3, [0, 1, 0]).

5. Implement the Transformation: Implement this transformation in the Attribute node. This will rotate each vertex of your object based on which side of the hypercube it’s on.

6. Apply the Transformation: Finally, apply the transformation to your object. You can do this by connecting the Attribute node to the Output node in the geometry node1.  
  
Source: [https://vishusandy.github.io/mobius-strip/  
  
](https://vishusandy.github.io/mobius-strip/)


Please note that the specific formula for the Möbius transformation would depend on the specific curvature of your hyperbolic space, which is not covered in this guide. You might need to look up more detailed tutorials or documentation for each step, especially for implementing the specific transformations in geometry nodes.

### Step 5
#### All vertices now rotate (with a Möbius transform) based on the camera’s position/rotation:
This is similar to the previous step, but now the rotation of each vertex depends on the position and rotation of the camera. This can also be achieved using a geometry node in Blender.  
  
Here’s a step-by-step guide on how to rotate all vertices with a Möbius transformation based on the camera’s position/rotation in Blender:


1. Open Blender: Start by opening Blender and importing or creating the 3D model you want to work with.

2. Create a Geometry Node: In the Geometry Node Editor, create a new geometry node for your object.

3. Add an Attribute Node: In the geometry node, add an Attribute node. This will allow you to create a new attribute for your object that will store the rotated coordinates.

4. Define the Möbius Transformation: A Möbius transformation is a complex function that can be defined using rotation matrices. You will need to create two rotation matrices: one for the major axis and one for the minor axis. The rotation along the major axis can be defined as  
    rot_theta = Matrix.Rotation(theta, 3, [0, 0, 1])  
    and the rotation along the minor axis can be defined as  
    rot_phi = Matrix.Rotation(phi, 3, [0, 1, 0]).
    
5. Implement the Transformation: Implement this transformation in the Attribute node. This will rotate each vertex of your object based on the position and rotation of the camera.
    
6. Apply the Transformation: Finally, apply the transformation to your object. You can do this by connecting the Attribute node to the Output node in the geometry node.
    

Please note that the specific formula for the Möbius transformation would depend on the specific curvature of your hyperbolic space, which is not covered in this guide. You might need to look up more detailed tutorials or documentation for each step, especially for implementing the specific transformations in geometry nodes.

### Step 6
#### Scene can be rendered at this point:
After all these transformations, the 3D scene is ready to be rendered. In Blender, this would involve setting up the camera and lighting, and then rendering the scene using the render engine.

Please note that while I’ve provided a high-level overview of how you might implement these steps in Blender, the specifics could vary depending on the details of the scene and the models you’re working with. You might need to look up more detailed tutorials or documentation for each step, especially for implementing the specific transformations in geometry nodes.
