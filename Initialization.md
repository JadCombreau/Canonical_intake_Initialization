# COMBREAU JAD - ANANAX CANONICAL INTAKE
## Markdown documentation file
## Ananax2d_Canonical_Intake Workflow over Isight

| | CANONICAL | ANALYTICAL |
|-----------|:-----------:|:-----------:|
|INTAKE | X | -- |
|BYPASS | -- | -- |

### Workflow type & role

This Workflow (Canonical Intake) has the final goal, like the other Workflows, the calculation of the acoustic attenuation matrix.
It intervenes in the canonical case of air intake, that is to say that unlike the analytical case, we do not have to generate a mesh. The mesh is assumed to be uniform and Actran automatically generates it for us.

The air inlet duct is therefore assumed to be more or less uniform. We do not calculate a flow, since it is supposed to be uniform. There is no weighted average to be used for computation in various nodes of mesh.

__This Workflow therefore presents seven boxes :__

![Exemple workflow](https://user-images.githubusercontent.com/45098441/72423329-5a64fd00-3784-11ea-81c9-93b43f4a6cd7.jpeg)
----------------------------


- __Initialization :__ *allows among other things the creation of initialization variables, environment variables or even the test of the structure and the reading of the input file (XML)*
- __Acoustic Meshes :__ *allows the generation and the creation of an uniform mesh (canonical case)*
- __Acoustic Models :__ *input file, thermodynamic file etc.*
- __Cutoff Computations :__ *source representation (modal base)*
- __Scout Computations :__ *blank calculation to determine the resources required (number of HPC nodes, amount of memory, etc.)*
- __Acoustic Computations :__ *Actran or Madhiwax solver for the noise acoustic calculation in the air intake (to obtain frequencies)*
- __Postprocessing :__ *allows the generation of the attenuation matrix (PIFF & PID calculus)*