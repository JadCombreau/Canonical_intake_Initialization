## Set ANANAX Environment and Resources PATH
### Script Language

__Set ANANAX Environment and Resources PATH__ box is written in Python and Bash (Shell UNIX language).
### What the box does ?

These scripts allow you to source the variable environment necessary for the execution of the various workflows scripts (*cdng_ananax_home.tmp*).

This Python script therefore allows you to create the different paths to source. Here we indicate the "jar" (compressed archive Java) file which contains the libraries necessary for the execution of the Java scripts of our Workflow.

__Set ANANAX Environment and Resources PATH__ box is the first script box in our workflow and followed by the __Init__ box, which consist in the correctly environment initializing for Workflow launching.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733839-f46be180-3b98-11ea-9394-2d7339747a44.jpeg)

----------------------------


### Which files to import ?

To execute the script __Set ANANAX Environment and Resources PATH__ correctly, we need to import Python libraries.
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
| version | Process version - Usually "v2020r5" | STRING | X | - |
| command | Process command - Actually "ananaxterm" | STRING | X | - |
| nameOfMetaComponent | Name Of Meta Component - Usually "00_Initialization" | STRING | X | - |


__Mapped outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |
| pathOfJavaSrcFolder | Java source folder wich contain all librairies | STRING | - | X |
| pathOfResourcesFolder | Job folder to copy all results | STRING | - | X |
| nameOfApplicationRootFolder | Name of result logs folder - Usually "LOGS" | STRING | - | X |
| initialization | Name Of Meta Component - Usually "00_Initialization" | STRING | - | X |
