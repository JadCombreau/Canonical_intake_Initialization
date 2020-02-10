## Build Paths
### Script Language

All the __Build Paths__ box is written in Python language.
### What the box does ?

This Python script allows the creation of different file paths necessary for all the Workflow.

Indeed, according to the preceding boxes which allowed us to know the number of frequencies and configurations for example, we must now create a folder by configuration and one by frequency. The different paths are created here but the folders themselves will be created later.

__The script is divided into different sub-areas for easier understanding :__

- *The "folders" part*
- *The "common" part*
- *The "acousmesh" part*
- *The "microphones" part*
- *The "linear models" part*
- *The "linear cutoff" part*
- *The "scouts" part*
- *The "linear computations" part*
- *The "postprocessing" part*

*In this Workflow case (*Canonical Intake*), we need to retrieve the values for the number and the name of all configurations, the number of treatments, the frequencies as well as the name of the post-processing process (This list is not exhaustive)

*__Build Paths__ box is preceded by the __Link Data from Numacous__ box, which consist in the Numacous directory link (copy of all files from this directory to the Job Folder repository) and followed by the __Scenario Analyser__ box (this box makes it possible to test if files or directories do not exist and therefore to determine which configurations or frequencies to restart)*.

![Initialization components](https://user-images.githubusercontent.com/45098441/72734164-7eb44580-3b99-11ea-8313-26fdce7081a8.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Inputs variables to be given to Isight or received from previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfTools | Name of tools - Usually "tools.list" | STRING | X |- |
| nameOfNacelle | Name of Nacelle - Usually "nacelle.stp" | STRING | X |- |
| nameOfSpinner | Name of Spinner - Usually "spinner.stp" | STRING | X | - |
| nameOfInputXml | Name of result input XML - Usually "input.xml" | STRING | X | - |
| nameOfMonitoringStatus | Name of Monitoring Status - Usually "status.log" | STRING | X | - |
| formatOfFrequencyStr | Format of Frequency - Usually "%08.2fHz" | STRING | X | - |
| formatOfConfigurationIdStr | Format of Configuration Id - Usually "%03d" | STRING | X | - |
| nameOfActranMemo | Name of actran Memo - Usually "bsub.actran.memo" | STRING | X | - |
| nameOfConstraints | Name of constraints - Usually "constraints.txt" | STRING | X | - |
| formatOfSizeMesh | Format of size Mesh - Usually "size_%s.unv" | STRING | X |- |
| nameOfGeomAcousData | Name of Geom Acous Data - Usually "geom_acous.data" | STRING | X |- |
| formatOfAcousticMesh | Format of Acoustic Mesh - Usually "mesh_%s.unv" | STRING | X | - |
| formatOfFieldmesh | Format of Filed Mesh - Usually "fieldmesh_%s.unv" | STRING | X | - |
| formatOfFieldmeshPtl | Format of Field Mesh Ptl - Usually "fieldmesh_%s.ptl" | STRING | X | - |
| nameOfMicrophones | Name of Microphones - Usually "microphones.txt" | STRING | X | - |
| formatOfAcousticModel | Format of Acoustic Model - Usually "conf%s_freq%d.edat" | STRING | X | - |
| nameOfSessionForAcousticAnalysis | Name of Session for Acoustic Analysis - Usually "tutu.py" | STRING | X | - |
| nameOfEnvFile | Name of Environment file | STRING | X | - |
| nameOfCutoffModes | Name of Cutoff Modes | STRING | X |- |
| formatOfScoutMemo | Format of Scout Memo | STRING | X |- |
| formatOfScoutMode | Format of Scout Mode | STRING | X | - |
| formatOfScoutResult | Format of Scout Result | STRING | X | - |
| nameOfActranSequentialLog | Name of Actran Sequential Log | STRING | X | - |
| nameOfActranParallelLog | Name of Actran Parallel Log | STRING | X | - |
| formatOfComputationResultActran | Format of Computation Result Actran | STRING | X | - |
| nameOfActranResultPtl | Name of Actran Result Ptl | STRING | X | - |
| formatOfComputationResultPtl | Format of Computation Result Ptl | STRING | X | - |
| formatOfComputationResult | Format of Computation Result | STRING | X |- |
| formatOfComputationMemo | Format of Computation Memo | STRING | X |- |
| formatOfAttenuationsMatrix | Format of Attenuations Maxtrix | STRING | X | - |
| formatOfLinearPiffResult | Format of Linear Piff Result | STRING | X | - |
| nameOfLinearPiffXML | Name of Linear Piff XML | STRING | X | - |
| nameOfInputs | Name of Inputs - Usually "INPUTS" | STRING | X | - |
| nameOfInfo | Name of Info | STRING | X | - |
| nameOfScripts | Name of Scripts - Usually "SCRIPTS" | STRING | X | - |
| formatOfFrequencyFolder | Format of Frequency directory - Usually "FREQ_%s" | STRING | X | - |
| formatOfConfigurationFolder | Format of Configuration Folder directory - Usually "CONF_%s" | STRING | X |- |
| nameOfFlowMeshFolder | Name of Flow Mesh directory - Usually "FLOWMESH" | STRING | X |- |
| nameOfFlowFolder | Name of Flow directory - Usually "FLOW" | STRING | X | - |
| nameOfAcousticMeshesFolder | Name of Acoustic Meshes directory - Usually "ACOUSMESH" | STRING | X | - |
| nameOfMicrophonesFolder | Name Of Microphones directory - Usually "MICROPHONES" | STRING | X | - |
| nameOfInterpolatedMeshesFolder | Name of Interpolated Meshes directory - Usually "INTERPOLATED_MESH" | STRING | X | - |
| nameOfLinearAcousticModelsFolder | Name of Linear Acoustic Models directory - Usually "LINEAR/MODELS | STRING | X | - |
| nameOfLinearCutoffFolder | Name of Linear Cutoff directory - Usually "LINEAR/CUTOFF" | STRING | X | - |
| nameOfScoutComputationsFolder | Name of Scout computations directory - Usually "SCOUT" | STRING | X |- |
| nameOfLinearComputationsFolder | Name of Linear computations directory - Usually "LINEAR/COMPUTATIONS" | STRING | X | - |
| formatOfPostprocessingProcessFolder | Format of Post Processing Process directory - Usually "MODALCONTENT_%s" | STRING | X | - |
| formatOfRelativePostprocessingFolder | Format of Relative Post Processing directory - Usually "RELATIVE_CONF%s" | STRING | X | - |
| nameOfLinearPostprocessingFolder | Name of Linear Post Processing directory - Usually "LINEAR/POST" | STRING | X | - |
| nameOfAbsolutePostprocessingFolder | Name of Absolute Post Processing directory | STRING | X | - |
| pathOfJobFolder | Path of Job Folder (to copy all results) | STRING | X | - |
| pathOfResourcesFolder | Path of Resources directory | STRING | X | - |
| meshFrequencies | Mesh Frequencies array from "Get Mesh & Models Frequencies" box | ARRAY REAL | X |- |
| pathOfUserFieldmeshes | Path of User Field Meshes | ARRAY STRING | X | - |
| areBaseline | Array of "True" if inputs are Baseline | ARRAY BOOL | X | - |
| baselineConfigurationIds | Baseline Configurations Ids | ARRAY INT | X | - |
| namesOfPostprocessingProcesses | Name of Post Processing Processes | ARRAY STRING | X | - |
| linearFrequencies | Linear Frequencies array | ARRAY REAL | X | - |
| numberOfConfigurations | Number of Configurations | INT | X | - |
| modelFrequencies | Models Frequencies from "Get Mesh & Models Frequencies" box | ARRAY REAL | X | - |
| pathOfNumacousFolder | Path of Numacous directory | STRING | X | - |

__Outputs variables to send to following boxes :__

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
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

