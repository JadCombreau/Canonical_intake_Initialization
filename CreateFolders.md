## Create Folders
### Script Language

All the __Create Folders__ box is written in Shell UNIX language.
### What the box does ?

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

__Check & Read XML__ box is preceded by the __Create Folders__ box, which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Get Mesh & Models Frequencies__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just linear frequencied to which we applied a step)

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
| PiffPostprocessingAnanax2dCanonicalIntake | `/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfAcousticMeshesFolder | DESCRIPTION | STRING | X |- |
| nameOfInputsFolder | DESCRIPTION | STRING | X |- |
| nameOfLinearAcousticModelsFolder | DESCRIPTION | STRING | X | - |
| nameOfLogsFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearComputationsFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearCutoffFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearPostprocessingFolder | DESCRIPTION | STRING | X | - |
| nameOfMicrophonesFolder | DESCRIPTION | STRING | X | - |
| nameOfScoutComputationsFolder | DESCRIPTION | STRING | X | - |
| nameOfScripts | DESCRIPTION | STRING | X | - |


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

