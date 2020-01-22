## Create Folders
### Script Language

All the __Create Folders__ box is written in Shell UNIX language.
### What the box does ?

This script consists in initializing an array containing the various Isight variables (containing repository names) then the creation of these different folders. In the Canonical Intake Workflow case, we need a folder for each member of this list :

- Acoustic Mesh
- Inputs
- Linear Acoustic Models
- Linear Computations
- Linear Cutoff
- Linear Postprocessing
- Logs
- Microphones
- Scout Computations
- Scripts

Finally, the script modifies the acces rights in RWX (770) and for groups (gr-acplat in our case).

__Create Folders__ box is preceded by the __Reference to Init_v2020r1__ box, which consists in correctly initializing the environment necessary for launching the Workflow and followed by the __Check & Read XML__ box which consist in the XML file reading & checking.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733876-0e0d2900-3b99-11ea-8aef-c4e3a3eb80dd.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs/outputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfAcousticMeshesFolder | Acoustic Meshes Folder - Usually "ACOUSMESH" | STRING | X | X |
| nameOfInputsFolder | Input folder - Usually "INPUTS" | STRING | X | X |
| nameOfLinearAcousticModelsFolder | Acoustic Models Folder - Usually "LINEAR/MODELS" | STRING | X | X |
| nameOfLogsFolder | Logs Folder - Usually "LOGS" | STRING | X | X |
| nameOfLinearComputationsFolder | Linear Computations Folder - Usually "LINEAR/COMPUTATIONS" | STRING | X | X |
| nameOfLinearCutoffFolder | Linear Cutoff Folder - Usually "LINEAR/CUTOFF" | STRING | X | X |
| nameOfLinearPostprocessingFolder | Linear Postprocessing Folder - Usually "LINEAR/POST" | STRING | X | X |
| nameOfMicrophonesFolder | Microphones Folder - Usually "MICROPHONES" | STRING | X | X |
| nameOfScoutComputationsFolder | Scout Computations Folder - Usually "SCOUT" | STRING | X | X |
| nameOfScripts | Scripts Folder - Usually "SCRIPTS" | STRING | X | X |
| pathOfJobFolder | Job Folder Repository | STRING | X | - |
