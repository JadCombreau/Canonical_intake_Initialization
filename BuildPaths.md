## Build Paths
### Script Language

All the __Build Paths__ box is written in Python.
### What the box does ?

This Python script allows the creation of different file paths necessary for all the Workflow.

Indeed according to the preceding boxes which allowed us to know the number of frequencies and configurations for example ... We must now create a folder by configuration and one by frequency. The different paths are created here but the folders themselves will be created later.

The script is divided into different sub-areas for easier understanding :

- The "folders" part
- The "common" part
- The "acousmesh" part
- The "microphones" part
- The "linear models" part
-- The "linear frequency" subpart
- The "linear cutoff" part
- The "scouts" part
- The "linear computations" part
- The "postprocessing" part

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
| nameOfTools | Usually "tools.list" | STRING | X |- |
| nameOfNacelle | Usually "nacelle.stp" | STRING | X |- |
| nameOfSpinner | Usually "spinner.stp" | STRING | X | - |
| nameOfInputXml | Name of result input XML - Usually "input.xml" | STRING | X | - |
| nameOfMonitoringStatus | Usually "status.log" | STRING | X | - |
| formatOfFrequencyStr | Usually "%08.2fHz" | STRING | X | - |
| formatOfConfigurationIdStr | Usually "%03d" | STRING | X | - |
| nameOfActranMemo | Usually "bsub.actran.memo" | STRING | X | - |
| nameOfConstraints | Usually "constraints.txt" | STRING | X | - |
| formatOfSizeMesh | Usually "size_%s.unv" | STRING | X |- |
| nameOfGeomAcousData | Usually "geom_acous.data" | STRING | X |- |
| formatOfAcousticMesh | Usually "mesh_%s.unv" | STRING | X | - |
| formatOfFieldmesh | Usually "fieldmesh_%s.unv" | STRING | X | - |
| formatOfFieldmeshPtl | Usually "fieldmesh_%s.ptl" | STRING | X | - |
| nameOfMicrophones | Usually "microphones.txt" | STRING | X | - |
| formatOfAcousticModel | Usually "conf%s_freq%d.edat" | STRING | X | - |
| nameOfSessionForAcousticAnalysis | Usually "tutu.py" | STRING | X | - |
| nameOfEnvFile | 0.0 | STRING | X | - |
| nameOfCutoffModes | - | STRING | X |- |
| formatOfScoutMemo | - | STRING | X |- |
| formatOfScoutModel | - | STRING | X | - |
| formatOfScoutResult | - | STRING | X | - |
| nameOfActranSequentialLog | - | STRING | X | - |
| nameOfActranParallelLog | - | STRING | X | - |
| formatOfComputationResultActran | Root folder - Usually /x86_64 | STRING | X | - |
| nameOfActranResultPtl | - | STRING | X | - |
| formatOfComputationResultPtl | - | STRING | X | - |
| formatOfComputationResult | - | STRING | X |- |
| formatOfComputationMemo | - | STRING | X |- |
| formatOfAttenuationsMatrixl | - | STRING | X | - |
| formatOfLinearPiffResult | - | STRING | X | - |
| nameOfLinearPiffXML | - | STRING | X | - |
| nameOfInputs | Usually "INPUTS" | STRING | X | - |
| nameOfInfo | - | STRING | X | - |
| nameOfScripts | Usually "SCRIPTS" | STRING | X | - |
| formatOfFrequencyFolder | Usually "FREQ_%s" | STRING | X | - |
| formatOfConfigurationFolder | Usually "CONF_%s" | STRING | X |- |
| nameOfFlowMeshFolder | Usually "FLOWMESH" | STRING | X |- |
| nameOfFlowFolder | Usually "FLOW" | STRING | X | - |
| nameOfAcousticMeshesFolder | Usually "ACOUSMESH" | STRING | X | - |
| nameOfMicrophonesFolder | Usually "MICROPHONES" | STRING | X | - |
| nameOfInterpolatedMeshesFolder | Usually "INTERPOLATED_MESH" | STRING | X | - |
| nameOfLinearAcousticModelsFolder | Usually "LINEAR/MODELS | STRING | X | - |
| nameOfLinearCutoffFolder | Usually "LINEAR/CUTOFF" | STRING | X | - |
| nameOfScoutComputationsFolder | Usually "SCOUT" | STRING | X |- |
| nameOfLinearComputationsFolder | Usually "LINEAR/COMPUTATIONS" | STRING | X | - |
| formatOfPostprocessingProcessFolder | Usually "MODALCONTENT_%s" | STRING | X | - |
| formatOfRelativePostprocessingFolder | Usually "RELATIVE_CONF%s" | STRING | X | - |
| nameOfLinearPostprocessingFolder | Usually "LINEAR/POST" | STRING | X | - |
| nameOfAbsolutePostprocessingFolder | - | STRING | X | - |
| pathOfJobFolder | Usually "/x86_64/samples/canonicalIntake" | STRING | X | - |
| pathOfResourcesFolder | Usually "/opt/soft/cdtng/tools/ananax/dev/resources_wf" | STRING | X | - |
| meshFrequencies | - | ARRAY REAL | X |- |
| pathOfUserFieldmeshes | - | ARRAY STRING | X | - |
| areBaseline | - | ARRAY BOOL | X | - |
| baselineConfigurationIds | - | ARRAY INT | X | - |
| namesOfPostprocessingProcesses | - | ARRAY STRING | X | - |
| linearFrequencies | - | ARRAY REAL | X | - |
| numberOfConfigurations | - | INT | X | - |
| modelFrequencies | - | ARRAY REAL | X | - |
| pathOfNumacousFolder | - | STRING | X | - |

