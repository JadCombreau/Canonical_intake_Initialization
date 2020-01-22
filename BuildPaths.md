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
| formatOfcomputationResultPtl | - | STRINGL | X | - |
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
| pathOfTools | All linear frequencies in the XML file | STRING | - | X |
| pathOfScriptsRootFolder | Configuration number in the XML file | STRING | - | X |
| pathOfNacelle | Logs folder result repository | STRING | - | X |
| pathsOfSpinner | DESCRIPTION | STRING | - | X |
| pathOfInputXml | Max node memory available | STRING | - | X |
| pathOfMonitoringStatus | Number of core in each node memory | STRING | - | X |
| pathOfConstraints | Maximum processes number | STRING | - | X |
| pathsOfSizeMesh | Security criteria for memory | ARRAY STRING | - | X |
| pathsOfAcousticMeshes | DESCRIPTION | ARRAY STRING | - | X |
| pathOfAcousGeomData | DESCRIPTION | STRING | - | X |
| pathOfMicrophones | DESCRIPTION | STRING | - | X |
| pathsOfFieldmeshes | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfFieldmeshesPtl | DESCRIPTION | ARRAY STRING | - | X |
| pathOfActranAcousticSession | DESCRIPTION | STRING | - | X |
| pathsOfLinearModels_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsEnv_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearAcousticModelsMemo_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfNumacousLinearModels_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearCutoffMemo | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfCutoffResults | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutMemo | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutResults | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutModels | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutMemosActran | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutResultsActran | DESCRIPTION | ARRAY STRING | - | X |
| pathsOfScoutLogs | DESCRIPTION | ARRAY STRING | - | X |

| pathsOfLinearLogs_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearMemos_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearMemosActran_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearResults_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsActran_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtl_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfLinearResultsPtlActran_configuration_linearFrequency | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfAttenuationsMatrices_process_configurationId | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfPiffResult_process_configurationId | DESCRIPTION | ARRAY STRING 2D | - | X |
| pathsOfPiffXml_process_configurationId | DESCRIPTION | ARRAY STRING 2D | - | X |

__Unmapped outputs variables (which are not sent to the following boxes) :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

