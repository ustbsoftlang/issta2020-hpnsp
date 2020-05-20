# The information of Test Cases and Bugs

For a pdf version, please refer to the file *"the information of Test Cases and Bugs.pdf"*



### 1. Programs

#### a) ANT-MOC

Input：

| Name              | Meaning                                        |
| ----------------- | ---------------------------------------------- |
| Geometry          | Geometric input files                          |
| Global Primitives | Supplemental geometry data file                |
| Materials         | Material data files                            |
| XS File Layout    | Material data structure file                   |
| Tally Mesh        | A grid about reaction rate output              |
| Num Azims         | The number of azimuths                         |
| Azim Spacing      | Track spacing of the azimuth plane             |
| Num Polars        | The number of polars                           |
| Polar Spacing     | Track spacing of the polar plane               |
| Global Refines    | Type of refines                                |
| Z Mesh            | Type of axial network                          |
| Quadrature        | Quadrature type                                |
| Solver            | Solver type                                    |
| Keff Type         | Calculating k-eff using neutron balance or not |
| Max Iterations    | Maximum number of iterations                   |
| Tolerance         | Tolerance of convergence                       |
| Segmentation      | Type of track segmentation                     |
| Axial Zones       | Overlapping plane axial layer                  |



Output:

**keff** : Effective value-added factors.



#### b) MISA-MD:

Input:

| Module                   | Name                 | Meaning                                                      |
| ------------------------ | -------------------- | ------------------------------------------------------------ |
| [simulation]             | phasespace           | the size of the simulate box, describing the number of lattices on each dimension |
|                          | cutoff_radius_factor | Truncation radius, calculating the maximum distance of the index when the force is affected between two atoms |
|                          | lattice_const        | Related to atomic type                                       |
|                          | timesteps            | number of time steps during the whole simulation             |
|                          | timesteps_length     | time step                                                    |
| [simulation.createphase] | create_phase         | Reading atoms from a file or creating atoms                  |
|                          | create_t_set         | the initial temperature                                      |
|                          | create_seed          | random seed                                                  |
| [simulation.alloy]       | create_seed          | random seek for creating atoms in Fe-Cu-Ni alloy material    |
|                          | fe                   | the percentage of Fe in Fe-Cu-Ni alloy material              |
|                          | cu                   | the percentage of Cu in Fe-Cu-Ni alloy material              |
|                          | ni                   | the percentage of Ni in Fe-Cu-Ni alloy material              |
| [simulation.collision]   | collision_step       | a parameter of cascading collisions                          |
|                          | lat                  |                                                              |
|                          | energy               | the energy of Primary Knock-on Atom                          |
|                          | direction            | the direction of Primary Knock-on Atom                       |



Output:

| Name          | Meaning                         |
| ------------- | ------------------------------- |
| T             | System temperature              |
| E             | System energy                   |
| lattice_const | lattice constant                |
| id            | atom id                         |
| step          | time step                       |
| type          | atom type                       |
| inter_type    | inter-atom type                 |
| locate.x      | x coordinates of the atom       |
| locate.y      | y coordinates of the atom       |
| locate.z      | z coordinates of the atom       |
| v.x           | x-directional speed of the atom |
| v.y           | y-directional speed of the atom |
| v.z           | z-directional speed of the atom |



#### c) MISA-SCD:

Input:

