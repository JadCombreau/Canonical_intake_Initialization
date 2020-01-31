## Init Workflow Subpart
### Scripts Language

Init Workflow part contains three boxes :

- *__Get JobID__ box written in Java language*
- *__Initialization__ box written in Java language*
- *__Copy Scripts & Manage Rights__ written in Shell UNIX language*

### What boxes do ?

This sub-part allows the initialization of the different paths and the construction of the paths for each execution (for each frequency of each configuration via the JobID).

It is separated into three boxes which are linked together.

__Get JobID :__

*The script __Get JobID__ allows to determine on which directory to work by calling on the JobID which will allow us to create the different paths and directories later.*

__Initialization :__

*This script makes it possible to obtain the name of study but also the name of the various processes.*
*This script allows the construction of the Numacous Folder path according to the JobID.*

__Copy Scripts & Manage Rights :__

*...*

![Initialization components](https://user-images.githubusercontent.com/45098441/72733867-08afde80-3b99-11ea-88fb-0736ee0ea2e3.jpeg)

__Init__ subpart is preceded by the __Set ANANAX environment and resources PATH__ box, which consist in ... and followed by the __Create Folders__ box which consist in ...

![Details](https://user-images.githubusercontent.com/45098441/72733862-02216700-3b99-11ea-90d0-fba2f892a949.jpeg)

----------------------------


### Which files to import ?

To execute the script __Check & Read XML__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

__Init__ subpart :

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |
| CommonFunctions | `/python/workflows/common` |
| PiffPostprocessing | `/python/workflows/ductnoise/common/postprocessing` |
| PiffPostprocessingAnanax2dCanonicalIntake | `/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

__Get JobID__ box :

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

__Initialization__ box :

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

__Copy Scripts & Manage Rights__ box :

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

__Init__ subpart :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Get JobID__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Initialization__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Copy Scripts & Manage Rights__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |


__Mapped outputs variables to send to following boxes :__

__Init__ subpart :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Get JobID__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Initialization__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Copy Scripts & Manage Rights__ box :

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |
