## Link Data From Numacous
### Script Language

All the __Link Data From Numacous__ box is written in Shell UNIX language.
### What the box does ?

This script allows the copy of the data present from the Numacous directory to our Job folder.
For this, the scripts will process all the following files, created previously :

- ACOUSMESH
- INTERPOLMESH
- MICROPHONES
- INPUTS
- INFO
- FLOW
- FLOWMESH
- SCOUT

The input XML file previously nammed "input.xml" will be copied and renamed "previous.xml" in our Job folder.

*__Link Data from Numacous__ box is preceded by the __Get Mesh & Models Frequencies__ box, which consist in the creation of the model frequency list, linked to the linear frequency and followed by the __Build Paths__ box which consist in the creation of different file paths necessary for all the Workflow.*

![Initialization components](https://user-images.githubusercontent.com/45098441/72733893-182f2780-3b99-11ea-938b-583d766d3fde.jpeg)
----------------------------

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Mapped inputs variables to receive to previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| pathOfJobFolder | Job folder to copy all results - Usually "/x86_64/samples/canonicalIntake" | STRING | X | - |
| pathOfNumacousFolder | Numacous folder repository - Usually "/projects/numacous" | STRING | X | - |