| Name                                    | Meaning                                                      |
| --------------------------------------- | ------------------------------------------------------------ |
| defectFile                              | The defect attributes file                                   |
| meshFile                                | The mesh file                                                |
| irradiationType                         | Type of irradiation (‘Cascade’ for neutron irradiation, ‘FrenkelPair’ for electron irradiation, ‘None’ for no irradiation) |
| $\color{red}\textrm{implantScheme}$     | $\color{red}\textrm{Toggle between Monte Carlo defect implantation and explicit defect implantation}$ |
| cascadeFile                             | The cascade defects file                                     |
| implantType                             | Where  uniformly implanting defects.                         |
| implantFile                             | The  data file containing non-uniform implantation profile.  |
| grainBoundaries                         | Toggle  whether we are going to include the effect of grain boundaries. |
| pointDefect                             | Toggle  whether point defects are allowed to move only.      |
| temperature                             | Temperature  (K)                                             |
| soluteConcentration                     | Initial  content of solute atoms (Cu) in iron.               |
| $\color{red}\textrm{numVac}$            | $\color{red}\textrm{Initial number of vacancies in the simulation system.}$ |
| dpaRate                                 | The  rate of DPA.                                            |
| totalDPA                                | Radiation  enhanced factor for Cu.                           |
| $\color{red}\textrm{annealTemperature}$ | $\color{red}\textrm{Annealing temperature (K).}$             |
| $\color{red}\textrm{annealTime}$        | $\color{red}\textrm{Total anneal time.}$                     |
| lattice                                 | The  lattice constant (nm).                                  |
| burgers                                 | Dislocation  loop burgers vector (nm).                       |
| reactionRadius                          | Reaction  distances (nm).                                    |
| grainSize                               | Grain  size (nm).                                            |
| dislocDensity                           | Dislocation  density ($$nm^{-2}$$).                          |
| cascadeVolume                           | Volume  of cascade ($$nm^{3}$$) .                            |
| $\color{red}\textrm{max3D}$             | $\color{red}\textrm{Maximum size for SIA defect to diffuse in 3D.}$ |
| $\color{red}\textrm{numSims}$           | $\color{red}\textrm{Number of times to repeat simulation.}$  |
| $\color{red}\textrm{totdatToggle}$      | $\color{red}\textrm{Toggle whether the total defects file is output . (The file  contains number of ever defect species, cluster number densities, average  cluster size, average radius of clusters and so on.)}$ |
| $\color{red}\textrm{minSolute}$         | $\color{red}\textrm{The minimum size of solute clusters included in the statistics.}$ |
| $\color{red}\textrm{minVoid}$           | $\color{red}\textrm{The minimum size of vacancy clusters included in the statistics.}$ |
| $\color{red}\textrm{minLoop}$           | $\color{red}\textrm{The minimum size of SIA clusters included in the statistics.}$ |
| $\color{red}\textrm{minVS}$             | $\color{red}\textrm{The minimum size of S_Vac clusters included in the statistics.}$ |

------

Output:

**CuCluster**: the number of Cu Cluster.



#### d) MISA-ETD

Input: 

| Name           | Meaning                                |
| -------------- | -------------------------------------- |
| maxClusterSize | the max cluster size during simulation |
| totalTime      | simulation time                        |
| timeStep       | time step                              |
| Cinit          | the initial concentration of cluster   |



Output:

 **[n, c]**: cluster size and cluster concentration.



#### e) ATHENA

Input :

Too many parameters, you can refer to the file "*./test/input/ATHENA/Input information of ATHENA.docx*".



Output:

| Name                   | Meaning                                                      |
| ---------------------- | ------------------------------------------------------------ |
| Rod Internal Pressure  | including Initial Cold Fuel Rod Plenum Volume, Maximum Fuel Rod Internal Pressure, Peak nodal burnup, Rod average burnup, Fuel rod void volume, Fission gas release, etc |
| Centerline Temperature | including Maximum Fuel Centerline Temperature, Axial node, Max Rad. Ave Fuel Enthalpy, Nodal burnup, Rod average burnup,etc |
| Strain Increment       | including Maximum Strain Increment, Axial node, Nodal burnup, Rod average burnup,etc |



## 2. Test Input

#### a) ANT-MOC

