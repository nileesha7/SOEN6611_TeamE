# SOEN6611_TeamE


## 1. File Structure

+ Scripts
    - main.py (Python script to calculate pearson and spearman correlation coefficient)
+ Projects
    - OverallDataAnalysis
        - Files related to correlation of metrics for all projects.
    - {Project_wise_folder} e.g. apache-sling
        + Code Change
            - ConfigurationChanges.txt
        + Data Analysis
            - Files related to correlation of metrics.
        + Data Collection
            - Version_X.X.X
                + JaCoco
                + Pitest
                + Bugs_vX.X.X.csv
                + CLOC_vX.X.X
            - Version_Y.Y.Y
                + JaCoco
                + Pitest
                + Bugs_vY.Y.Y.csv
                + CLOC_vY.Y.Y


- The repository contains a **Projects** folder which has all the data pertaining to the project.
- Inside the project folder there are 5 project folders named **(FileUpload, JfreeChart, Common-IO, apache-sling, common-collections)**
- The **Projects** folder also includes overall data analysis folder containing various data analysis files for all metrics and all projects.
- Inside each of the project folders, there are three folders **CodeChange, DataAnalysis and DataCollection**.
- **Data collection** contains raw data version wise. 
    + **File Upload/Data Collection/Version_1.2.1/JacCoco** contains the **Jacoco reports** for the File Upload project for its 1.2.1 version.
    + **File Upload/Data Collection/Version_1.2.1/pitest** contains the **PiTest report** for the File Upload project for its 1.2.1 version.
    + **File Upload/Data Collection/Version_1.2.1/CLOC_v1.2.1.csv** contains the **Lines of code** for the File Upload project for its 1.2.1 version.
    + **File Upload/Data Collection/Version_1.2.1/Bug_v1.2.1.csv** contains the **Bug list** for the File Upload project for its 1.2.1 version.
- **Data Analysis** inside the project name folder contains data analysis of all matrics for all versions of that project.
- **Code Change** inside the project name folder contains configuration code.


## 2. Commands used to run the tools for collecting the data
Before executing following commands ensure Jacoco and PiTest plugins mentioned in all projects are updated in `POM.XML` <br />
Note : All these commands are executed using command prompt/terminal: 
+ For code coverage and McCabe Complexity run Jacoco Reports - 
    - Go to the project folder and run – `mvn verify`
    - From within the project go to target\site\jacoco
+ We used PiTest to retrieve the mutation score for all versions of the project.
    - From the project directory, run the following command <br />
       &nbsp; `mvn org.pitest:pitest-maven:mutationCoverage`
+ We used CLOC tool to retrieve data for code churns and post release defect density and store them in csv files, so we used the following commands 
    - `cloc ‘path\Project_Name’ > filename.csv`  for deriving code churns data
    - `cloc --diff ‘path\Project_Name_Version_A’ ‘path \Project_Name_Version_B’ > filename.csv`  <br />
     &nbsp; which compared the elements of version A and version B and then exported the data to filename.csv. All this data is stored    in each version of the projects folder. <br />
`Source : https://sourceforge.net/projects/cloc/files/cloc/v1.64/`
+ Steps to Run Projects/Scripts/main.py - for computing correlations between various metrices 
    - Install python 3 or above, pip and pip install pandas, scipy, numpy and matlpotlib libraries.
    - Run python file and run `python main.py` on the terminal/command prompt

## 3. Team Members

- Jasraj Singh Bedi | 40046931 | jasraj3453@gmail.com
- Himanshu Kohli | 40070839 | atomicboy2012@gmail.com
- Neelisha Fernandes | 40053845 | nileesha.fernando94@gmail.com
- Sagar Vetal | 40071979 | vetal.sagar07@gmail.com
- Simran Sidhu | 40011611 | simrantechm@gmail.com
 

