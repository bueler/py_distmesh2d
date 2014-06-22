py_fem_distmesh2d
=================

Self-contained 2D finite element examples using Python and scipy and matplotlib.

The codes `py_distmesh2d.py` and `mesh_examples.py` are from [py_distmesh2d](https://github.com/ckhroulev/py_distmesh2d) by Constantine Khroulev.  They are a Python re-implementation of `distmesh2d` in *Per-Olaf Persson and Gil Strang, A Simple Mesh Generator in MATLAB. SIAM Review, Volume 46 (2), pp. 329-345, June 2004* (http://persson.berkeley.edu/distmesh/).

What's new compared to Per-Olaf's and Constantine's work?:

* `meshtools.py`: Python re-implementations of codes from the [Math 692 one-page Matlab FEM code challenge](http://www.dms.uaf.edu/~bueler/challenge.htm), which dates to Fall 2004.  These tools include `fixmesh`, `edgelist`, and `bdyrefine`

* `cg.py`: Boring implementation of the conjugate gradient method.  (See *H. Elman, D. Silvester, and A. Wathen, Finite Elements and Fast Iterative Solvers with applications in incompressible fluid dynamics.  Oxford 2005.*)  This way we don't even need `numpy.linalg.solve`.  In practice, performance for PDE problems here (as opposed to variational inequality problems) is limited by meshing, not linear algebra.

* `poisson.py`: Assemble and solve Poisson equation del^2 u = f.  See also http://www.cs.uaf.edu/~bueler/poissonv2.pdf

* `obstacle.py`: Solve the obstacle problem associated to the Poisson equation.  That is, solve the variational inequality.  See also http://www.dms.uaf.edu/~bueler/obstacleDOC.pdf

Demos
-----

Running

    $ python fem_examples.py

gives the first solution plot, which is simply a solution of Poisson's equation on a disc.

![disc solution](https://github.com/bueler/py_fem_distmesh2d/raw/master/ex_disc_soln.png)

Doing

    $ python obstacle_example.py

gives the second and third plots below, which show the solution of a Poisson-like obstacle problem on a disc with a spherical obstacle.  The third plot shows those nodes which touch the obstacle (red dots).

![spherical obstacle: solution](https://github.com/bueler/py_fem_distmesh2d/raw/master/ex_obs_soln.png)

![spherical obstacle: coincidence set](https://github.com/bueler/py_fem_distmesh2d/raw/master/ex_obs_coincidence.png)
