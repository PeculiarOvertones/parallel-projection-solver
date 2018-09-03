# parallel-projection-solver
This code calculates the projection of microstructure on a plane.
The STL geometry is centered at the origin.
A plane is also centered at the origin and it can be aligned in (+/-) X, Y, Z directions.
The plane can be rotated in 3D by specifying Euler angles alpha, beta, and gamma.
First, cells lying inside the geometry are tagged (InOutFlag).
Then, a ray is sent along the direction of the normal to find out the intersection of panels lying above the plane.
Finally, with enough refinement of the plane, accurate area can be computed.

I have parallelized the code using MPI. The partitioning strategy is naive but serves the purpose.
The images shown in the Output folder are calculated using 1,024 processors for a 512x512 grid.
I cannot provide the STL geometry because it was created for my research project on ablative materials.

To group the files from multiple processors generated in Output, the python script groupPlanes.py is provided.

I took matrix.hpp, nvector.hpp, and parts of ops.hpp files from Makram Kamaleddine on Github.
Happy coding!
