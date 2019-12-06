# Review paper notes
> **A Review of Motion Planning Techniques
> for Automated Vehicles**
David González, Joshué Pérez, Vicente Milanés, and Fawzi Nashashibi



---
Abstract::
Intelligent vehicles have increased their capabilities for highly and, even fully, automated driving under controlled environments. Scene information is received using onboard sensors and communication network systems, i.e., infrastructure and other vehicles. Considering the available information, different motion planning and control techniques have been implemented to autonomously driving on complex environments. The main goal is focused on executing strategies to improve safety, comfort, and energy optimization. However, research challenges such as navigation in urban dynamic environments with obstacle avoidance capabilities, i.e., vulnerable road users (VRU) and vehicles, and cooperative maneuvers among automated and semi- automated vehicles still need further efforts for a real environment implementation. This paper presents a review of motion planning techniques implemented in the intelligent vehicles literature. A description of the technique used by research teams, their contributions in motion planning, and a comparison among these techniques is also presented. Relevant works in the overtaking and obstacle avoidance maneuvers are presented, allowing the understanding of the gaps and challenges to be addressed in the next years. Finally,an overview of future research direction and applications is given.

Index Terms—Motion planning, automated vehicles, path planning, intelligent transportation systems.


---

Notes:::::::::::::::::::::::::::

![](https://i.imgur.com/c31nXC2.png)

![](https://i.imgur.com/6u3CGIc.png)

![](https://i.imgur.com/mVHbq9G.png)




---


1. the Advance Highway Systems (AHS). Behringer et al. [14]
describe the architecture proposed for the VaMoRs-L vehicle
in the PROMETHEUS project.

2. These planning techniques were classified in four groups, according to their implementation in automated driving: graph search, sampling, interpolating and numerical optimization.
3. Graph Search Based Planners In automated driving, the basic idea is to traverse a state space to get from point A to point B. This state space is often represented as an occupancy grid or lattice that depicts where objects are in the  environment.
4. Dijkstra Algorithm: It is a graph searching algorithm that
finds single-source shortest path in the graph. The onfiguration
space is approximated as a discrete cell-grid space, lattices,
among others.

5. A-Star Algorithm (A∗): It is a graph searching algorithm that
enables a fast node search due to the implementation of heuristics (it is an extension of Dijkstra’s graph search algorithm). Its most important design aspect is the determination of the cost function, which defines the weights of the nodes. It is suitable for searching spaces mostly known a priori by the vehicle [30], but costly in terms of memory and speed for vast areas.

6. the dynamic A∗ (D∗) [31], Field D∗ [32],Theta∗ [33], Anytime repairing A∗ (ARA∗) and Anytime D∗ (AD∗) [34], among others. Ziegler et al. [35] implemented the A∗ algorithm along with Voronoi cost functions for planning in unstructured spaces and parking lots.

7.State Lattice Algorithm: The algorithm uses a discrete representation of the planning area with a grid of states (often a hyper-dimensional one). This grid is referred as state lattice
over of which the motion planning search is applied [46]. The path search in this algorithm is based in local queries from a set of lattices or primitives containing all feasible features,
allowing vehicles to travel from an initial state to several others. A cost function decides the best path between the precomputed lattices. A node search algorithm is applied in different implementations.

8. B. Sampling Based Planners
These planners try to solve timing constrains—i.e., planning in high dimensional spaces—that deterministic methods cannot meet. The approach consists on randomly sampling the configuration space or state space, looking for connectivity inside it [21]. The downside is the fact that the solution is suboptimal. The most commonly used methods in robotics are the Probabilistic Roadmap Method (PRM) [93] and the Rapidly-exploring Random Tree (RRT) [94]. The latter has been extensively tested for automated vehicles.

9. Interpolating curve planners
Interpolation is defined as the process of constructing and inserting a new set of data within the range of a previously known set (reference points). This means that these algorithms take a previously set of knots (e.g., a given set of way-points describing a global road map), generating a new set of data (a smoother path) in benefit of the trajectory continuity, vehicle constraints and the dynamic environment the vehicle navigates.

10. Lines and Circles: Different segment road network can be represented by interpolating known way-points with straight and circular shapes.
11. Clothoid Curves: This type of curve is defined in terms of Fresnel integrals [73]. Using clothoid curves is possible to define trajectories with linear changes in curvature since their curvature is equal to their arc-length; making smooth ansitions
between straight segments to curved ones and vice versa.

12.Polynomial Curves: These curves are commonly implemented to meet the constraints needed in the points they interpolate, i.e. they are useful in terms of fitting position, angle and curvature constraints, among others.

13. Bézier Curves: These are parametric curves that rely on control points to define their shape. The core of Bézier curves are the Bernstein polynomials. These curves have been extensively used in CAGD applications, technical drawing, aeronautical and automotive design. The advantage of this kind of curves is their low computational cost, since the curve behavior is defined by control points.

14 Spline Curves: A spline is a piecewise polynomial parametric curve divided in sub-intervals that can be defined as polynomial curves [28], [76], b-splines [88], [89] (that can also be represented in Bézier curves [105]) or clothoid curves [99]. The junction between each sub-segment is called knot and they commonly possess a high degree of smoothness constraint at the joint between the pieces of the spline.

15.Numerical Optimization
These methods aim to minimize or maximize a function subject to different constrained variables. In path planning is often used to smooth previously computed trajectories as in [54] and also to compute trajectories from kinematic constraints [5]. Function Optimization: This technique finds a real valued function’s roots (minimize the variables outcome). It has been implemented to improve the potential field method (PFM) in mobile robotics for obstacles and narrow passages, obtaining C1 continuity


---

Discussion:::::::::::

1. the key issues when designing robotic architectures [20],
[21]. The associated constrains in the automated vehicle research area—i.e., traffic rules, high speeds or road layout—turn real-time motion planning in a critical aspect for achieving automated driving on complex environments.

2. Current challenges are associated to real-time planning calculation on dynamic environments. Urban scenarios where multiple agents—i.e., pedestrians, cyclists, other vehicles—have to be taken into account, require a continuous evaluation (and re-calculation) of the determined trajectories. The limited time for generating a new free collision trajectory with multiple dynamic obstacles is an unsolved challenge.

3. Recent developments aim to consider
some of these constrains in the planning stage leading to smooth and achievable trajectories, reducing control stage constrains. Next steps should be focused on developing algorithms able to fuse perception uncertainties with control constraints. This work has been already started by KIT [5] and CMU [108].