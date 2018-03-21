# coding_project

The purpose of this code is to automate the analysis process of high-performance liquid chromatography (HPLC) tandem-mass spectrometry (MS/MS) data.

In the Chang lab, we often want to measure levels of certain metabolites in intestinal content samples, from both mice and humans. Metabolite levels can often inform on changes in physiology, such as an influx of gut microbes that produce a particular compound. We utilize HPLC-MS/MS to measure metabolite levels, which ionizes samples and sorts compounds by their mass-to-charge ratio, measured in the form of peak area.

Output from the HPLC-MS/MS machine consists of an individual file for each compound and sample. Because most experiments measure several compounds in many samples, as well as water controls and standards for each compound, this results in dozens of output files. After data extraction from the machine, all analysis is usually done manually in Excel and Prism, by members of my lab. This is time consuming and very monotonous, which is why I chose this process for automation.

The scripts for this analysis, one in Python and one in R, enable the user to extract the relevant data from each raw file into a dataframe, normalize the sample data to standard curve slope values (by linear regression), display the data in a bar plot, and save the data as a final .csv file. The example data included in this project contains water controls, standards, and three human ileostomy samples (52_A1, 56_A1, EL_A1) for 7 metabolites (creatine, tryptophan, serotonin, nms, kynurenine, ipa, and hippuric acid).

The Python script requires a folder of input files (file) and an output file name (output) to run the hplcmsms_dict_csv function. The raw data files in the "rawdata" folder are an example of the format of files that the script requires for correct analysis. Each .CSV file in the "rawdata" folder contains the machine's attempts at MS measurement; the script extracts the "Accepted" measurement attempt with the largest peak value. The "python_data.csv" file is an example of output from this script, which is required as input for the R script.

The R script requires 3 input files (stdfile, mgfile, pythonfile), an output plot file name (plot), and an output data file name (output). The "stdfile" input .csv should contain the concentration of each standard for each metabolite, as shown in the file "std_concentrations.csv". The "mgfile" input .csv should contain the milligrams of each original sample for eventual normalization, as shown in the file "mg_sample.csv". The "pythonfile" input .csv should contain the extracted data from the Python output, as shown in the file "python_data.csv".

