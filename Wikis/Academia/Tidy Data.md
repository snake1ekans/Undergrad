A paradigm for data processing and filtering created by Hadley Wickham (original paper found [[Tidy Data paper.pdf|here]]). The long and short of it is 3 main principles that allow data to be universally processed, despite messiness in individual values and data points. This is especially important when interacting with [[R Programming (fix format)|R]] and the [[Tidyverse (R package)|tidyverse]]. In the tidyverse, the most useful packages for tidying are [[Tidyverse (R package)#Tidyr|Tidyr]] and [[Tidyverse (R package)#Dplyr|Dplyr]].

---
# 3 Axioms
## Each variable is a column; each column is a variable
Essentially what it says on the tin. Each variable should have its own column and each column should only contain one variable. For example, if time and date are independently important, then each should have their own column. If height and weight are independently important, they should have their own columns.
## Each observation is a row; each row is an observation
Simple as. Each observation performed in a test should be its own row, and each row should be one observation. That means that you should avoid duplicate rows with mostly the same data, and avoid doubling up observations on a row
## Each value is a cell; each cell is a value
Each cell should contain only 1 data value, and each data value should be entirely and exclusively contained in 1 cell. This means that data is easy to process and no manipulations need to be done to cells to process and filter data

---
# Examples
## Untidy 
# A tibble: 3 × 6  
GNLCCCODE CT_0BRK CT_25BRK CT_50BRK CT_75BRK CT_100BRK  
\<chr>       \<dbl>    \<dbl>    \<dbl>    \<dbl>     \<dbl>  
1 CW_101      0.715    0.678    0.638    0.596     0.553  
2 CW_102      0.598    0.598    0.598    0.598     0.598  
3 CW_103      0.332    0.332    0.332    0.332     0.332

## Tidy
# A tibble: 15 × 3  
GNLCCCODE Brook_Percentage Probability  
\<chr>     \<chr>                  \<dbl>  
1 CW_101    CT_0BRK                0.715  
2 CW_101    CT_25BRK               0.678  
3 CW_101    CT_50BRK               0.638  
4 CW_101    CT_75BRK               0.596  
5 CW_101    CT_100BRK              0.553  
6 CW_102    CT_0BRK                0.598  
7 CW_102    CT_25BRK               0.598  
8 CW_102    CT_50BRK               0.598  
9 CW_102    CT_75BRK               0.598  
10 CW_102    CT_100BRK              0.598  
11 CW_103    CT_0BRK                0.332  
12 CW_103    CT_25BRK               0.332  
13 CW_103    CT_50BRK               0.332  
14 CW_103    CT_75BRK               0.332  
15 CW_103    CT_100BRK              0.332


#statistics #biology #bioinformatics #software 