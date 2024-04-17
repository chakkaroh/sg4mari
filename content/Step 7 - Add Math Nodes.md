---
title: Step 7 - Add Math Nodes
draft: false
tags:
  - example-tag
---
 
The rest of your content lives here. You can use **Markdown** here :)
#### Implement the Equation Using Math Nodes:
- Since you're dealing with a 3D mesh, you'll need to apply the transformation equation to each vertex individually.
- Use [[Attribute Nodes]] to access the coordinates of each vertex of your mesh.
- Apply the transformation equation to the x, y, and z components of each vertex's position separately using Math Nodes.

#### Break Down the Equation:
1. **Calculate Denominator**: The denominator in the equation is $$ 1 + x^2 + y^2 $$ Use Math nodes to calculate this value separately.

2. **Calculate $$ \frac{2x}{\text{Denominator}} $$** Use a Divide node to divide  $$2x$$ by the denominator.

3. **Calculate $$ \frac{2y}{\text{Denominator}} $$** Use another Divide node to divide $$ 2y $$ by the denominator.

4. **Calculate $$ \frac{x^2 + y^2 - 1}{\text{Denominator}} $$**: Use Subtract and Divide nodes to implement this part of the equation.

#### Apply the Transformation:

- Use Combine XYZ Nodes to combine the transformed x, y, and z components into new vertex positions.
- Replace the original vertex positions with the transformed positions using Attribute Nodes and Set Position Nodes.

#### Test and Iterate:

- Switch to the 3D Viewport to see the result of the transformation applied to your complex 3D mesh.
- Fine-tune the parameters and adjustments as needed to achieve the desired result.

By following these adjusted steps, you can implement the transformation in Blender using Math Nodes to create a non-Euclidean spherical geometry from your complex 3D mesh.