Mileston-1-Luque.Rmd
================
Ana Luque
October 09, 2021

Loading the packages:

``` r
library(datateachr)
library(tidyverse)
```

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.5     v purrr   0.3.4
    ## v tibble  3.1.4     v dplyr   1.0.7
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   2.0.1     v forcats 0.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

# Task 1: Choose your favorite dataset

## 1.1

Based on the description of the data sets the ones that looked more
interesting and worth of data analysis were:

*1. Flow sample* *2. Cancer sample* *3. Vancouver trees* *4. Steam
games*

## 1.2

Exploring more information about the tibbles.

``` r
#Exploring the Flow_sample tibble
#To know the name of the columns, number of rows and columns glimpse function can be used
glimpse(flow_sample)
```

    ## Rows: 218
    ## Columns: 7
    ## $ station_id   <chr> "05BB001", "05BB001", "05BB001", "05BB001", "05BB001", "0~
    ## $ year         <dbl> 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 191~
    ## $ extreme_type <chr> "maximum", "maximum", "maximum", "maximum", "maximum", "m~
    ## $ month        <dbl> 7, 6, 6, 8, 6, 6, 6, 6, 6, 6, 6, 7, 6, 6, 6, 7, 5, 7, 6, ~
    ## $ day          <dbl> 7, 12, 14, 25, 11, 18, 27, 20, 17, 15, 22, 3, 9, 5, 14, 5~
    ## $ flow         <dbl> 314, 230, 264, 174, 232, 214, 236, 309, 174, 345, 185, 24~
    ## $ sym          <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N~

``` r
#Function used to open the data in the RStudio Data Window
tibble::view(flow_sample)
# Class prints the vector of names of classes an object inherits from.
class(flow_sample)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
#Returns the first 6 rows of a dataframe,
head(flow_sample)
```

    ## # A tibble: 6 x 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1909 maximum          7     7   314 <NA> 
    ## 2 05BB001     1910 maximum          6    12   230 <NA> 
    ## 3 05BB001     1911 maximum          6    14   264 <NA> 
    ## 4 05BB001     1912 maximum          8    25   174 <NA> 
    ## 5 05BB001     1913 maximum          6    11   232 <NA> 
    ## 6 05BB001     1914 maximum          6    18   214 <NA>

``` r
#Exploring the cancer_sample
glimpse(cancer_sample)
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, ~
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "~
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450~
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9~
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, ~
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, ~
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0~
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0~
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0~
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0~
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087~
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0~
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345~
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902~
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18~
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.~
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114~
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246~
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0~
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188~
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0~
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051~
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8~
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6~
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,~
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, ~
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791~
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249~
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0~
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0~
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985~
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0~

``` r
tibble::view(cancer_sample)
class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
head(cancer_sample)
```

    ## # A tibble: 6 x 32
    ##         ID diagnosis radius_mean texture_mean perimeter_mean area_mean
    ##      <dbl> <chr>           <dbl>        <dbl>          <dbl>     <dbl>
    ## 1   842302 M                18.0         10.4          123.      1001 
    ## 2   842517 M                20.6         17.8          133.      1326 
    ## 3 84300903 M                19.7         21.2          130       1203 
    ## 4 84348301 M                11.4         20.4           77.6      386.
    ## 5 84358402 M                20.3         14.3          135.      1297 
    ## 6   843786 M                12.4         15.7           82.6      477.
    ## # ... with 26 more variables: smoothness_mean <dbl>, compactness_mean <dbl>,
    ## #   concavity_mean <dbl>, concave_points_mean <dbl>, symmetry_mean <dbl>,
    ## #   fractal_dimension_mean <dbl>, radius_se <dbl>, texture_se <dbl>,
    ## #   perimeter_se <dbl>, area_se <dbl>, smoothness_se <dbl>,
    ## #   compactness_se <dbl>, concavity_se <dbl>, concave_points_se <dbl>,
    ## #   symmetry_se <dbl>, fractal_dimension_se <dbl>, radius_worst <dbl>,
    ## #   texture_worst <dbl>, perimeter_worst <dbl>, area_worst <dbl>, ...

``` r
#Exploring the Vancouver_trees
glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149~
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7~
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"~
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "~
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C~
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL~
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE~
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "~
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "~
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "~
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7~
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"~
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "~
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD~
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, ~
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00~
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "~
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19~
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08~
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4~

