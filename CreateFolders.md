## Create Folders
### Script Language

All the __Create Folders__ box is written in Bash (Shell UNIX language).
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

Finally, the script modifies the acces rights in __RWX (770)__ and for groups (__gr-nactools__ in our case).

__Create Folders__ box is preceded by the __Init__ Workflow subpart, which consists in correctly environment initializing (necessary for Workflow launching). This scripts box is followed by the __Check & Read XML__ box which consist in the XML file checking and reading.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733876-0e0d2900-3b99-11ea-8aef-c4e3a3eb80dd.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Inputs variables to be given to Isight or received from previous boxes :__  

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfAcousticMeshesFolder | Acoustic Meshes Folder - Usually "ACOUSMESH" | STRING | X | - |
| nameOfInputsFolder | Input folder - Usually "INPUTS" | STRING | X | - |
| nameOfLinearAcousticModelsFolder | Acoustic Models Folder - Usually "LINEAR/MODELS" | STRING | X | - |
| nameOfLogsFolder | Logs Folder - Usually "LOGS" | STRING | X | - |
| nameOfLinearComputationsFolder | Linear Computations Folder - Usually "LINEAR/COMPUTATIONS" | STRING | X | - |
| nameOfLinearCutoffFolder | Linear Cutoff Folder - Usually "LINEAR/CUTOFF" | STRING | X | - |
| nameOfLinearPostprocessingFolder | Linear Postprocessing Folder - Usually "LINEAR/POST" | STRING | X | - |
| nameOfMicrophonesFolder | Microphones Folder - Usually "MICROPHONES" | STRING | X | - |
| nameOfScoutComputationsFolder | Scout Computations Folder - Usually "SCOUT" | STRING | X | - |
| nameOfScripts | Scripts Folder - Usually "SCRIPTS" | STRING | X | - |
| pathOfJobFolder | Job Folder Repository | STRING | X | - |
