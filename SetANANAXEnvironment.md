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
| Logger | `/python/workflows/common` |
| CommonFunctions | `/python/workflows/common` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Inputs variables to be given to Isight or received from previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| version | Name of process version | STRING | X | - |
| command | Process command name | STRING | X | - |
| initialization | Name of Meta Component Initialization folder | STRING | X | - |


__Outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| nameOfMetaComponent | Name of Meta Component folder | STRING | - | X |
| pathOfJavaSrcFolder | Java source folder path wich contain all librairies | STRING | - | X |
| pathOfPythonSrcFolder | Python source folder path wich contain all librairies | STRING | - | X |
| pathOfResourcesFolder | Resources folder path | STRING | - | X |
| nameOfApplicationRootFolder | Path of root folder | STRING | - | X |