``` r
tibble::view(vancouver_trees)
class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
head(vancouver_trees)
```

    ## # A tibble: 6 x 20
    ##   tree_id civic_number std_street genus_name species_name cultivar_name  
    ##     <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>          
    ## 1  149556          494 W 58TH AV  ULMUS      AMERICANA    BRANDON        
    ## 2  149563          450 W 58TH AV  ZELKOVA    SERRATA      <NA>           
    ## 3  149579         4994 WINDSOR ST STYRAX     JAPONICA     <NA>           
    ## 4  149590          858 E 39TH AV  FRAXINUS   AMERICANA    AUTUMN APPLAUSE
    ## 5  149604         5032 WINDSOR ST ACER       CAMPESTRE    <NA>           
    ## 6  149616          585 W 61ST AV  PYRUS      CALLERYANA   CHANTICLEER    
    ## # ... with 14 more variables: common_name <chr>, assigned <chr>,
    ## #   root_barrier <chr>, plant_area <chr>, on_street_block <dbl>,
    ## #   on_street <chr>, neighbourhood_name <chr>, street_side_name <chr>,
    ## #   height_range_id <dbl>, diameter <dbl>, curb <chr>, date_planted <date>,
    ## #   longitude <dbl>, latitude <dbl>

``` r
#Exploring the steam_games
glimpse(steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14~
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO~
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", ~
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT~
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un~
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re~
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u~
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018~
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain~
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB~
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,~
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie~
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai~
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, ~
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl~
    ## $ game_description         <chr> "About This Game Developed by id software, th~
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope~
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio~
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve~
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, ~
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N~

``` r
tibble::view(steam_games)
class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
head(steam_games)
```

    ## # A tibble: 6 x 21
    ##      id url    types  name  desc_snippet recent_reviews all_reviews release_date
    ##   <dbl> <chr>  <chr>  <chr> <chr>        <chr>          <chr>       <chr>       
    ## 1     1 https~ app    DOOM  Now include~ Very Positive~ Very Posit~ May 12, 2016
    ## 2     2 https~ app    PLAY~ PLAYERUNKNO~ Mixed,(6,214)~ Mixed,(836~ Dec 21, 2017
    ## 3     3 https~ app    BATT~ Take comman~ Mixed,(166),-~ Mostly Pos~ Apr 24, 2018
    ## 4     4 https~ app    DayZ  The post-so~ Mixed,(932),-~ Mixed,(167~ Dec 13, 2018
    ## 5     5 https~ app    EVE ~ EVE Online ~ Mixed,(287),-~ Mostly Pos~ May 6, 2003 
    ## 6     6 https~ bundle Gran~ Grand Theft~ NaN            NaN         NaN         
    ## # ... with 13 more variables: developer <chr>, publisher <chr>,
    ## #   popular_tags <chr>, game_details <chr>, languages <chr>,
    ## #   achievements <dbl>, genre <chr>, game_description <chr>,
    ## #   mature_content <chr>, minimum_requirements <chr>,
    ## #   recommended_requirements <chr>, original_price <dbl>, discount_price <dbl>

## 1.3

By analyzing the content of the tibbles I choose the following data sets
*1. Flow sample* *2. Cancer sample*

**Flow\_sample** seems a very simple data set, however it has both
quantitative and qualitative variables that can be used to group the
information according to the content of the rows. Also a lot of
information can be obtained from it, for example knowing in which month
more flow is produced.

**Cancer\_sample** I liked this data set because I am pretty
familiarized with it, since my research is related to bladder cancer
patients. Moreover, I have more experience working with quantitative
data, because exact conclusions can be obtained from it. I would like to
know if there is some relationship between the characteristic of the
nucleus from the breast biopsy and the diagnosis.

## 1.4

Research questions related to each data set **Flow sample** *Is there a
relationship with the flow and the month of the year?*

**Cancer\_sample** *Is there a relationship between the diagnosis and
the area of the nucleus in the biopsy?*

**Final choice: Cancer\_sample**

# Task 2: Exploring your dataset

Exploration of the data set using dplyr and ggplot to get to know more
the variables in the tibble *Cancer\_samples*

First of all, a brief introduction of the data set. *Cancer\_samples*
was obtained from the UCI Machine Learning Repository and it contains
information about the cell nuclei in the biopsy of a breast cancer mass
obtained with fine needle aspirate (FNA) and analysed trough machine
learning using digitized imaging. It contains the ID of the patient and
the diagnosis B: benign tumor and M= malign tumor.

It has the mean, standard deviation (se), and worst (max) values of each
variable:

-   radius (mean of distances from center to points on the perimeter)in
    um
-   texture (standard deviation of gray-scale values)
-   perimeter in um
-   area in um^2
-   smoothness (local variation in radius lengths)
-   compactness (perimeter^2 / area - 1.0)
-   concavity (severity of concave portions of the contour)
-   concave points (number of concave portions of the contour)
-   symmetry
-   fractal dimension (“coastline approximation” - 1)

Moreover, a brief explanation of ggplot. It is a package that can be
loaded in R studio used to generate different type of graphs. The first
argument is always the tibble where your data set is store, then you
will set the aesthetic mapping (with aes()), the first two variables are
the x and the y axis, then you can add parameters like color and fill
that are related to your variables. You then add on layers named geoms
(like geom\_point() or geom\_histogram()), inside this layers you can
also specify constant parameteres such as width, color and fill.

Another package I was using is called dplyr, is for data manipulation,
allowing you to add new variables (mutate), select a set of columns by
their names (select), filter some rows (filter), reduce multiple
variables into a summary (summaries) etc..

“%in%” Is used instead of “==” " %&gt;% " Is for pipping and is used to
nest functions “&lt;-” is used to sign a function to a variable “print”
is used to print the variable in the r console

### First excercise

To get to know better the data set I will make a bar graph that counts
the amount of patients diagnose with a benign and malign tumor.
Furthermore, I will analyze the distribution of the perimeter (um) of
the nucleolus in the different biopsies, to see how much variability the
data set has and if is worth comparing it with other variables

``` r
# A bar chart was used to count the number of patients with malign and benign tumors, this function only need the x value, since it adds bars whose height is proportional to the number of rows. 
#To add the number of patients in the graph geom_text was used. By setting vjust (the vertical justification), it is possible to move the text above or below the tops of the bars, 1.5 to put it above the bars.

