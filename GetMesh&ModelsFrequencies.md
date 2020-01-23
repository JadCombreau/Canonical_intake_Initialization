## Get Mesh & Models Frequencies
### Script Language

All the __Get Mesh & Models Frequencies__ box is written in Python.
### What the box does ?

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

*__Get Mesh & Models Frequencies__ box is preceded by the __Check & Read XML__ box which consist in the XML file reading & checking and followed by the __Link Data from Numacous__ box which consist in the Numacous directory link (copy of all files in this directory to the Job Folder repository)*

![Initialization components](https://user-images.githubusercontent.com/45098441/72733887-149ba080-3b99-11ea-8a0b-7e1238c4e042.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| linearFrequencies | Array containing all XML linear frequencies | ARRAY REAL | X |- |
| stepOfMeshFrequencies | Usually "1000.0" | REAL | X |- |
| minMeshFrequency | Usually "2000.0" | REAL | X | - |


__Mapped outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| meshFrequencies | All mesh frequencies after script | ARRAY REAL | - | X |
| modelFrequencies | - | ARRAY REAL | - | X |




__Unmapped outputs variables (which are not sent to the following boxes) :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| maxFrequency | - | REAL | - | X |
| frequencyUpperRange | - | INT | - | X |
| meshFrequency | mesh frequencies before array | REAL | - | X |

