HexMeshSimplification
======================
This repository contains the experiment results and executable file of the paper

Singularity Structure Simplification of Hexahedral Mesh via Weighted Ranking

![img](https://github.com/ohehe/HexMeshSimplification/blob/master/example.png)

**Introduction**:
----------------------
In this paper, we propose an improved singularity structure simplification method for hexahedral (hex) meshes using a weighted ranking approach. In previous work, the selection of to-be-collapsed base complex sheets/chords is only based on their thickness, which will introduce a few closed-loops and cause an early termination of simplification and a slow convergence rate. In this paper, a new weighted ranking function is proposed by combining the valence prediction function of local singularity structure, shape quality metric of elements and the width of base complex sheets/chords together. Adaptive refinement and local optimization are also introduced to improve the uniformity and aspect ratio of mesh elements. Compared to thickness ranking methods, our weighted ranking approach can yield a simpler singularity structure with fewer base-complex components, while achieving comparable Hausdorff distance ratio and better mesh quality. Comparisons on a hex-mesh dataset are performed to demonstrate the effectiveness of the proposed method.

**Contents**:
----------------------
The simpilification results of our method with different cofficients of k_sv and k_sd are provided in 
'0.3ksv_0.7ksd_0.2ksq' and '0.4ksv_0.6ksd_0.2ksq' folder respectively, the simplification results of ranking by valence term and width term are also provided in 'valence_term' and 'width_term' folder respectively. Moreover, the mesh file (.vtk), histogram of scaled Jacobian (.png) and statistics (.txt) are included in each folder. The statistics of results includes minimum scaled Jacobian, average scaled Jacobian, Hausdorff distance ratio, the number of base-complex components, and total time.

**Usage**:
----------------------
On Windows, the executable files (.exe) of corresponding parameters are included in each folder. 
	The .exe file can run by the command that 'complex_simplification.exe SIM R B SR F input', in which 
	
	**R**--the ratio of the simplification of mesh elements,
	
	**B**--the base number for optimization iteration, 
	
	**SR**--the ratio of target simplification ratio of base-complex components,
	
	**F**--F is 1 means that input mesh include sharp feature,
	
	*input*--the name of input mesh file (.vtk).

**An example of default command:**

 complex_simplification.exe SIM 1 2 1 0 ./octree/airplane1_input_tri_hexa