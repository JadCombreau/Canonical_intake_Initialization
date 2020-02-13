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
| pathOfTools | Tools directory path | STRING | - | X |
| pathOfScriptsRootFolder | Path of the Scripts root directory | STRING | - | X |
| pathOfNacelle | Path of nacelle directory | STRING | - | X |
| pathsOfSpinner | Path of Spinner directory | STRING | - | X |
| pathOfInputXml | Path of input XML file | STRING | - | X |
| pathOfMonitoringStatus | Path of Monitoring status directory | STRING | - | X |
| pathOfConstraints | Path of constraints directory | STRING | - | X |
| pathsOfSizeMesh | Path of size mesh directory | ARRAY STRING | - | X |
| pathsOfAcousticMeshes | Paths of Acoustic Meshes directories | ARRAY STRING | - | X |
| pathOfAcousGeomData | Path of Acoustic Geometric Data directory | STRING | - | X |
| pathOfMicrophones | Path of Microphones directory | STRING | - | X |
| pathsOfFieldmeshes | Paths of fields meshes directories | ARRAY STRING | - | X |
| pathsOfFieldmeshesPtl | Paths of Fields meshes Ptl directories | ARRAY STRING | - | X |
| pathOfActranAcousticSession | Paths of Actran Acoustic Session directories | STRING | - | X |
| pathsOfLinearModels_configuration_linearFrequency | Paths of linear models directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsEnv_configuration_linearFrequency | Paths of environment linear acoustic models directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsMemo_configuration_linearFrequency | Paths of linear acoustic models memos directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfNumacousLinearModels_configuration_linearFrequency | Paths of numacous linear models directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearCutoffMemo | Paths of linear cutoff memo directories | ARRAY STRING | - | X |
| pathsOfCutoffResults | Paths of cutoff results directories | ARRAY STRING | - | X |
| pathsOfScoutMemo | Paths of scout memo directories | ARRAY STRING | - | X |
| pathsOfScoutResults | Paths of scout results directories | ARRAY STRING | - | X |
| pathsOfScoutModels | Paths of scout models directories | ARRAY STRING | - | X |
| pathsOfScoutMemosActran | Paths of scout memos actran directories | ARRAY STRING | - | X |
| pathsOfScoutResultsActran | Paths of scout results Actran directories | ARRAY STRING | - | X |
| pathsOfScoutLogs | Paths of scout logs directories | ARRAY STRING | - | X |
| pathsOfLinearLogs_configuration_linearFrequency | Paths of linear logs directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearMemos_configuration_linearFrequency | Paths of linear memos directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearMemosActran_configuration_linearFrequency | Paths of linear memo Actran directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearResults_configuration_linearFrequency | Paths of linear results directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsActran_configuration_linearFrequency | Paths of linear results Actran directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtl_configuration_linearFrequency | Paths of linear results Ptl directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtlActran_configuration_linearFrequency | Paths of linear Results Ptl Actran directories (for each frequency of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfAttenuationsMatrices_process_configurationId | Paths of attenuations matrices directories | ARRAY STRING 2D | - | X |
| pathsOfPiffResult_process_configurationId | Paths of piff result directories (for each process of each configuration) | ARRAY STRING 2D | - | X |
| pathsOfPiffXml_process_configurationId | Paths of XML piff (for each process of each configuration) | ARRAY STRING 2D | - | X |
| nbTreatments | Number of Treatments | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | True if input is "enginerating" input | BOOLEAN | - | X |
| enginerating | Enginerating value | DOUBLE | - | X |
| areAttenuationMatrices | True if inputs are Matrices Attenuations | BOOLEAN | - | X |

