## Update Monitoring
### Script Language

All the __Update Monitoring__ box is written in Python.
### What the box does ?

This script allows to update the status of the workflow and to pass the finished parts in "finished", it allows to modify the XML file directly (using of the Python language DOM API - Document Object Model) which allows you to access the tree structure of an XML file and thus read or modify the nodes and information that interest us.

__Update Monitoring__ box is preceded by the __Copy Init__ box which consists in copying the folder from our Job folder (after modifications) into the Numacous folder. This is the last box of the Initialization part.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733988-401e8b00-3b99-11ea-9015-013f4ee6d3d6.jpeg)
----------------------------


### Which files to import ?

To execute the script __Update Monitoring__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

| Import name | Import location |
| ------ | ------ |
| UpdateMonitoring | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |
| CommonFunctions | `/python/workflows/common` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| linearFrequencies | All linear frequencies in the XML file | ARRAY DOUBLE | X | - |
| numberOfConfigurations | Configuration number in the XML file | INT | X | - |
| meshFrequencies | meshFrequencies array | ARRAY DOUBLE | X | - |
| modelFrequencies | modelFrequencies from linearFrequencies | ARRAY DOUBLE | X | - |
| areAcousticMeshes | All linear frequencies in the XML file | ARRAY DOUBLE | X | - |
| areLinearAcousticModels | Configuration number in the XML file | INT | X | - |
| isFlow | Logs folder result repository | STRING | X | - |
| isFlowMesh | DESCRIPTION | ARRAY STRING | X | - |
| areMicrophones | Number of core in each node memory | INT | X | - |
| areLinearCutoffResults | Maximum processes number | INT | X | - |
| areInterpolatedMeshes | Security criteria for memory | REAL | X | - |
| areLinearResults | DESCRIPTION | ARRAY STRING | X | - |
| areScoutResults | DESCRIPTION | BOOL | X | - |
| nbAcousticMeshesAvailable | DESCRIPTION | INT | X | - |
| nbCutoffResultsAvailable | DESCRIPTION | REAL | X | - |
| nbLinearResultsAvailable | DESCRIPTION | INT | X | - |
| nbScoutResultsAvailable | DESCRIPTION | REAL | X | - |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X | - |
| linearComputations | linearComputations name - Usually 01_Linear/04_LinearComputations | STRING | X | - |
| initialization | Usually 00_Initialization | STRING | X | - |
| linearPreComputations | DESCRIPTION | STRING | X | - |
| microphones | DESCRIPTION | STRING | X | - |
| linearCutoffComputations | DESCRIPTION | STRING | X | - |
| flow | DESCRIPTION | STRING | X | - |
| linearAcousticModels | DESCRIPTION | REAL | X | - |
| interpolatedMeshes | DESCRIPTION | REAL | X | - |
| acousticMeshes | DESCRIPTION | REAL | X | - |