| Method                 | GID            | TID                    | Reference                                                    | Location                                                     |
| ---------------------- | -------------- | ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Custom  Tesing         |                | ANT-MOC-CT01           | Literature                                                   | test/input/ANT-MOC/CT/beavrs-3d.zip                          |
|                        |                | ANT-MOC-CT02           | Literature                                                   | test/input/ANT-MOC/CT/c5g7-3d-rodded-A.zip                   |
|                        |                | ANT-MOC-CT03           | Literature                                                   | test/input/ANT-MOC/CT/c5g7-3d-rodded-B.zip                   |
|                        |                | ANT-MOC-T04            | Literature                                                   | test/input/ANT-MOC/CT/c5g7-3d-unrodded.zip                   |
|                        |                | ANT-MOC-CT05           | Literature                                                   | test/input/ANT-MOC/CT/takeda-unrodded.zip                    |
|                        |                | ANT-MOC-CT06           | Literature                                                   | test/input/ANT-MOC/CT/takeda-rodded.zip                      |
| Differential Testing   |                | ANT-MOC-DT01           | ANT-MOC-CT02                                                 |                                                              |
|                        |                | ANT-MOC-DT02           | ANT-MOC-CT03                                                 |                                                              |
|                        |                | ANT-MOC-DT03           | ANT-MOC-CT04                                                 |                                                              |
|                        |                | ANT-MOC-DT04           | ANT-MOC-CT05                                                 |                                                              |
|                        |                | ANT-MOC-DT05           | ANT-MOC-CT06                                                 |                                                              |
|                        |                | ANT-MOC-DT06~DT11      | Derived from ANT-MOC-CT05 by changing the variable of "Num Polars" with "4, 6, ... , 14" |                                                              |
|                        |                | ANT-MOC-DT12~DT17      | Derived from ANT-MOC-CT06 by changing the variable of "Num Polars" with "4, 6, ... , 14" |                                                              |
|                        |                | ANT-MOC-DT'01          | OpenMOC                                                      | test/input/ANT-MOC/DT/c5g7-rodded-A.zip                      |
|                        |                | ANT-MOC-DT'02          | OpenMOC                                                      | test/input/ANT-MOC/DT/c5g7-rodded-B.zip                      |
|                        |                | ANT-MOC-DT'03          | OpenMOC                                                      | test/input/ANT-MOC/DT/c5g7-unrodded.zip                      |
|                        |                | ANT-MOC-DT'04          | OpenMOC                                                      | test/input/ANT-MOC/DT/takeda-unrodded.zip                    |
|                        |                | ANT-MOC-DT'05          | OpenMOC                                                      | test/input/ANT-MOC/CT/takeda-rodded.zip                      |
|                        |                | ANT-MOC-DT'06~DT'11    | Derived from ANT-MOC-DT'04 by changing the variable of "Num Polars" with "4, 6, ... , 14" |                                                              |
|                        |                | ANT-MOC-DT'12~DT'17    | Derived from ANT-MOC-DT'05 by changing the variable of "Num Polars" with "4, 6, ... , 14" |                                                              |
| Property-based Testing |                | ANT-MOC-PT01           | ANT-MOC-CT01                                                 |                                                              |
|                        |                | ANT-MOC-PT02           | ANT-MOC-CT02                                                 |                                                              |
|                        |                | ANT-MOC-PT03           | ANT-MOC-CT03                                                 |                                                              |
|                        |                | ANT-MOC-CT04           | ANT-MOC-CT04                                                 |                                                              |
|                        |                | ANT-MOC-PT05           | ANT-MOC-CT05                                                 |                                                              |
|                        |                | ANT-MOC-PT06           | ANT-MOC-CT06                                                 |                                                              |
|                        |                | ANT-MOC-PT07           | derived by expert experience                                 | test/input/ANT-MOC/PT/beavrs-single-assembly.zip             |
|                        |                | ANT-MOC-PT08           | derived by expert experience                                 | test/input/ANT-MOC/PT/c5g7-single-assembly.zip               |
| Metamorphic Testing    | ANT-MOC-MR2-G1 | ANT-MOC-MR2-1-T01      | ANT-MOC-CT02                                                 | /test/input/ANT-MOC/MT/MTGrou-deepth/c5g7-deepth1.zip        |
|                        |                | ANT-MOC-MR2-G1-T02     | derived from ANT-MOC-CT02, setting the deepth of assembly1 at "level2" | /test/input/ANT-MOC/MT/MTGrou-deepth/c5g7-deepth2.zip        |
|                        |                | ANT-MOC-MR2-G1-T03     | derived from ANT-MOC-CT02, setting the deepth of assembly1 at "level3" | /test/input/ANT-MOC/MT/MTGrou-deepth/c5g7-deepth3.zip        |
|                        | ANT-MOC-MR3-G1 | ANT-MOC-MR3-G1-T01~T08 | derived from ANT-MOC-CT02, changing the variable of "Num Polar " with "2, 4, 6, ..., 16" | test/input/ANT-MOC/MT/MTGroup-polar-c5g7-rodded-A/polar = ${i} (i=2, 4, 6, ..., 16) |
|                        | ANT-MOC-MR3-G2 | ANT-MOC-MR3-G2-T01~T08 | derived from ANT-MOC-CT03, changing the variable of "Num Polar " with "2, 4, 6, ..., 16" | test/input/ANT-MOC/MT/MTGroup-polar-c5g7-rodded-B/polar = ${i} (i=2, 4, 6, ..., 16) |
|                        | ANT-MOC-MR3-G3 | ANT-MOC-MR3-G3-T01~T08 | derived from ANT-MOC-CT04, changing the variable of "Num Polar " with "2, 4, 6, ..., 16" | test/input/ANT-MOC/MT/MTGroup-polar-c5g7-unrodded/polar = ${i} (i=2, 4, 6, ..., 16) |
|                        | ANT-MOC-MR3-G4 | ANT-MOC-MR3-G4-T01~T08 | derived from ANT-MOC-CT05, changing the variable of "Num Polar " with "2, 4, 6, ..., 40" | test/input/ANT-MOC/MT/MTGroup-polar-c5g7-unrodded/polar = ${i} (i=2, 4, 6, ..., 40) |
|                        | ANT-MOC-MR3-G5 | ANT-MOC-MR3-G5-T01~T08 | derived from ANT-MOC-CT05, setting the variable of "Num Modules" at "1,1,1",  changing the variable of "Num Polar " with "2, 4, 6, ..., 40" |                                                              |
|                        | ANT-MOC-MR3-G6 | ANT-MOC-MR3-G6-T01~T08 | derived from ANT-MOC-CT05, setting the variable of "Num Modules" at "5,5,1",  changing the variable of "Num Polar " with "2, 4, 6, ..., 40" |                                                              |

