# COMBREAU JAD - ANANAX CANONICAL INTAKE
## Markdown documentation file

## Ananax2d_Canonical_Intake Workflow over Isight

### Workflow type & role

This Workflow (Canonical Intake) has the final goal, like the other Workflows, the calculation of the acoustic attenuation matrix.
It intervenes in the canonical case of air intake, that is to say that unlike the analytical case, we do not have to generate a mesh. The mesh is assumed to be uniform and Actran automatically generates it for us.

The air inlet duct is therefore assumed to be more or less uniform. We do not calculate a flow, since it is supposed to be uniform. There is no weighted average to be used for computation in various nodes of mesh.

__This Workflow therefore presents seven boxes :__

----------------------------

![Exemple workflow](https://user-images.githubusercontent.com/45098441/72423329-5a64fd00-3784-11ea-81c9-93b43f4a6cd7.jpeg)

----------------------------

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

## Check & Read XML

### What the box does ?

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

__Check & Read XML__ box is preceded by the __Create Folders__ box, which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Get Mesh & Models Frequencies__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just linear frequencied to which we applied a step)

----------------------------

![Initialization components](https://user-images.githubusercontent.com/45098441/72422704-36ed8280-3783-11ea-9d05-2fd0d949db32.jpeg)

----------------------------

### Which files to import ?

To execute the script __Check & Read XML__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

| Import name | Import location |
| ------ | ------ |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |
| CommonFunctions | `/python/workflows/common` |
| PiffPostprocessing | `/python/workflows/ductnoise/common/postprocessing` |
| PiffPostprocessingAnanax2dCanonicalIntake | /python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |
| pathOfJobFolder | Job folder to copy all results | STRING | X | - |
| nameOfLogsFolder | Name of result logs folder - Usually LOGS | STRING | X | - |
| verbosity | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfComponent | Name of result component folder - Usually checkSchema | STRING | X | - |
| pathOfApplicationRootFolder | Root folder - Usually /x86_64 | STRING | X | - |
| namesOfMetaComponent | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |

__Mapped outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| linearFrequencies | All linear frequencies in the XML file | ARRAY DOUBLE | - | X |
| numberOfConfigurations | Configuration number in the XML file | INT | - | X |
| pathOfLogsFolder | Logs folder result repository | STRING | - | X |
| pathsOfUserFieldmeshes | DESCRIPTION | ARRAY STRING | - | X |
| maxNodeMemory | Max node memory available | INT | - | X |
| numberOfCoresByNode | Number of core in each node memory | INT | - | X |
| maxNumberOfProcesses | Maximum processes number | INT | - | X |
| memorySecurityCriteria | Security criteria for memory | REAL | - | X |
| namesOfPostprocessingProcesses | DESCRIPTION | ARRAY STRING | - | X |
| areBaseline | DESCRIPTION | BOOL | - | X |
| baselineConfigurationsIds | DESCRIPTION | INT | - | X |

__Unmapped outputs variables (which are not sent to the following boxes) :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

### Which files do we receive from previous boxes ? 

### And which files do we send to following boxes ?


