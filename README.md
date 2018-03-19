#coding_project

#The purpose of this code is to automate the analysis process of high-performance liquid chromatography (HPLC) tandem-mass spectrometry (MS/MS) data.
#Output from the machine consists of an individual file for each compound and sample. Because most experiments measure several compounds in many samples, as well as water controls and standards for each compound, this results in dozens of output files.
#After extraction from the machine, all analysis is done manually in Excel and Prism, by members of my lab. This is fairly time consuming and very monotonous.
#These scripts, one in Python and one in R, enable the user to extract the relevant data from each raw file into a dataframe, normalize the sample data to standard curve slope values (by linear regression), display the data in a bar plot, and save the data as a final .csv file.
