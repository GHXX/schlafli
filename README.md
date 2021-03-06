# schlafli
openGL viewer for Polytopes and Tesselations of any dimension
![Great Stellated 120-cell](https://raw.githubusercontent.com/aruth2/schlafli/master/120cell.gif)

This code comes in 2 main parts. The interpreter is passed a schlafli symbol and produces the geometrical description of the polytope, and the viewer displays and/or manipulates the polytope. The interpreters are written in python and ruby whereas the viewer is written in C.

**TO USE:**

Compile the file with make. This was tested using the freeglut3 implementation of openGL. 

    make

Execute the code. Some default symbols are accessible within the right-click menu.

    make test

Alternatively, execute the code by providing it a description of the geometry (e.g.)

    ./polytope -symbol "5/2 3 5" -scale 2.5

Commandline options are (Any order is accepted but options with "-" are expected to be followed by something):

    -symbol "[schlafli symbol]"
    -scale [multiplier] - scales the geometry of the shape by the multiplier
    -schlegeldistance [distance] - specifies the distance from the origin used in schlegel projection
    -pointsize [size]
    -linewidth [size]
    schlegel3d - {default} projects a more-than-3 dimensional shape into 3 dimensions using the schlegel projection method.
    schlegel2d - projects a more-than-2 dimensional shape into 2 dimensions using the schlegel projection method.
    points - draw points
    wireframe - {default} draw edges
    solid - draw faces. Misbehaves when drawing star polytopes because GL_POLYGON does not support concave shapes
    
*Explanation of Schlafli symbol:*

Based upon a community-answered question at: https://codegolf.stackexchange.com/questions/114280/schläfli-convex-regular-polytope-interpreter

Thanks to Level River St and Don Hatch for providing code to generate polytopes.

The Schläfli Symbol is a notation of the form {p,q,r,...} that defines regular polytopes and tessellations.

The Schläfli symbol is a recursive description, starting with a p-sided regular polygon as {p}. For example, {3} is an equilateral triangle, {4} is a square and so on.

A regular polyhedron that has q regular p-sided polygon faces around each vertex is represented by {p,q}. For example, the cube has 3 squares around each vertex and is represented by {4,3}.

A regular 4-dimensional polytope, with r {p,q} regular polyhedral cells around each edge is represented by {p,q,r}. For example a tesseract, {4,3,3}, has 3 cubes, {4,3}, around an edge.

In general a regular polytope {p,q,r,...,y,z} has z {p,q,r,...,y} facets around every peak, where a peak is a vertex in a polyhedron, an edge in a 4-polytope, a face in a 5-polytope, a cell in a 6-polytope, and an (n-3)-face in an n-polytope.

A regular polytope has a regular vertex figure. The vertex figure of a regular polytope {p,q,r,...y,z} is {q,r,...y,z}.

Regular polytopes can have star polygon elements, like the pentagram, with symbol {5/2}, represented by the vertices of a pentagon but connected alternately.