##### 

#### b) MISA-SCD

| Method                 | TID           | Reference                                 | Location                                          |
| ---------------------- | ------------- | ----------------------------------------- | ------------------------------------------------- |
| Custom Testing         | MISA-SCD-CT01 | electron irradiation                      | test/input/MISA-SCD/CT/test-electron.zip          |
|                        | MISA-SCD-CT02 | neutron irradiation                       | test/input/MISA-SCD/CT/test-neutron.zip           |
|                        | MISA-SCD-CT03 | electron irradiation using  adaptive grid | test/input/MISA-SCD/CT/test-electron-adaptive.zip |
|                        | MISA-SCD-CT04 | neutron irradiation using  adaptive grid  | test/input/MISA-SCD/CT/test-neutron-adaptive.zip  |
| Property-based Testing | MISA-SCD-PT01 | MISA-SCD-CT01                             |                                                   |
|                        | MISA-SCD-PT02 | MISA-SCD-T02                              |                                                   |
|                        | MISA-SCD-PT03 | MISA-SCD-CT03                             |                                                   |
|                        | MISA-SCD-T04  | MISA-SCD-CT04                             |                                                   |

#### c) MISA-MD

| Method                 | GID            | TID                    | Reference                                                    | Location                                                     |
| ---------------------- | -------------- | ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Differential Testing   |                | MISA-MD-T01            | Expert experience                                            | test/input/MISA-MD/DT/1kev-<135>/MISA-MD.toml                |
|                        |                | MISA-MD-T02~T07        | derived from MISA-MD-T01, changing the variable of "energy" with "5000, 10000, 15000, ..., 30000" | test/input/MISA-MD/DT/${i}kev-<135>/MISA-MD.toml, (i=5, 10, 15,..., 30) |
|                        |                | MISA-MD-T08            | derived from MISA-MD-T02, changing the variable of "direction" with [1,2,2] | test/input/MISA-MD/DT/5kev-<122>/MISA-MD>.toml               |
|                        |                | MISA-MD-T09            | derived from MISA-MD-T02, changing the variable of "direction" with [2,3,5] | test/input/MISA-MD/DT/5kev-<235>/MISA-MD.toml                |
|                        |                | MISA-MD-T10            | derived from MISA-MD-T02, changing the variable of "direction" with [2,4,5] | test/input/MISA-MD/DT/5kev-<245>/MISA-MD.toml,               |
|                        |                | MISA-MD-T11            | derived from MISA-MD-T02, changing the variable of "direction" with [3,4,5] | test/input/MISA-MD/DT/5kev-<345>/MISA-MD.toml                |
|                        |                | MISA-MD-DT01~DT11      | MISA-MD-T01~T11                                              |                                                              |
|                        |                | MISA-MD-DT'01          | Expert experience                                            | test/input/MISA-MD/DT/1kev-<135>/lammps.in                   |
|                        |                | MISA-MD-DT'02~DT'07    | derived from MISA-MD-DT'01 by changing the line of 3, 4, 5 of the input file | test/input/MISA-MD/DT/${i}kev-<135>/lammps.in, (i=5, 10, 15,..., 30) |
|                        |                | MISA-MD-DT'08          | derived from MISA-MD-DT'01 by changing the line of 3, 4, 5 of the input file | test/input/MISA-MD/DT/1kev-<122>/lammps.in                   |
|                        |                | MISA-MD-DT'09          | derived from MISA-MD-DT'01 by changing the line of 3, 4, 5 of the input file | test/input/MISA-MD/DT/1kev-<235>/lammps.in                   |
|                        |                | MISA-MD-DT'010         | derived from MISA-MD-DT'01 by changing the line of 3, 4, 5 of the input file | test/input/MISA-MD/DT/1kev-<245>/lammps.in                   |
|                        |                | MISA-MD-DT'011         | derived from MISA-MD-DT'01 by changing the line of 3, 4, 5 of the input file | test/input/MISA-MD/DT/1kev-<345>/lammps.in                   |
| Property-based Testing |                | MISA-MD-PT01           | MISA-MD-T01                                                  | test/input/MISA-MD/PT/5kev-<135>-80/MISA-MD.toml             |
|                        |                | MISA-MD-PT02           | MISA-MD-T02                                                  | test/input/MISA-MD/PT/5kev-<122>-80/MISA-MD.toml             |
|                        |                | MISA-MD-PT03           | Expert experience                                            | test/input/MISA-MD/PT/5kev-<135>-50/MISA-MD.toml             |
|                        |                | MISA-MD-PT04           | Expert experience                                            | test/input/MISA-MD/PT/5kev-<135>-80-Cu-Ni/MISA-MD.toml       |
|                        | MISA-MD-MR4-G1 | MISA-MD-MR4-G1-T01~T07 | MISA-MD-T01~T07                                              |                                                              |
|                        | MISA-MD-MR5-G1 | MISA-MD-MR5-G1-T01~T04 | derived from MISA-MD-T01, increasing the variable of "phasespace" for "[50,50,50], [60,60,60] ,... [80,80,80] |                                                              |
|                        | MISA-MD-MR6-G1 | MISA-MD-MR6-G1-T01     | derived from MISA-MD-T01, increasing the variable of "Ni"    | test/input/MISA-MD/MT/MTGroup-Ni/test0.toml                  |
|                        |                | MISA-MD-MR6-G1-T02     |                                                              | test/input/MISA-MD/MT/MTGroup-Ni/test1.toml                  |
|                        |                | MISA-MD-MR6-G1-T03     |                                                              | test/input/MISA-MD/MT/MTGroup-Ni/test2.toml                  |
|                        | MISA-MD-MR7-G1 | MISA-MD-MR6-G1-T01     | derived from MISA-MD-T01, increasing the variable of "Cu"    | test/input/MISA-MD/MT/MTGroup-Cu/test0.toml                  |
|                        |                | MISA-MD-MR6-G1-T01     |                                                              | test/input/MISA-MD/MT/MTGroup-Cu/test1.toml                  |
|                        |                | MISA-MD-MR6-G1-T01     |                                                              | test/input/MISA-MD/MT/MTGroup-Cu/test2.toml                  |
|                        |                | MISA-MD-MR8-G1         | MISA-MD-MR8-G1-T01~T07                                       | MISA-MD-T01~T07                                              |
|                        | MISA-MD-MR9-G1 | MISA-MD-MR9-G1-T01~T07 | MISA-MD-T01~T07                                              |                                                              |

