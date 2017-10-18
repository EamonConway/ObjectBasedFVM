# ObjectBasedFVM

The plan is to form a library of objects for use in the Finite Volume method. 
The mesh elements will be used to create element objects. 
These objects will be capable of returning information required, given a specific interpolant (bilinear,linear)
This will allow for a construction of the flux which can then be used in your own personal timestepping.

Eg// Bilinear FVM
element object 
  element.field(f1,f2,f3,f4) - returns values of the field at the four faces
  element.grad(f1,f2,f2,f3) - returns the gradient of the field at the four faces (dotted with unit normal)
  element.grad_n - returns the gradient of the field at the four faces (dotted with unit normal)
  element.Jacobian - return jacobian mapping?? 
  
Importantly, these objects should be constructed such that if the mesh is mixed element, the object takes that into account.
Will require minimal input from the use, but should still return consistent results. 

To be done// 
  - Class MESH_ELEMENT
  - Calculate Control Volume size
  - Extend MESH_ELEMENT to do both surface integral and volume integral (Gauss Points for both)
  - Current thought is a for loop over each element, could this be done in a more intelligent way ? 
  - Can this definition of MESH_ELEMENT interface with something more complicated such as a quadtree structure for mesh refinement
  - 
  
