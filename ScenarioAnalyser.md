## Scenario Analyser
### Script Language

All the __Scenario Analyser__ box is written in Python language.
### What the box does ?

The __Scenario Analyzer__ script allows you to test if there are missing folders/files after the first execution of the workflow (during the first execution, all repositories exists but are empty ...). This script therefore avoids restarting all configurations/frequencies and therefore saves a lot of time.

This script must therefore be able to check if a file is missing in a specific folder (we know exactly the number of configurations and frequencies to launch).

To begin, this script must copy the Numacous Repository and remove folder if it already exists.

__This script must therefore test the existence of each member of the following list :__

- isFlowMesh
- isFlow
- areAcousticMeshConstraints
- areAllAcousticMeshes
- isAcousGeomData
- areMicrophones
- areAllInterpolatedMeshes
- areAllCutoffResults
- areAllScoutResultsAndMemos
- areAllComputationsResults

*__Scenario Analyser__ box is preceded by the __Build Paths__ box which consist in the creation of different file paths necessary for all the Workflow. This box is followed by the __Copy Init__ Workflow subpart which consists in copying folders from our Job folder (after modifications) into the Numacous folder.*

![Initialization components](https://user-images.githubusercontent.com/45098441/72733938-2e3ce800-3b99-11ea-9aef-180fca448d24.jpeg)
----------------------------


### Which files to import ?

To execute the script __Scenario Analyser__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

| Import name | Import location |
| ------ | ------ |
| Logger | `/python/workflows/common` |
| ScenarioAnalyser | `/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

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
| areAcousticMeshes | All linear frequencies in the XML file | ARRAY DOUBLE | - | X |
| areLinearAcousticModels | Configuration number in the XML file | INT | - | X |
| isFlow | Logs folder result repository | STRING | - | X |
| isFlowMesh | DESCRIPTION | ARRAY STRING | - | X |
| areAcousticMeshConstraints | Max node memory available | INT | - | X |
| areMicrophones | Number of core in each node memory | INT | - | X |
| areLinearCutoffResults | Maximum processes number | INT | - | X |
| areInterpolatedMeshes | Security criteria for memory | REAL | - | X |
| areLinearResults | DESCRIPTION | ARRAY STRING | - | X |
| areScoutResults | DESCRIPTION | BOOL | - | X |
| nbAcousticMeshesAvailable | DESCRIPTION | INT | - | X |
| nbCutoffResultsAvailable | DESCRIPTION | REAL | - | X |
| velocityAtFan | DESCRIPTION | REAL | - | X |
| staticCelerityAtFan | DESCRIPTION | REAL | - | X |
| staticFluidDensityAtFan | DESCRIPTION | REAL | - | X |
| Cp | DESCRIPTION | REAL | - | X |
| Cv | DESCRIPTION | REAL | - | X |
| nbTreatments | DESCRIPTION | INT | - | X |
| angles | Array microphones angles - Usually each 5° | ARRAY DOUBLE | - | X |
| isEnginerating | DESCRIPTION | BOOL | - | X |
| enginerating | DESCRIPTION | DOUBLE | - | X |
| areAttenuationMatrices | In intake flow, we want attenuation matrice | BOOL | - | X |

