## Copy Init
### Script Language

All the __Copy Init__ box is written in Dynamic Java.
### What the box does ?

COPY INIT DESCRIPTION

*__Copy Init__ box is preceded by the __Scenario Analyser__ box (this box makes it possible to test if files or directories do not exist and therefore to determine which configurations or frequencies to restart) and followed by the __Update Monitoring__ box (allows to update the status of the workflow and to pass the finished parts in "completed")*.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733988-401e8b00-3b99-11ea-9015-013f4ee6d3d6.jpeg)
----------------------------


### Which files to import ?

To execute the script __Copy Init__ correctly, we need to import Python libraries.
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
| linearFrequencies | All linear frequencies in the XML file | ARRAY DOUBLE | - | X |
| numberOfConfigurations | Configuration number in the XML file | INT | - | X |
| pathOfLogsFolder | Logs folder result repository | STRING | - | X |
| pathsOfUserFieldmeshes | DESCRIPTION | ARRAY STRING | - | X |
| maxNodeMemory | Max node memory available | INT | - | X |
| numberOfCoresByNode | Number of core in each node memory | INT | - | X |
| maxNumberOfProcesses | Maximum processes number | INT | - | X |
| memorySecurityCriteria | Security criteria for memory | REAL | - | X |
| namesOfPostprocessingProcesses | DESCRIPTION | ARRAY STRING | - | X |
| areBaseline | DESCRIPTION | BOOL | - | X |
| baselineConfigurationsIds | DESCRIPTION | INT | - | X |
| machAtFan | DESCRIPTION | REAL | - | X |
| velocityAtFan | DESCRIPTION | REAL | - | X |
| staticCelerityAtFan | DESCRIPTION | REAL | - | X |
| staticFluidDensityAtFan | DESCRIPTION | REAL | - | X |
| Cp | DESCRIPTION | REAL | - | X |
| Cv | DESCRIPTION | REAL | - | X |
