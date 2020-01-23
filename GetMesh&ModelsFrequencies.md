## Get Mesh & Models Frequencies
### Script Language

All the __Get Mesh & Models Frequencies__ box is written in Python.
### What the box does ?


This script makes it possible to calculate the mesh frequencies according to the linear frequencies coming from the XML file (*input.xml*).

Depending of the *__stepOfMeshFrequencies__* value and the *__minMeshFrequency__* desired, we will refine the linear frequencies and define the mesh frequencies for the geometry.

Finally, the linear frequencies are listed in a table named *__modelFrequencies__*.

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