#### d) MISA-ETD

| Method                     | GID              | TID                          | Reference                                                    | Location                                   |
| -------------------------- | ---------------- | ---------------------------- | ------------------------------------------------------------ | ------------------------------------------ |
| Custom Testing             |                  | MISA-ETD-CT01                | literature                                                   | test/input/MISA-ETD/CT/test0.in            |
| Differential Testing       |                  | MISA-ETD-DT01                | MISA-ETD-CT01                                                |                                            |
|                            |                  | MISA-ETD-DT02                | derived from MISA-ETD-CT01, changing the variable of totalTime from "100000" to "150000" | test/input/MISA-ETD/DT/totalTime=150000.in |
|                            |                  | MISA-ETD-DT03                | derived from MISA-ETD-CT01, changing the variable of totaltime from "150000" to "200000" | test/input/MISA-ETD/DT/totalTime=200000.in |
|                            |                  | MISA-ETD-DT'01               | Implementing another version of the program（matlab）        | Console input                              |
|                            |                  | MISA-ETD-DT'02               | derived from MISA-ETD-DT'01, changing the variable of totaltime from "100000" to "150000" |                                            |
|                            |                  | MISA-ETD-DT'03               | derived from MISA-ETD-DT'01, changing the variable of totaltime from "100000" to "200000" |                                            |
| Metamorphic Testing        | MISA-ETD-MR10-G1 | MISA-ETD-MR10-G1-T0001~T1000 | Derived from MISA-ETD-CT01, changing the variable of totalTime from "1000, 2000, 3000, ..., 1000000" |                                            |
| Richardson’s Extrapolation |                  | MISA-ETD-RE01                | MISA-ETD-T01                                                 |                                            |
|                            |                  | MISA-ETD-RE02                | derived from MISA-ETD-T01, replace the variable of timeStep with "timeStep / 2" | test/input/MISA-ETD/RE/dt=0.05.in          |
|                            |                  | MISA-ETD-RE03                | derived from MISA-ETD-RE02, replace the variable of timeStep with "timeStep / 2" | test/input/MISA-ETD/RE/dt=0.025            |
|                            |                  | MISA-ETD-RE04                | derived from MISA-ETD-RE03, replace the variable of timeStep with "timeStep / 2" | test/input/MISA-ETD/RE/dt=0.0125           |
|                            |                  | MISA-ETD-RE05                | derived from MISA-ETD-RE04, replace the variable of timeStep with "timeStep / 2" | test/input/MISA-ETD/RE/dt=0.00625          |
|                            |                  | MISA-ETD-RE06                | derived from MISA-ETD-RE05, replace the variable of timeStep with "timeStep / 2" | test/input/MISA-ETD/RE/dt=0.003125         |

