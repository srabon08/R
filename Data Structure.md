## Data Structure

Dataframe and tibbles are building blocks for analysis in R. 

### Dataframe

A dataframe is a table of columns, like spreadsheets or SQL tables. Each column is a variable and each row is an observation. Dataframes help summarize and format data.

#### Uselful Practices: 

* Name columns according to variables.
* Ensure equal length of columns, even with missing data.
  
#

### Tibble

A tibble is a simplified dataframe in the tidyverse. It makes data manipulation easier.

#### Pros and Cons compared to dataframes:

* Pros: No data type changes, no variable name changes, no row names, won't overload console (automatically set to pull up the first 10 rows and as many column fits in the screen), easy printing
* Cons: Less flexible than data frames, some differences in syntax and behavior

---

### Tidy data 

Read [Tidy Data](https://vita.had.co.nz/papers/tidy-data.pdf) by Hadley Wickham

