---
layout: post
title:  "Destruction physics in unity"
date:   2018/04/15
author: Oscar Johnson
galleries:
  - title: Voronoi with fuzzy boundaries
    image: https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Approximate_Voronoi_Diagram.svg/220px-Approximate_Voronoi_Diagram.svg.png
    url: https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Approximate_Voronoi_Diagram.svg/220px-Approximate_Voronoi_Diagram.svg.png
  - title: Example of a randomly generated voronoi
    image: https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Voronoi_growth_euclidean.gif/220px-Voronoi_growth_euclidean.gif
    url: https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Voronoi_growth_euclidean.gif/220px-Voronoi_growth_euclidean.gif
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/DggxVVvJLi8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---
### About
Another project in unity 3D! This time to create a system that allowed for the destruction of convex meshes in a realistic fashion. 

This project started out by looking at [Voronoi diagrams](https://mathworld.wolfram.com/VoronoiDiagram.html) and the implementation of an algorithm that would generate these patterns and then slice up meshes into sections based on randomly generated nodes. This way the system would be able to create realistic looking destruction of props in a scene.

{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}

After a quick 2D version of the Voronoi function was implemented, that placed randomly generated nodes across a 2D plane and calculated the boundaries between them, a mesh slicing function was build to cut across these boundaries to break the object down into primitives. This function worked by taking a plane, looking for intersections in existing triangles in the polygon and deleting them. Any triangles not intersected were sorted out into sides (Left or right of the plane) and triangles intersecting the plane would have vertices added across the cutting line that would be used to rebuild the intersected triangles and also to rebuild the face on both sides of the cut. This would result in one object being split into two.

<img src="https://wiki.freecadweb.org/images/thumb/a/a9/Part_Slice_Demo.png/600px-Part_Slice_Demo.png">

More research was required however as upon implementing the Voronoi algorithm in 2D, the tax on the system of then slicing mesh down into primitives was too high and there was a series of erroneous behavior (Probably to do with the high system cost) that made the project too complex for the 3 week deadline I had. Therefore a more simple approach was required.

Sticking with the same mesh slicing function, a simple function was created to randomly generate a point inside the 3D mesh and then place a series of slices pivoting around that point. This resulted in quite an interesting shattering effect that can be seen in the video above.

This project was coded in c# for unity and can be viewed in the github repository [here](https://github.com/JohnnersUK/Modifying-Meshes).

