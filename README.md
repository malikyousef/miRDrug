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

## The  Pseudocode of miRDrug can seen over this [file](Pseudocode)


## KNIME prerequisit

## KNIME Version
This workflow was made in version “4.6.3” of KNIME5. Hence, utilizing a version that is at or above the specified version will serve to mitigate the occurrence of unnecessary errors.
Environment Settings
The G-S-M workflow incorporates both Python and R scripts. Therefore, to prevent any errors from occurring, it is essential to properly configure the KNIME Python settings by following the path: 
File -> Preferences -> KNIME (left side of the pop-up) -> Python

Additionally, the R server must be running simultaneously during the execution of the workflow. To initiate the R server, the following commands should be executed in R/RStudio:
library(Rserve);
Rserve(args = "--vanilla")

## Knime Workflow
By adhering to these environmental settings, errors will be effectively mitigated in this stable version of the workflow.

•	List Files/Folders Node ("Node 479"): needs to give the path of the directory which contains data

•	Table Reader ("Node 478"): finds the ".table" file in a given directory and reads those values and put it into a table.

•	Table Reader ("Read miRNA data"): finds the ".table" file in a given directory and reads those values and put it into a table.

•	Row Filter ("remove 5.0"): If there is other than a value except for two classes one needs to remove that value from the class column.

•	MissingValues ("Node 477"): extracts missing values and converts required columns from strings to numbers.

•	User Inputs: component including Number of Iteration, Output folder name, Group File Path, and Model parameters.

•	Set Up Parameters ("Node 433"): component including the number of initial clusters, the initial number of genes, the label of the positive class, the number of iterations for internal rank, and reduction ratio parameters.

•	Rank Functions Weights ("Node 434"): Component including accuracy, sensitivity, specificity, F-measure, AUC, and precision weights.

•	Upload Groups File ("Node 466"): uploading grouping file which comes from the "User Inputs" component.

•	G-S-M ("Node 468"): that G-S-M operations are made.

•	Display Result ("Node510"): Component that results are visualized.

## Including Data Path
The source-choosing operation shown in Figure 1 should be performed to specify the directory of input files to be used.
 
 
## Figure 1: Shows how the directory of input files can be selected.
## Parameter Settings
The components below should be set before running the workflow.

## User Inputs
This component possesses four distinct parameters.


1.	Number of Iterations: determines how many iterations the model will make
2.	Output Folder Name: sets the name of the output folder name
3.	Choose Group File: requests file found in gene clusters
4.	Choose Model Name: allows to specify the model to be selected by the user (Current models are: Random Forest, Support Vector Machine, Decision Tree, Naive Bayes, and Treebag Classifiers)

## Set Up Parameters
This component contains the following 5 different parameters.


1.	Number of Initial Clusters
2.	Initial Number of Genes: Determines the number of genes used in the t-test.
3.	The Label of the Positive Class: Requests the value name of positive targets.
4.	Number of Iterations for Internal Rank: (Default value: 5)
5.	Reduction Ratio: (Default value: 0.1)


## Rank Function Weights
The parameters in this component are used to establish the relative importance of different factors in the formula used to calculate the ranking.


1.	Accuracy Weight: (Default value: 1.0)
2.	Sensitivity Weight: (Default value: 0.0)
3.	Specificity Weight: (Default value: 0.0)
4.	F-measure Weight: (Default value: 0.0)
5.	AUC Weight: (Default value: 0.0)
6.	Precision Weight: (Default value: 0.0)





![image](https://github.com/user-attachments/assets/3b3134ff-8d9e-407f-98b5-7500c6cd28cd)

