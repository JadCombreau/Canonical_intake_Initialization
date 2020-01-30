## Set ANANAX Environment and Resources PATH
### Script Language

__Set ANANAX Environment and Resources PATH__ box is written in Python and Shell UNIX language.
### What the box does ?

These scripts allow you to source the variable environment necessary for the execution of the various workflow scripts (*cdng_ananax_home.tmp*)

The Python script therefore allows you to create the different paths to source. Here we indicate the "jar" file which contains the libraries necessary for the execution of the Java scripts of our Workflow.

__Set ANANAX Environment and Resources PATH__ box is preceded by the __Create Folders__ box, which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Get Mesh & Models Frequencies__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just linear frequencied to which we applied a step)

![Initialization components](https://user-images.githubusercontent.com/45098441/72733839-f46be180-3b98-11ea-9394-2d7339747a44.jpeg)

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
| PiffPostprocessingAnanax2dCanonicalIntake | `/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

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
| MachToleranceDichotomy | DESCRIPTION | REAL | X | - |


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
| machAtFan | DESCRIPTION | REAL | - | X |
| velocityAtFan | DESCRIPTION | REAL | - | X |
| staticCelerityAtFan | DESCRIPTION | REAL | - | X |
| staticFluidDensityAtFan | DESCRIPTION | REAL | - | X |
| Cp | DESCRIPTION | REAL | - | X |
| Cv | DESCRIPTION | REAL | - | X |



__Unmapped outputs variables (which are not sent to the following boxes) :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

