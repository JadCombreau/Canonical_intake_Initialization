## Create Folders
### Script Language

All the __Create Folders__ box is written in Shell UNIX language.
### What the box does ?



__Check & Read XML__ box is preceded by the __Reference to Init_v2020r1__ box, which consist in the correct copy of all files and folders required for this workflow and followed by the __Check & Read XML__ box which consist in the XML file reading & checking.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733876-0e0d2900-3b99-11ea-8aef-c4e3a3eb80dd.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfAcousticMeshesFolder | DESCRIPTION | STRING | X |- |
| nameOfInputsFolder | DESCRIPTION | STRING | X |- |
| nameOfLinearAcousticModelsFolder | DESCRIPTION | STRING | X | - |
| nameOfLogsFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearComputationsFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearCutoffFolder | DESCRIPTION | STRING | X | - |
| nameOfLinearPostprocessingFolder | DESCRIPTION | STRING | X | - |
| nameOfMicrophonesFolder | DESCRIPTION | STRING | X | - |
| nameOfScoutComputationsFolder | DESCRIPTION | STRING | X | - |
| nameOfScripts | DESCRIPTION | STRING | X | - |