Ex1.2 <- ggplot(cancer_sample,aes(diagnosis)) +
  geom_bar(fill = "orange", alpha = 0.6) +
  geom_text(aes(label = ..count..), stat = "count", vjust = 1.5)
print(Ex1.2)
```

![](Milestone-1-Luque_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
## To know the distribution of the perimeter for both benign and malign tumor geom_jitter was used,that shows in what ranges the values are located and if there is any difference between the perimeter of benign tumors and malign tumors. Since one of the main factors to detect a malign tumor during pathology analysis is to look for large nucleus. The color, transparency (alpha) and width are constant, that is why it goes directly in the geom layer outside the aes
Ex1.1<- ggplot(cancer_sample, aes(diagnosis, perimeter_mean)) + 
    geom_jitter(color= "red", alpha = 0.4, width = 0.25)
print(Ex1.1)
```

![](Milestone-1-Luque_files/figure-gfm/unnamed-chunk-3-2.png)<!-- -->

### Second exercise

Explore the relationship between 2 variables in a plot.I wanted to know
if there is a relationship between the perimeter of the nuclei and the
concavity.Since larger cells (with bigger perimeter) tend to have more
concave portions of the contour. I group the plot by diagnosis to see
the variability within each group or if it has come distinguish
characteristics.

``` r
#To do a scatter plot I used geom_point with the perimeter in the x axis and the concavity in the y axis. Using the shape outside aes sinceis a constant value 
Ex2<- ggplot(cancer_sample, aes(perimeter_mean, concavity_mean)) +
       geom_point(mapping = aes( fill = diagnosis), shape = 21)
print(Ex2)
```

