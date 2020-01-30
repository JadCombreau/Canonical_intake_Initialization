## Get Job ID
### Script Language

Init Workflow part contains three boxes :

- *__Get JobID__ box written in Java language*
- *__Initialization__ box written in Java language*
- *__Copy Scripts & Manage Rights__ written in Shell UNIX language*

### What boxes do ?

__Get JobID :__

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

__Initialization :__

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

__Copy Scripts & Manage Rights :__

In the case of this Workflow (Canonical Intake), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

![Initialization components](https://user-images.githubusercontent.com/45098441/72733867-08afde80-3b99-11ea-88fb-0736ee0ea2e3.jpeg)

__Init__ subpart is preceded by the __Set ANANAX environment and resources PATH__ box, which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Create Folders__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just linear frequencied to which we applied a step)

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
