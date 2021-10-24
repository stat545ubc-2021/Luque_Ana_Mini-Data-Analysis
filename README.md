# Luque_Ana_Mini-Data-Analysis
Repository where the Milestone 1, 2 and 3 of the Mini Data Analysis will be done for the STAT545a course. In which a data set was analyzed by generating research questions and creating graphs and tables to explore more in depth the information. 

To edit the rmd file you will need to install R studio and create a link with the github repository ([click here to learn more about linking github and R studio](https://happygitwithr.com/rstudio-git-github.html)). It is best to work in a separate branch to avoid messing with the original files, after the changes are done you can do a pull request ([click here to learn more about Pull Requests & the GitHub Workflow](https://guides.github.com/introduction/flow/)).

Data manipulation packages *(dyplr and tidyr)* and graphing packages (*ggplot2*) were used to explore more in depth the data set. Other libraries  may be needed in different milestones, you can find them at the beginning of the files.

Moreover, a brief explanation of ggplot. It is a package that can be loaded in R studio, used to generate different type of graphs. The first argument is always the tibble where your data set is stored, then you will set the aesthetic mapping (with aes()), the first two variables are the x and the y axis, then you can add parameters like color and fill that are related to your variables. You then add on layers named geoms (like geom_point() or geom_histogram()), inside this layers you can also specify constant parameters such as width, color and fill. ([click here to learn more about the ggplot2 package](https://rafalab.github.io/dsbook/ggplot2.html).

Dplyr is used for data manipulation, allowing you to add new variables (mutate), select a set of columns by their names (select), filter some rows (filter), reduce multiple variables into a summary (summaries) etc.. ([click here to learn more about the dyplyr package](https://afit-r.github.io/dplyr).

"%in%" Is used instead of "==".
" %>% " Is for pipping and is used to nest functions.
"<-" is used to assign a function to a variable.
"print" is used to print the variable in the r console.

:pencil2: *Milestone 1*
Different data sets were presented and one had to be chosen to make four research questions.
The chosen data set was **Cancer_samples**. It was obtained from the UCI Machine Learning Repository and it contains information about the cell nuclei in the biopsy of a breast cancer mass obtained with fine needle aspirate (FNA) and analyzed through machine learning using digitized imaging. 

It contains the ID of the patient and the diagnosis B: benign tumor and M= malign tumor.

It has the mean, standard error (se), and worst (max) values of each variable:

* radius (mean of distances from center to points on the perimeter)in um
* texture (standard deviation of gray-scale values)
* perimeter in um
* area in um^2
* smoothness (local variation in radius lengths)
* compactness (perimeter^2 / area - 1.0)
* concavity (severity of concave portions of the contour)
* concave points (number of concave portions of the contour)
* symmetry
* fractal dimension ("coastline approximation" - 1)


:pencil2: *Milestone 2*
The main objective of analyzing this data set is to determine which variables can be used to diagnose tumors by imaging analysis of nuclei from biopsies, and the main differences between de nuclei of benign and malign tumors, Using ggplot2 and dyplyr packages the following research questions were analyzed.

1. Is there a difference within the area of the nuclei of benign and malign tumors?
2. Do malign tumors have more variability in smoothness in their nuclei than benign tumors?
3. Could it be possible to diagnose the tumor of a patient just by looking at the concavity of the nuclei?
4. Is there a relationship between the symmetry of the nuclei and the compactness in malign tumors? 

Furthermore, an exploration about tidy and untidy data was made.

:pencil2: *Milestone 3*

In this file two research questions were chosen to sharpen the results. The main intention of this milestone is manipulating special data types specifically factors. Moreover a linear model was created between two variables. Later on the model was used to make predictions in both malign and benign samples.  
Finally a CSV file was created from a summary table, the function here::here was used to save the file in a specific location within the project repository. The model was saved in a RDS file, making it possible to load it again from any other RMD file.  

The following research questions were analyzed.

1. Could it be possible to diagnose the tumor of a patient just by looking at the concavity of the nuclei?
2. Is there a relationship between the area of the nuclei and the perimeter in malign tumors?


