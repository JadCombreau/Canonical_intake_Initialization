# ANANAX CANONICAL INTAKE
## Markdown documentation file
## Ananax2d_Canonical_Intake Workflow over Isight

| | CANONICAL | ANALYTICAL |
|-----------|:-----------:|:-----------:|
|INTAKE | X | -- |
|BYPASS | -- | -- |

### Workflow type & role

This Workflow (__Canonical Intake__) has the final goal (*like the other Workflows*) the acoustic attenuation matrix calculus.
This Workflow is for canonical case of air intake, that is to say (unlike the analytical case) we do not have to generate any mesh. 

The mesh is assumed to be uniform and Actran automatically generates it for us. Sounds simple right ?

The air inlet duct is therefore assumed to be more or less uniform. We do not calculate any flow. There is no weighted average to be used for computation in various nodes of mesh.

__This Workflow therefore presents seven boxes :__

![Canonical Workflow](https://user-images.githubusercontent.com/45098441/72733825-eddd6a00-3b98-11ea-9b77-2d24f6790d91.jpeg)
----------------------------


- __Initialization :__ *allows among other things the creation of initialization variables, environment variables or even structure test and the input XML file reading.*
- __Acoustic Meshes :__ *allows the generation and the creation of an uniform mesh (canonical case)*
- __Acoustic Models :__ *input file, thermodynamic file (etc.)*
- __Cutoff Computations :__ *source representation (modal base)*
- __Scout Computations :__ *blank calculation to determine the resources required (number of HPC nodes, amount of memory, etc.)*
- __Acoustic Computations :__ *Actran or Madhiwax solver for the noise acoustic calculation in the air intake (to obtain frequencies)*
- __Postprocessing :__ *allows the generation of the attenuation matrix (PIFF & PID calculus)*

### Initialization details :

#### The left side :

![Workflowleft](https://user-images.githubusercontent.com/45098441/72735505-3c403800-3b9c-11ea-9b80-446dedf0615e.jpeg)

#### And the right side :

![Workflowright](https://user-images.githubusercontent.com/45098441/72735511-3f3b2880-3b9c-11ea-9771-076188e4fe7a.jpeg)