__Mapped outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| pathOfTools | - | STRING | - | X |
| pathOfScriptsRootFolder | - | STRING | - | X |
| pathOfNacelle | - | STRING | - | X |
| pathsOfSpinner | - | STRING | - | X |
| pathOfInputXml | - | STRING | - | X |
| pathOfMonitoringStatus | - | STRING | - | X |
| pathOfConstraints | - | STRING | - | X |
| pathsOfSizeMesh | - | ARRAY STRING | - | X |
| pathsOfAcousticMeshes | - | ARRAY STRING | - | X |
| pathOfAcousGeomData | - | STRING | - | X |
| pathOfMicrophones | - | STRING | - | X |
| pathsOfFieldmeshes | - | ARRAY STRING | - | X |
| pathsOfFieldmeshesPtl | - | ARRAY STRING | - | X |
| pathOfActranAcousticSession | - | STRING | - | X |
| pathsOfLinearModels_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsEnv_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsMemo_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfNumacousLinearModels_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearCutoffMemo | - | ARRAY STRING | - | X |
| pathsOfCutoffResults | - | ARRAY STRING | - | X |
| pathsOfScoutMemo | - | ARRAY STRING | - | X |
| pathsOfScoutResults | - | ARRAY STRING | - | X |
| pathsOfScoutModels | - | ARRAY STRING | - | X |
| pathsOfScoutMemosActran | - | ARRAY STRING | - | X |
| pathsOfScoutResultsActran | - | ARRAY STRING | - | X |
| pathsOfScoutLogs | - | ARRAY STRING | - | X |
| pathsOfLinearLogs_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearMemos_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearMemosActran_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearResults_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsActran_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtl_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtlActran_configuration_linearFrequency | - | ARRAY STRING 2D | - | X |
| pathsOfAttenuationsMatrices_process_configurationId | - | ARRAY STRING 2D | - | X |
| pathsOfPiffResult_process_configurationId | - | ARRAY STRING 2D | - | X |
| pathsOfPiffXml_process_configurationId | - | ARRAY STRING 2D | - | X |

__Unmapped outputs variables (which are not sent to the following boxes) :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

