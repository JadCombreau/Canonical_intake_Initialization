## Update Monitoring
### Script Language

All the __Update Monitoring__ box is written in Python language.
### What the box does ?

This script allows to update the status of the workflow and to pass the finished parts in *"completed"*.
It allows to modify the XML file directly (using of the Python language DOM API - *Document Object Model*) which allows you to access the tree structure of an XML file and thus read or modify the nodes and information that interest us.

__Update Monitoring__ box is preceded by the __Copy Init__ box which consists in copying folders from our Job folder (after modifications) into the Numacous folder. This is the last box of the Initialization part.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733988-401e8b00-3b99-11ea-9015-013f4ee6d3d6.jpeg)
----------------------------


### Which files to import ?

To execute the script __Update Monitoring__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

| Import name | Import location |
| ------ | ------ |
| UpdateMonitoring | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| linearFrequencies | Linear Frequencies from XML file | ARRAY REAL | X | - |
| numberOfConfigurations | Number of configurations from XML file | INT | X | - |
| meshFrequencies | Mesh Frequencies array from "Get Mesh & Models Frequencies" box | ARRAY REAL | X | - |
| modelFrequencies | Model Frequencies from "Get Mesh & Models Frequencies" box | ARRAY REAL | X | - |
| linearComputations | Linear Computations folder name | STRING | X | - |
| initialization | Initialization folder name| STRING | X | - |
| linearPreComputations | Linear Pre Computations (Scout) folder name | STRING | X | - |
| microphones | Microphones folder name | STRING | X | - |
| linearCutoffComputations | Linear Cutoff Computations folder name | STRING | X | - |
| flow | Flow folder name | STRING | X | - |
| linearAcousticModels | Linear Acoustic Models folder name | STRING | X | - |
| interpolatedMeshes | Interpolated Meshes folder name | STRING | X | - |
| acousticMeshes | Acoustic Meshes folder name | STRING | X | - |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X | - |
| pathOfMonitoringStatus | "status.log" file input path | STRING | X | - |
| areAcousticMeshes | True if inputs are Acoustic Meshes | BOOLEAN | X | - |
| areLinearAcousticModels | True if inputs are Linear Acoustic Models | BOOLEAN | X | - |
| isFlow | True if input is Flow | BOOLEAN | X | - |
| isFlowMesh | True if input is Flow Mesh | BOOLEAN | X | - |
| areMicrophones | True if inputs are Microphones | BOOLEAN | X | - |
| areLinearCutoffResults | True if inputs are Linear Cutoff Results | BOOLEAN | X | - |
| areInterpolatedMeshes | True if inputs are Interpolated Meshes | BOOLEAN | X | - |
| areLinearResults | True if inputs are Linear Results | BOOLEAN | X | - |
| areScoutResults | True if inputs are Scout Results | BOOLEAN | X | - |
| nbAcousticMeshesAvailable | Number of Acoustic Meshes Available | INT | X | - |
| nbCutoffResultsAvailable | Number of Cutoff Results Available | INT | X | - |
| nbInterpolatedMeshesAvailable | Number of Interpolated Meshes Available | INT | X | - |
| nbLinearAcousticModelsAvailable | Number of Linear Acoustic Models Available | INT | X | - |
| nbLinearResultsAvailable | Number of Linear Results Available | INT | X | - |
| nbScoutResultsAvailable | Number of Scout Results Available | INT | X | - |
