---
title: UAV Propeller 
keywords: tutorial, uav propeller
summary: 
sidebar: mydoc_sidebar
permalink: mydoc_tutorials_aerostruct_uav_prop.html
folder: mydoc
---

{% include note.html content="We recommend going through the tutorial in [Get started](mydoc_get_started_download_docker.html) before running this case." %}

The following is an aerostructural shape optimization case for the UAV propeller in hover. The baseline design is an untwisted, untapered NACA 0012 propeller blade. The flow is solved using the DARhoSimpleFoam CFD solver and the structure is solved using an open-source FEM solver [TACS](https://github.com/smdogroup/tacs). The load and displacement transfer is computed using [FUNtoFEM](https://github.com/smdogroup/funtofem). The aerostructural coupling is implemented in the [OpenMDAO/Mphys](https://github.com/OpenMDAO/mphys) framework.

<pre>
Case: Propeller aerostructural optimization 
Geometry: NACA 0012 UAV Propeller 
Objective function: Shaft Power Coefficient
Design variables: 6 twist variables, 72 shape variables, 6 chord variables, rotation speed
Constraints: Thrust coefficient, propeller thickness, propeller spanwise curvature, leading edge, and mass
RPM: 5000
Reynolds number: 180 thousand
Mesh cells: ~1.5 million
Solver: DARhoSimpleFoam
</pre>

<img src="{{ site.url }}{{ site.baseurl }}/images/tutorials/Prop_Solid_Mesh.png" width="500" />

Figure 1. Propeller solid FEM mesh. The blue and red dots are the FFD points, where the blue dots are the only ones that move during the optimization.
