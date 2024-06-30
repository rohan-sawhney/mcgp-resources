<img src="imgs/logo.gif" height="64" width="84" align="right" />

# Resources on Monte Carlo Geometry Processing

**Course Material**: Links to [webpage](https://www.google.com/), recordings [[pre-recorded](https://youtu.be/cmgNqCwaPYc), live (coming soon!)] and slides [[keynote](https://github.com/rohan-sawhney/mcgp-resources.github.io/blob/main/MCGP-slides.key), [pdf](https://github.com/rohan-sawhney/mcgp-resources.github.io/blob/main/MCGP-slides.pdf)].

**Abstract**: Accurately analyzing large amounts of geometric data is critical for many scientific and engineering applications. Techniques based on _partial differential equations (PDEs)_ provide powerful tools for analyzing physical systems, but conventional solvers are not yet at a stage where they “just work” on problems of real-world complexity. A constant challenge is spatial discretization, which divides the domain into a high-quality volumetric mesh for PDE-based analysis. Unfortunately, this approach does not scale well to modern computer architectures, and as such, there remains a large divide between our ability to _visualize_ and _analyze_ the natural world.

The [walk on spheres (WoS)](https://en.wikipedia.org/wiki/Walk-on-spheres_method) algorithm makes a radical departure from conventional PDE solvers, by reformulating fundamental PDEs like the Poisson equation as recursive integrals that can be solved using the Monte Carlo method. Since these integrals closely resemble those in light transport, one can leverage deep knowledge from [Monte Carlo rendering](https://pbrt.org) to build new scalable algorithms with vastly different numerical tradeoffs, such as avoiding volumetric meshing altogether.

This course, presented at the [Symposium on Geometry Processing Graduate School](https://sgp2024.github.io/program/#graduate-school), provides a broad overview of grid-free Monte Carlo methods for PDEs, with an emphasis on teaching the key principles of Monte Carlo, from sample generation and variance reduction to system design, by ways of WoS and its recent generalizations.

## Associated Publications and Code

The course material is based on the following publications:
> Monte Carlo Geometry Processing [[Project](https://www.cs.cmu.edu/~kmcrane/Projects/MonteCarloGeometryProcessing/index.html), [Paper](http://www.rohansawhney.io/mcgp.pdf), [PhD thesis](http://rohansawhney.io/RohanSawhneyPhDThesis.pdf), [Talk](https://www.youtube.com/watch?v=zl9GtPX0LjM&feature=youtu.be)]<br>
> Walk on Stars: Grid-Free Monte Carlo for PDEs with Neumann Boundary Conditions [[Project](https://www.cs.cmu.edu/~kmcrane/Projects/WalkOnStars/index.html), [Paper](http://www.rohansawhney.io/WalkOnStars.pdf), [Talk](https://youtu.be/InWVU68KhMs)]<br>
> Walkin' Robin: Walk on Stars with Robin Boundary Conditions [[Project](https://imaging.cs.cmu.edu/walk_on_stars_robin/), [Paper](http://www.rohansawhney.io/WoStRobin.pdf)]<br>
> Grid-Free Monte Carlo for PDEs with Spatially Varying Coefficients [[Project](https://cs.dartmouth.edu/wjarosz/publications/sawhneyseyb22gridfree.html), [Paper](http://www.rohansawhney.io/vcwos.pdf), [Talk](https://www.youtube.com/watch?v=dXROl0KGPXc)]<br>
> Boundary Value Caching for Walk on Spheres [[Paper](http://www.rohansawhney.io/BoundaryValueCaching.pdf), [Talk](https://www.youtube.com/watch?v=J9o7kgrpco0)]

All solvers and geometric queries are implemented in the open-source [Zombie](https://github.com/rohan-sawhney/zombie) and [FCPW](https://github.com/rohan-sawhney/fcpw) libraries (respectively). Also checkout the following basic code examples: [WoS for Laplace](https://www.cs.cmu.edu/~kmcrane/Projects/MonteCarloGeometryProcessing/WoSLaplace2D.cpp.html), [WoS for Poisson](https://www.cs.cmu.edu/~kmcrane/Projects/MonteCarloGeometryProcessing/WoSPoisson2D.cpp.html), [WoSt step-by-step tutorial](https://github.com/GeometryCollective/wost-simple).

## Additional Resources (will be updated regularly)

WoS relies on and connects rich concepts from Monte Carlo methods, PDEs, and stochastic differential equations: from a [harmonic analysis](https://en.wikipedia.org/wiki/Harmonic_function) perspective, WoS is a Monte Carlo method for solving [Laplace equations](https://en.wikipedia.org/wiki/Laplace's_equation), while from a [random process](https://en.wikipedia.org/wiki/Stochastic_process) perspective, it is an acceleration strategy for simulating [Brownian motion](https://en.wikipedia.org/wiki/Brownian_motion). Here are some enjoyable reference resources on these topics:

> CMU 21-387: Monte Carlo Methods and Applications [[Course webpage](https://geometrycollective.github.io/monte-carlo/mcma-fa2023.html)]\
> Monte Carlo Methods - a special topics course [[Book](https://math.arizona.edu/~tgk/mc/book.pdf)]\
> Physically Based Rendering: From Theory To Practice [[Book](https://pbrt.org)] - _Goto reference_ for MC rendering

> Harmonic Function Theory [[Book](https://www.axler.net/HFT.pdf)]\
> Partial Differential Equations by Lawrence C. Evans [[Book](https://books.google.com/books?hl=en&lr=&id=Ott1EAAAQBAJ&oi=fnd&pg=PP1&dq=%22Partial+Differential+Equations%22+by+L.+C.+Evans&ots=cVFCwE3VzM&sig=06kAKV2mAvSUM6LyxvIUEzfJN28#v=onepage&q=%22Partial%20Differential%20Equations%22%20by%20L.%20C.%20Evans&f=false)]

> Stochastic Differential Equations by Bernt Øksendal [[Book](http://www.stat.ucla.edu/~ywu/research/documents/StochasticDifferentialEquations.pdf)]\
> Handbook of Brownian Motion - Facts and Formulae [[Book](https://link.springer.com/book/10.1007/978-3-0348-8163-0)]\
> Einstein's Investigations on the Theory of Brownian Movement from 1926! [[Book](https://www.amazon.com/Investigations-Theory-Brownian-Movement-Physics/dp/0486603040)]

> Some Continuous Monte Carlo Methods for the Dirichlet Problem [[Mervin Muller's original paper on WoS](https://projecteuclid.org/journals/annals-of-mathematical-statistics/volume-27/issue-3/Some-Continuous-Monte-Carlo-Methods-for-the-Dirichlet-Problem/10.1214/aoms/1177728169.full)]\
> The Rate of Convergence of the Walk on Spheres Algorithm [[Paper](https://mbraverm.princeton.edu/files/AttachBBlocaldim.pdf)]

WoS has recently seen growing interest in computer graphics, as it shares many computational benefits with [Monte Carlo rendering](https://pbrt.org): logarithmic scaling with geometric detail, robustness, trivial parallelism, output-sensitive evaluation, and the ability to work with different geometric representations. Beyond our [own work](https://github.com/rohan-sawhney/mcgp-resources/tree/main?tab=readme-ov-file#associated-publications-and-code) on the topic, here is a non-exhaustive list of publications on advanced/alternative WoS estimators:

> Kelvin Transformations for Simulations on Infinite Domains [[Project](https://cseweb.ucsd.edu/~viscomp/projects/SIG21KelvinTransform/), [Paper](https://cseweb.ucsd.edu/~viscomp/projects/SIG21KelvinTransform/paper/KelvinTransform.pdf)]\
> Coupling Conduction, Convection and Radiative Transfer in a Single Path-Space [[Project](https://www.irit.fr/STORM/site/coupling-conduction-convection-and-radiative-transfer-in-a-single-path-space/), [Paper](https://hal.science/hal-04090428)]\
> A Monte Carlo Method for Fluid Simulation [[Project](https://riouxld21.github.io/research/publication/2022-mcfluid/), [Paper](https://riouxld21.github.io/research/publication/MCFluid.pdf)]\
> Velocity-Based Monte Carlo Fluids [[Project](https://rsugimoto.net/VelMCFluidsProject/), [Paper](https://rsugimoto.net/VelMCFluidsProject/VelMCFluids.pdf)]\
> Neural Monte Carlo Fluid Simulation [[Project](https://pranav-jain.github.io/projects/nmcfs/index.html), [Paper](https://pranav-jain.github.io/projects/nmcfs/nmcfs.pdf)]\
> A Differential Monte Carlo Solver For the Poisson Equation [[Project](https://www.shuangz.com/projects/diff-wos-sg24/), [Paper](https://www.shuangz.com/projects/diff-wos-sg24/diff-wos-sg24.pdf)]\
> Solving Inverse PDE Problems using Grid-Free Monte Carlo Estimators [[Paper](https://arxiv.org/pdf/2208.02114)]\
> Heat Simulation on Meshless Crafted-Made Shapes [[Paper](https://dl.acm.org/doi/pdf/10.1145/3623264.3624457?casa_token=xzk76-QIKEsAAAAA:Le6WPwP9lhf9HrVZj9Ueyvbb2aZUq514VHryxtHE55z63bWW7FfeHf8-6MrI5vQEN1YTlcadf3-3)]\
> A Practical Walk-on-Boundary Method for Boundary Value Problems [[Project](https://rsugimoto.net/WoBforBVPsProject/), [Paper](https://rsugimoto.net/WoBforBVPsProject/WoBforBVPs.pdf)]\
> Walk on Spheres for PDE-based Path Planning [[Paper](https://arxiv.org/pdf/2406.01713)]\
> Stochastic Computation of Barycentric Coordinates [[Paper](https://graphics.pixar.com/library/StochasticCoordinates/paper.pdf)]

as well as strategies for improving efficiency and increasing applicability to more boundary representations:

> A Bidirectional Formulation for Walk on Spheres [[Project](https://cs.dartmouth.edu/~wjarosz/publications/qi22bidirectional.html), [Paper](https://cs.dartmouth.edu/~wjarosz/publications/qi22bidirectional.pdf)]\
> Mean Value Caching for Walk on Spheres [[Paper](https://diglib.eg.org/items/490fc1c8-790c-4bab-8a4b-04166e5ac91d)]\
> Neural Caches for Monte Carlo Partial Differential Equation Solver [[Project](https://zilulii.github.io/cache-website/), [Paper](https://zilulii.github.io/cache-website/assets/SA23_upload.pdf)]\
> Solving Poisson Equations using Neural Walk-on-Spheres [[Paper](https://openreview.net/pdf?id=dQveBV9lZl)]\
> Discontinuity-Aware 2D Neural Fields [[Project](https://yashbelhe.github.io/danf/index.html), [Paper](https://yashbelhe.github.io/danf/DiscontinuityAwareNeuralFields_SigAsia2023.pdf)]\
> GPU-Accelerated Monte Carlo Geometry Processing for Gradient-Domain Methods [[Paper](https://www.diva-portal.org/smash/get/diva2:1627037/FULLTEXT01.pdf)]\
> Hierarchical Point Distance Fields [[Paper](https://dl.acm.org/doi/abs/10.1007/978-3-030-90436-4_35)]\
> Spelunking the deep: Guaranteed queries on neural implicit surfaces via range analysis [[Project](https://nmwsharp.com/research/interval-implicits/), [Paper](https://nmwsharp.com/media/papers/interval-implicits/SpelunkingTheDeep.pdf)]\
> Ray Tracing Harmonic Functions [[Project](https://markjgillespie.com/Research/harnack-tracing/index.html), [Paper](https://markjgillespie.com/Research/harnack-tracing/HarnackTracing.pdf)]

Also, here are a few fun educational demos, blogs and tweets:

> ShaderToy demos [[implicit surface](https://www.shadertoy.com/view/wdffWj), [curve inflation](https://www.shadertoy.com/view/7tyyzW), [diffusion curves](https://www.shadertoy.com/view/WdXfzl)]\
> Blogs [[demofox](https://blog.demofox.org/2020/07/11/interpolating-data-over-arbitrary-shapes-with-laplaces-equation-and-walk-on-spheres/), [javascript implementation](https://observablehq.com/@fil/walk-on-spheres)]\
> Tweets [[MCGP](https://x.com/keenanisalive/status/1258152669727899650), [WoSt](https://x.com/keenanisalive/status/1674890996814090240), [Variable Coefficients](https://x.com/keenanisalive/status/1526156137971728385), [Path Planning](https://x.com/rms80/status/1317532899302805504)]

## Course Contributors

[Rohan Sawhney](http://www.rohansawhney.io)\
[Bailey Miller](https://www.bailey-miller.com)

## Citation

If you want to cite this course, use the following BibTeX:
```
@inproceedings{Sawhney:2024:MCGP,
    author = {Sawhney, Rohan and Miller, Bailey},
    booktitle = {SGP 2024 Graduate School Courses},
    title = {Monte Carlo Geometry Processing},
    year = {2024}}
```

## License

This tutorial is licensed under the [CC BY 4.0 license](LICENSE.txt).