![](Milestone-1-Luque_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

### Third exercise

I will analyze the density of a the area (um^2) of the nucleolus in the
different biopsies, to see how much variability the data set has and if
is worth comparing it with other variables

``` r
# To know the density of a single variable (the area) in both benign and malign tumors I used geom_distribution, I used ..density..  to create the histogram with a density scale. Fill was used to color the inside of the histogram
Ex3.1 <- ggplot(cancer_sample, aes(area_mean)) +
   geom_histogram(fill = "green", alpha = 0.7)
print(Ex3.1)
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](Milestone-1-Luque_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
# I wanted to know the density of the area by diagnosis, to see if the area is different for malign and benign tumors and if there is a relationship, also to see in which the is more heterogeneity. Malign tumors tend to have bigger nucleus 
#Using geom_density you don't have to specify ..density.. it does it automatically.
#Putting fill inside of the aes in the geom_density layer is used to put in a different color the distribution of the two diagnosis.
#Alpha is used for transparency of the color (when the graphs are overlapping)
Ex3.2 <- ggplot(cancer_sample, aes(area_mean)) + 
    geom_density(aes(fill = diagnosis), alpha=0.8)
print(Ex3.2)
```

![](Milestone-1-Luque_files/figure-gfm/unnamed-chunk-5-2.png)<!-- -->
\#\#\# Forth excercise I want to know the mean values for the two
diagnostic groups, to analyze which variables are clues in detecting
malign and benign tumors or if there is any difference between the two
groups. Moreover, the standard deviation can be used to know the
variation.

``` r
# First I grouped the data set by diagnosis to have a group with all the data regarding malign tumors and data regarding benign tumors.
# The summarize function collapses the information from all the rows from each group in one 
# Mean is used to obtain the mean within the values in the group and sd is used for standard deviation
# Digits is used to set the amount of digits shown in the table 
# Pivot_longer and pivot_wider are used to transpose the data to have a better and understandable table
Ex4 <- cancer_sample %>%
  group_by(diagnosis) %>%
  summarise(Mean_area = mean(area_mean),
            Sd_area = sd(area_mean),
            Mean_perimeter = mean(perimeter_mean),
            SD_perimeter = sd(perimeter_mean),
            Mean_texture = mean(texture_mean),
            SD_texture = sd(texture_mean),
            Mean_smoothness = mean(smoothness_mean),
            SD_smoothness = sd(smoothness_mean), digits = 2)%>%
               pivot_longer(cols = -diagnosis, names_to = 'Diagnosis') %>% 
               pivot_wider(names_from = diagnosis, values_from = value)
head(Ex4)
```

    ## # A tibble: 6 x 3
    ##   Diagnosis           B      M
    ##   <chr>           <dbl>  <dbl>
    ## 1 Mean_area      463.   978.  
    ## 2 Sd_area        134.   368.  
    ## 3 Mean_perimeter  78.1  115.  
    ## 4 SD_perimeter    11.8   21.9 
    ## 5 Mean_texture    17.9   21.6 
    ## 6 SD_texture       4.00   3.78

# Task 3: Research questions

The main objective of analyzing this data set is to determine which
variables can be used to diagnose tumors by imaging abalyzis of nucleous
from biopsis.

1.  Is there a difference within the area of the nucleus of benign
    tumors and malign tumors?
2.  Does malign tumors have more variability in smoothness in their
    nucleus than benign tumors?
3.  Could it be possible to diagnose the tumor of a patience just by
    looking at the concavity of the nucleolus?
4.  Is there a relationship between the symmetry of the nucleolus and
    the compactness in malign tumors?