##### 

#### e) ATHENA

| Method                     | TID         | Reference                                                    | Location                       |
| -------------------------- | ----------- | ------------------------------------------------------------ | ------------------------------ |
| Custom Testing             | ATHENA-T01  | expert experience                                            | test/input/ATHENA/CT/test0.inp |
| Differential Testing       | ATHENA-DT01 | ATHENA-T01                                                   |                                |
|                            | ATHENA-DT02 | expert experience                                            | test/input/ATHENA/DT/test1.inp |
|                            | ATHENA-DT03 | expert experience                                            | test/input/ATHENA/DT/test2.inp |
|                            | ATHENA-DT04 | expert experience                                            | test/input/ATHENA/DT/test3.inp |
| Property-baseed Testing    | ATHENA-PT01 | ATHENA-DT01                                                  |                                |
|                            | ATHENA-PT02 | ATHENA-DT02                                                  |                                |
|                            | ATHENA-PT03 | ATHENA-DT03                                                  |                                |
|                            | ATHENA-PT04 | ATHENA-DT04                                                  |                                |
| Richardson’s Extrapolation | ATHENA-RE01 | derived from ATHENA-RE01, changing the variable of "na" with "5" | test/input/ATHENA/RE/na=5.inp  |
|                            | ATHENA-RE02 | derived from ATHENA-RE01, replacing the variable of "na" with "na * 2" | test/input/ATHENA/RE/na=10.inp |
|                            | ATHENA-RE03 | derived from ATHENA-RE02, replacing the variable of "na" with "na * 2" | test/input/ATHENA/RE/na=20.inp |
|                            | ATHENA-RE04 | derived from ATHENA-Re03, replacing the variable of "na" with "na * 2" | test/input/ATHENA/RE/na=40.inp |
|                            | ATHENA-RE05 | derived from ATHENA-Re04, replacing the variable of "na" with "na * 2" | test/input/ATHENA/RE/na=80.inp |



### 3. Oracles

##### a) Expected results

|     TId      |   Description   | xpected |   Expected type   |
| :----------: | :-------------: | :-----: | :---------------: |
| ANT-MOC-CT01 |    beavrs-3d    | 0.99927 | Value + Deviation |
| ANT-MOC-CT02 |  C5g7-rodded-A  | 1.12806 | Value + Deviation |
| ANT-MOC-CT03 |  C5g7-rodded-B  | 1.07777 | Value + Deviation |
| ANT-MOC-CT04 |  C5g7-unrodded  | 1.14308 | Value + Deviation |
| ANT-MOC-CT05 | Takeda-unrodded | 0.97732 | Value + Deviation |
| ANT-MOC-CT06 |  Takeda-rodded  | 0.9623  | Value + Deviation |



| TId           | Description          | Expected            | Expected type           |
| ------------- | -------------------- | ------------------- | ----------------------- |
| MISA-SCD-CT01 | Electron irradiation | Evolutionary Trends | Picture from literature |
| MISA-SCD-CT02 | Neutron irradiation  | Evolutionary Trends | Picture from literature |
| MISA-SCD-CT03 | Electron irradiation | Evolutionary Trends | Picture from literature |
| MISA-SCD-CT04 | Neutron irradiation  | Evolutionary Trends | Picture from literature |



![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/Electron-irradiation-reference.png)

Time (bottom axis) and dose (top axis) evolution of Cu precipitation kinetics in a Fe-1.34at.%Cu at 290 ◦C under electron irradiation . (a) Evolution of total Cu cluster number density. (b) Evolution of average Cu cluster radius.



