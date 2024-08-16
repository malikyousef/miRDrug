# miRDrug
# miRDrug: Comprehensive Analysis of the Shared Genes Within miRNA-Drug Pairs Using Grouping, Scoring, and Modeling Approach
                                  
 Emma Qumsiyeh1,  Burcu Bakir-Gungor2,   and  Malik Yousef3,4

1Department of  Computer Science and Information Technology, Al-Quds University, Palestine
2Department of Computer Engineering, Faculty of Engineering, Abdullah Gul University, Kayseri, Turkey
3Department of Information Systems, Zefat Academic College, Zefat, Israel
4Galilee Digital Health Research Center, Zefat Academic College, Zefat, Israel

# Corresponding authors:
Malik Yousef: malik.yousef@gmail.com
Emma Qumsiyeh: emma.qumsiyeh@hotmail.com


## Knime Workflow
miRDrug tool is a Knime workflow. In order to run the workflow, you need to download Knime and install it in your local machine.
This is the link for downloading Knime: https://www.knime.com/downloads<br>
For more information about the Knime platform you might visit https://www.knime.com/software-overview <br>
See this [page](pages/SettingsKnime.md) for information about setting Knime.
<br>
Visit this [page](https://github.com/malikyousef/GediNET/blob/main/pages/TableFormat.md) for instruction in how to prepare the dataset into Knime table format (*.table) using a Knime workflow
<br>
Visit this [page](https://github.com/malikyousef/GediNET/blob/main/pages/GroupingFile.md) for instruction in how to upload the Groups file.  
Visit this [page](https://github.com/malikyousef/GediNET/blob/main/pages/outputs.md) for the outputs of GediNET.
<br> 

**Running the workflow:**

- You need to use the node “MCCV Iterations” in order to specify the number of Monte Carlo Cross Validation (MCCV) iterations, for example 10 or 100.
- You need to configure the node “List Files/Folders” to point it to the folder that has the gene expression dataset in a table format (as described above)
- You might [download](GDS4824.table) an example of such data named [GDS2545.table](GDS2545.table)<br>

## The  Pseudocode of miRDrug can seen over this [file](pages/Pseudocode.txt) 
## miRDrug main workflow is: ##

![alt text](https://github.com/malikyousef/GediNET/blob/main/images/GediNET_main.JPG?raw=true)
