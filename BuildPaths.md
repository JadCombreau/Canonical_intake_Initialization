## Build Paths
### Script Language

All the __Build Paths__ box is written in Python.
### What the box does ?

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

__Check & Read XML__ box is preceded by the __Create Folders__ box, which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Get Mesh & Models Frequencies__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just linear frequencied to which we applied a step)

![Initialization components](https://user-images.githubusercontent.com/45098441/72734164-7eb44580-3b99-11ea-8313-26fdce7081a8.jpeg)
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
| nameOfTools | Input XML which contain all data | FILE | X |- |
| nameOfNacelle | Python source folder wich contain all librairies | STRING | X |- |
| nameOfSpinner | Job folder to copy all results | STRING | X | - |
| nameOfInputXml | Name of result logs folder - Usually LOGS | STRING | X | - |
| nameOfMonitoringStatus | Verbosity schema value - Actually fine | STRING | X | - |
| formatOfFrequencyStr | Name of result component folder - Usually checkSchema | STRING | X | - |
| formatOfConfigurationIdStr | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfActranMemo | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| nameOfConstraints | DESCRIPTION | REAL | X | - |
| formatOfSizeMesh | Input XML which contain all data | FILE | X |- |
| nameOfGeomAcousData | Python source folder wich contain all librairies | STRING | X |- |
| formatOfAcousticMesh | Job folder to copy all results | STRING | X | - |
| formatOfFieldmesh | Name of result logs folder - Usually LOGS | STRING | X | - |
| formatOfFieldmeshPtl | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfMicrophones | Name of result component folder - Usually checkSchema | STRING | X | - |
| formatOfAcousticModel | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfSessionForAcousticAnalysis | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| nameOfEnvFile | DESCRIPTION | REAL | X | - |
| nameOfCutoffModes | Input XML which contain all data | FILE | X |- |
| formatOfScoutMemo | Python source folder wich contain all librairies | STRING | X |- |
| formatOfScoutModel | Job folder to copy all results | STRING | X | - |
| formatOfScoutResult | Name of result logs folder - Usually LOGS | STRING | X | - |
| nameOfActranSequentialLog | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfActranParallelLog | Name of result component folder - Usually checkSchema | STRING | X | - |
| formatOfComputationResultActran | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfActranResultPtl | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| formatOfcomputationResultPtl | DESCRIPTION | REAL | X | - |
| formatOfComputationResult | Input XML which contain all data | FILE | X |- |
| formatOfComputationMemo | Python source folder wich contain all librairies | STRING | X |- |
| formatOfAttenuationsMatrixl | Job folder to copy all results | STRING | X | - |
| formatOfLinearPiffResult | Name of result logs folder - Usually LOGS | STRING | X | - |
| nameOfLinearPiffXML | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfInputs | Name of result component folder - Usually checkSchema | STRING | X | - |
| nameOfInfo | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfScripts | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| formatOfFrequencyFolder | DESCRIPTION | REAL | X | - |
| formatOfConfigurationFolder | Input XML which contain all data | FILE | X |- |
| nameOfFlowMeshFolder | Python source folder wich contain all librairies | STRING | X |- |
| nameOfFlowFolder | Job folder to copy all results | STRING | X | - |
| nameOfAcousticMeshesFolder | Name of result logs folder - Usually LOGS | STRING | X | - |
| nameOfMicrophonesFolder | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfInterpolatedMeshesFolder | Name of result component folder - Usually checkSchema | STRING | X | - |
| nameOfLinearAcousticModelsFolder | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfLinearCutoffFolder | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| nameOfScoutComputationsFolder | Python source folder wich contain all librairies | STRING | X |- |
| nameOfLinearComputationsFolder | Job folder to copy all results | STRING | X | - |
| formatOfPostprocessingProcessFolder | Name of result logs folder - Usually LOGS | STRING | X | - |
| formatOfRelativePostprocessingFolder | Verbosity schema value - Actually fine | STRING | X | - |
| nameOfAbsolutePostprocessingFolder | Name of result component folder - Usually checkSchema | STRING | X | - |
| pathOfJobFolder | Root folder - Usually /x86_64 | STRING | X | - |
| pathOfResourcesFolder | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| meshFrequencies | Python source folder wich contain all librairies | STRING | X |- |
| pathOfUserFieldmeshes | Job folder to copy all results | STRING | X | - |
| areBaseline | Name of result logs folder - Usually LOGS | STRING | X | - |
| baselineConfigurationIds | Verbosity schema value - Actually fine | STRING | X | - |
| namesOfPostprocessingProcesses | Name of result component folder - Usually checkSchema | STRING | X | - |
| 0 | Root folder - Usually /x86_64 | STRING | X | - |
| 1 | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| numberOfConfigurations | Root folder - Usually /x86_64 | STRING | X | - |
| modelFrequencies | Name of result meta component folder - Usually 00_Initialization | STRING | X | - |
| pathOfNumacousFolder | Root folder - Usually /x86_64 | STRING | X | - |
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

