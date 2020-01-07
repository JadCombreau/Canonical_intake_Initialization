# COMBREAU JAD - ANANAX CANONONICAL INTAKE WORKFLOW
## Markdown documentation file

## Ananax2d_Canonical_Intake Workflow over Isight

### Workflow type

Here is the Workflow structure by specification :

| | CANONICAL | ANALYTICAL |
|-----------|-----------|-----------|
|INLET | `'Isn't this fun?'` | 'Isn't this fun?' |
|ACTRAN |`"Isn't this fun?"` |"Isn't this fun?" |
|MADIWHAX |`is em-dash` | is em-dash |

Explanation of the workflow and his role

Here is the exact structure of the workflow through its different boxes or components :

![Exemple worflow](https://user-images.githubusercontent.com/45098441/71828184-201f9f80-30a2-11ea-81f8-18cfbb8be836.jpeg)


## Check & Read XML

### Explanation of what the box does

This part of the "Check & Read XML" Workflow is for, but, as its name suggests, to verify and read the input XML file of the Workflow. We must therefore retrieve the values that interest us.

First, we must check the structure of the XML input file by running the XSD specific to this type of XML and in the specific case of this Workflow. We will therefore have to indicate the path to the XSD file.

In the case of this Workflow (Canonical Intake), we need to retrieve the values ​​for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process. This list is not exhaustive.

### Which files to import ?

To execute the script "Check & Read XML" correctly, we need to import other Python libraries.
The table below lists all the imports to be made :

| Import name | Import functions | Import location |
| ------ | ------ | ------ |
| XMLAnanax2dCanonicalIntake | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/workflows/common` |
| CommonFunctions | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/workflows/common` |
| PiffPostprocessing | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/workflows/ductnoise/common/postprocessing` |
| PiffPostprocessingAnanax2dCanonicalIntake | FUNCTIONS NAMES | `/share/giseh_fr0_devel/ananax/v2020r1/RedHatEL-7/x86_64/src_wf/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

| Variable Name | Variable description | Value type | Input Value | Output Value |
| ------ | ------------ | ------ | ------ |  ------ |
| pathOfXML | DESCRIPTION | TYPE | INPUT | OUTPUT |
| pathOfLogsFolder | DESCRIPTION | TYPE | INPUT | OUTPUT |
| myLogger | DESCRIPTION | TYPE | INPUT | OUTPUT |
| xsd | DESCRIPTION | TYPE | INPUT | OUTPUT |
| linearFrequencies | DESCRIPTION | TYPE | INPUT | OUTPUT |
| numberOfConfigurations | DESCRIPTION | TYPE | INPUT | OUTPUT |
| namesOfConfigurations | DESCRIPTION | TYPE | INPUT | OUTPUT |
| pathsOfUserFieldmeshes | DESCRIPTION | TYPE | INPUT | OUTPUT |
| nbTreatments | DESCRIPTION | TYPE | INPUT | OUTPUT |
| maxNodeMemory | DESCRIPTION | TYPE | INPUT | OUTPUT |
| numberOfCoresByNode | DESCRIPTION | TYPE | INPUT | OUTPUT |
| maxNumberOfProcesses | DESCRIPTION | TYPE | INPUT | OUTPUT |
| memorySecurityCriteria | DESCRIPTION | TYPE | INPUT | OUTPUT |
| namesOfPostprocessingProcesses | DESCRIPTION | TYPE | INPUT | OUTPUT |
| N1k | DESCRIPTION | TYPE | INPUT | OUTPUT |
| areAttenuationMatrices | DESCRIPTION | TYPE | INPUT | OUTPUT |
| piff | DESCRIPTION | TYPE | INPUT | OUTPUT |


