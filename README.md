# COMBREAU JAD - ANANAX CANONICAL INTAKE
## Markdown documentation file

## Ananax2d_Canonical_Intake Workflow over Isight

### Workflow type & role

This Workflow (Canonical Intake) has the final goal, like the other Workflows, the calculation of the acoustic attenuation matrix.
It intervenes in the canonical case of air intake, that is to say that unlike the analytical case, we do not have to generate a mesh. The mesh is assumed to be uniform and Actran automatically generates it for us.

The air inlet duct is therefore assumed to be more or less uniform. We do not calculate a flow, since it is supposed to be uniform. There is no weighted average to be used for computation in various nodes of mesh.

__This Workflow therefore presents seven boxes :__

![Exemple workflow](https://user-images.githubusercontent.com/45098441/72247568-6e2e2900-35f5-11ea-850a-23eac41aa2e9.jpeg)

- __Initialization :__ *allows among other things the creation of initialization variables, environment variables or even the test of the structure and the reading of the input file (XML)*
- __Acoustic Meshes :__ *allows the generation and the creation of an uniform mesh (canonical case)*
- __Acoustic Models :__ *input file, thermodynamic file etc.*
- __Cutoff Computations :__ *source representation (modal base)*
- __Scout Computations :__ *blank calculation to determine the resources required (number of HPC nodes, amount of memory, etc.)*
- __Acoustic Computations :__ *Actran or Madhiwax solver for the noise acoustic calculation in the air intake (to obtain frequencies)*
- __Postprocessing :__ *allows the generation of the attenuation matrix (PIFF & PID calculus)*

Here is the Workflow structure by specification :

| | CANONICAL | ANALYTICAL |
|-----------|:-----------:|:-----------:|
|INTAKE | X | -- |
|BYPASS | -- | -- |

Here is the exact structure of the workflow through its different boxes or components :


![Initialization components](https://user-images.githubusercontent.com/45098441/72422332-88e1d880-3782-11ea-9f99-39a2ec1a7396.jpeg)



## Check & Read XML

### Explanation of what the box does

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values ​​for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

### Which files to import ?

To execute the script "Check & Read XML" correctly, we need to import other Python libraries.
The table below lists all the imports to be made :

| Import name | Import functions | Import location |
| ------ | :------: | ------ |
| XMLAnanax2dCanonicalIntake | FUNCTIONS NAMES | `/src_wf/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | FUNCTIONS NAMES | `/src_wf/python/workflows/common` |
| CommonFunctions | FUNCTIONS NAMES | `/src_wf/python/workflows/common` |
| PiffPostprocessing | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/workflows/ductnoise/common/postprocessing` |
| PiffPostprocessingAnanax2dCanonicalIntake | FUNCTIONS NAMES | `/src_wf/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

| Variable Name | Variable description | Value type | Input Value | Output Value |
| ------ | :------------: | :------: | :------: |  :------: |
| pathOfPythonSrcFolder | DESCRIPTION | STRING | INPUT | OUTPUT |
| pathOfXML | DESCRIPTION | TYPE | INPUT | OUTPUT |
| pathOfLogsFolder | DESCRIPTION | STRING | - | OUTPUT |
| myLogger | DESCRIPTION | TYPE | INPUT | OUTPUT |
| xsd | DESCRIPTION | STRING | INPUT | OUTPUT |
| linearFrequencies | DESCRIPTION | ARRAY DOUBLE | 0 | OUTPUT |
| numberOfConfigurations | DESCRIPTION | INT | 0 | OUTPUT |
| namesOfConfigurations | DESCRIPTION | ARRAY STRING | 0 | OUTPUT |
| pathsOfUserFieldmeshes | DESCRIPTION | ARRAY STRING | 0 | OUTPUT |
| nbTreatments | DESCRIPTION | INT | 0 | OUTPUT |
| maxNodeMemory | DESCRIPTION | INT | 12 | OUTPUT |
| numberOfCoresByNode | DESCRIPTION | INT | 8 | OUTPUT |
| maxNumberOfProcesses | DESCRIPTION | INT | 0 | OUTPUT |
| memorySecurityCriteria | DESCRIPTION | REAL | 0.0 | OUTPUT |
| namesOfPostprocessingProcesses | DESCRIPTION | ARRAY STRING | 0 | OUTPUT |
| N1k | DESCRIPTION | TYPE | INPUT | OUTPUT |
| areAttenuationMatrices | DESCRIPTION | BOOL | INPUT | OUTPUT |
| piff | DESCRIPTION | TYPE | INPUT | OUTPUT |