![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/Neutron-irradiation-reference.png)

Time (bottom axis) and dose (top axis) evolution of Cu precipitation kinetics in a Fe-0.3at.%Cu at 300 ◦C under neutron irradiation . (a) Evolution of total Cu cluster number density. (b) Evolution of average Cu cluster radius.

|    Test Id    | Description | Expected | Expected type           |
| :-----------: | :---------: | :------: | ----------------------- |
| MISA-ETD-CT01 |    test     |  Matrix  | Picture from literature |

**Reference result**：

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/rt-reference.png)



##### b) Propertis

| Program  | PID  | Description                                                  |        Reason         |
| -------- | ---- | ------------------------------------------------------------ | :-------------------: |
| ANT-MOC  | P1   | The ID of any characteristic line must be unique             |    Implementation     |
|          | P2   | The ID of any characteristic line must be a positive integer |    Implementation     |
|          | P3   | The length of any characteristic line must be a positive integer |    Implementation     |
|          | P4   | The ID of FSR must be unique                                 |    Implementation     |
|          | P5   | The flux distribution must be geometrically symmetric        | Physics & Computation |
| MISA-MD  | P6   | The ID of any molecule must be unique                        |    Implementation     |
|          | P7   | The position and velocity of a molecule should not be NAN    |    Implementation     |
|          | P8   | The position of a molecule must be within the simulation space |    Implementation     |
|          | P9   | The action and the reaction force between any two molecules must be identical |        Physics        |
|          | P10  | The kinetic energy of the entire system must be conserved (equal to the input PKA energy) |        Physics        |
|          | P11  | The number of molecules should not change                    |        Physics        |
|          | P12  | Within two consecutive time steps, the change of the force exerted on a molecule should not be greater than ε, where ε = 20 |   Domain knowledge    |
| MISA-SCD | P13  | ¬(Cu < 0∧V < 0∧SIA_m < 0∧SIA_im < 0)                         |      Computation      |
|          | P14  | ¬(SIA_m > 0∧SIA_im > 0)                                      |      Computation      |
|          | P15  | ¬((SIA_m > 0 v SIA_im > 0) ∧ V > 0 )                         |      Computation      |
| ATHENA   | P16  | The pressure of the system should not change within the inner loop |   Numeric algorithm   |
|          | P17  | The result of the inner loop must converge                   |   Numeric algorithm   |

##### c) MRs

| Program | MRID | Description                                                  |   Reason    |
| ------- | ---- | ------------------------------------------------------------ | :---------: |
| ANT-MOC | MR1  | For any two test case i and i′, if i is identical to i′ except that i is performed on a single physical core and i′ is performed on multiple physical cores, then keff(p(i)) = keff(p(i′)) |  Execution  |
|         | MR2  | For a source test case i, if the follow-up test case i′ is derived from i by increasing the depth of a control pin, then keff(p(i))>keff(p(i′)) |   Physics   |
|         | MR3  | For a source test case i0, if follow-up test cases i1, i2,... are derived by gradually increasing the amount of polar angles, i.e., by densifying the grids, then keff(p(ik)) − keff(p(ik+1))<2×10, when k→+∞ | Computation |
| MISA-MD | MR4  | For a source test case i, if the follow-up test case i′ is derived from i by increasing the initial PKA, then T(p(i))<T(p(i′)), where T extracts the system temperature from the program output |   Physics   |
|         | MR5  | For a source test case i, if the follow-up test case i′ is derived from i by increasing the simulation space, then T(p(i))>T(p(i′)) |   Physics   |
|         | MR6  | For a source test case i, if the follow-up test case i′ is derived from i by increasing Ni content, then T(p(i))≠T(p(i′)) |   Physics   |
|         | MR7  | For a source test case i, if the follow-up test case i′ is derived from i by increasing Cu content, then T(p(i))≠T(p(i′)) |   Physics   |
|         | MR8  | For a source test case i, if the follow-up test case i′ is derived from i by increasing the initial PKA, then Fs(p(i))<Fs(p(i′)), where Fs extracts the amount of Frankel defects from the program output. |   Physics   |
|         | MR9  | For a source test case i, if the follow-up test case i′ is derived from i by increasing the initial PKA, then Fp(p(i))<Fp(p(i′)), where Fp extracts the peak value of Frankel defects from the program output |   Physics   |
| MISA-RT | MR10 | If the simulation times of the source and the follow-up test cases i and i′ are larger than a certain T0, p(i) = p(i′) |   Physics   |

