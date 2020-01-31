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
*We also have a test case for "IsNIS"*

__Copy Scripts & Manage Rights :__

*__Copy Scripts & Manage Rights__ script allows the folders copy and rights managing*

__Init__ subpart is preceded by the __Set ANANAX environment and resources PATH__ box, which consist in variable environment sourcing (necessary for the execution of the various workflow scripts) and followed by the __Create Folders__ box which consist in the repository creation (contained in the namesOfFolder agregate).

![Initialization components](https://user-images.githubusercontent.com/45098441/72733867-08afde80-3b99-11ea-88fb-0736ee0ea2e3.jpeg)

![Details](https://user-images.githubusercontent.com/45098441/72733862-02216700-3b99-11ea-90d0-fba2f892a949.jpeg)

----------------------------


### Which files to import ?

To execute these scripts correctly, we need to import Python libraries.
The table below lists all the imports to be made for each box :

__Get JobID box :__

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

__Initialization box :__

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

__Copy Scripts & Manage Rights box :__

| Import name | Import location |
| :------: | :------: |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

__Init general subpart :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Get JobID box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Initialization box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |

__Copy Scripts & Manage Rights box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | X |- |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | X |- |


__Mapped outputs variables to send to following boxes :__

__Init general subpart :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Get JobID box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Initialization box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |

__Copy Scripts & Manage Rights box :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| XMLInput | Input XML which contain all data | FILE | - | X |
| pathOfPythonSrcFolder | Python source folder wich contain all librairies | STRING | - | X |