##### d) Richardson

| Program  | Expected  |
| -------- | --------- |
| MISA-ETD | $$2^{4}$$ |
| ATHENA   | Unchanged |



### 4. Bugs

#### a) ANT-MOC

**B1: When deserializing from an input file, “-” is converted into “0”. Hence, “10-1” and “1-01” will both become “1001”**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b1.png)

**Reason**: Substitute '-' with '0' may has a bug.

**B2: A negative number may be generated for ID of characteristic line**

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b2.png)

**Reason**: There may be no tracks under a specified azimuthal angle for a certain process, which would lead to a `0` when `getMyNum2DTracks()` was invoked. If it happens, `xy` evaluates to `-1`, cause a negative number.



**B3: Around the corner of the simulation space, the length of a characteristic line may be 0**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b3-1.png)

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b3-2.png)

Reason:  tracks shoot out the surface YMAX will always re-enter the geometry at corners, which probably produces invalid tracks or zero-lengh tracks or something



**B4: The generation of FSR ID is not unique**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b4.png)

**Reason**: Because of the cyclic track decomposition algorithm, FSRs are supposed to be synchronized across processes. However, this means that we have to break the thread-parallelized FSR generation algorithm to ensure that FSRs are numbered in the same order across all processes..



**B5:  Related Code: Due to the incorrect offset computation, the length of a characteristic line may be 0**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b5.png)

**Reason**: mismatched links on YMIN and YMAX surfaces.



**B6: Due to mismatch of the endpoints of a characteristic line, the length of the line may be 0**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b6.png)

**Reason**: zero-length caused by wrongly nudged endpoints of tracks.



**B8: The ICPC compiler of Tianhe-2 supercomputer is incompatible with our program.**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b8.png)

**Reason**: According to the manual, `simd` can be replaced by `omp simd` construct. 



**B9: Error in load balance algorithm**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/antmoc-b9.png)

**Reason**: Load balancing for angular decomposition has a confirm issue that the fluxes may be wrongly computed when a process has zero angle. This is not fixed yet and should be avoided by set the number of azimuthal angles properly.



#### b) MISA-MD

**B1：Error in communication algorithm causes the collision of molecule IDs**

A part of error output  showing below :

| ID    | Locate.x  | ...  | ID    | Locate.x |
| ----- | --------- | ---- | ----- | -------- |
| 62501 | 0.0151414 | ...  | 62501 | 71.3981  |
| 31251 | 0.0151414 | ...  | 31251 | 71.3981  |
| 93751 | 0.0151414 |      | 93751 | 71.3981  |

**Related code** :

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b1.png)

**Reason**: Error in Computation-Parallelization.



**B3: Error in indexing computation causes the loss of molecules in communication**

**Related Code**:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b3.png)

**Reason**: Error in indexing computation causes the loss of molecules in communication, inter atoms are filtered in *InterAtomList::unpackExInterRecv()*.



**B4: Incorrect communication strategy**

**Related code**:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b4.png)

**Reason**: Incorrect communication strategy in *InterBorderPacker::sendLength()*.



**B5: Incorrect communication algorithm in ghost regions**

**Related Code**:

Adding new GhostAtom operation.

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b5.png)

**Reason**:  Incorrect communication algorithm in ghost regions. 

To fix this bug, we should remove ghost inter atoms before each simulation time step and set atom's property 0 when receiving a new inter atom.



**B6: Error in indexing computation when updating molecule velocity** 

**Related Code**:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b6.png)

**B7: Error in computing molecule distance causes the incorrect indexing computation**

Related code:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b7.png)



**B8：Incorrect coding in speed calculation during cascade collision**

**Related Code**:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b8.png)

**Reason**：Incorrect coding in speed calculation during cascade collision.



**B9：Incorrect string constant, where “Ni” was written as “Nii”**

**Related Code**:

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/md-b9.png)

**Reason**：Incorrect string constant, where “Ni” was written as “Nii”.



#### c) MISA-SCD:

**B1：Duplicate insertion of the same data**

**Related Code:** 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/scd-b1.png)



**B2: Incorrect merge of two defect species**

**Related Code**: 

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/scd-b2.png)

**Reason**: SIA+Cu should not combine.



#### d) MISA-ETD

**B1: Cancellation**

**Related Code:**

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/etd-b1.png)

**Reason:** line 122 may has large cancellation error.

![image](https://github.com/ustbsoftlang/issta2020-hpnsp/raw/master/TestCaseInfo.assets/etd-b1-2.png)

