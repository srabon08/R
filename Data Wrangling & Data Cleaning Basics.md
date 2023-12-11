## Data Wrangling

The main difference between data wrangling and data cleaning is that data wrangling is the process of converting and mapping data from one format to another format to use that data to perform analyzing, but data cleaning is the process of eliminating the incorrect data or to modify them.

| **Package** | **Functions** |
|-------------|---------------|
| Tidyverse   | Data manipulation, visualization, and data cleaning |
| data.table  | Fast and memory-efficient data manipulation |
| janitor     | Data cleaning and formatting |
| readxl      | Excel file import | 


> Note: 

* The following packages are part of the core tidyverse:
  
| **Package** | **Functions** |
|-------------|---------------|
| dplyr       | Data manipulation |
| tidyr       | Data reshaping |
| stringr     | String manipulation |
| lubridate   | Date and time manipulation |
| purr     | Functional programming |
| forcats   | Factor manipulation |
| readr    | Data import |
| tibble   | Data frame creation |

* If you are working with tabular data and need to manipulate it, dplyr is the way to go. On the other hand, if you need to reshape your data, tidyr is the package you should use. If you are using Tidyverse, no need to load dplyr or tidyr separately.
   
---

### Grammer of data wrangling: 

Hadley Wickham, one of the authors of **dplyr**, has identified **five verbs** for working with data in a data frame

| Function | Description |
| --- | --- |
| `select()` | Take a subset of the columns (i.e., features, variables) |
| `filter()` | Take a subset of the rows (i.e., observations) |
| `mutate()` | Add or modify existing columns |
| `arrange()` | Sort the rows |
| `summarize()` | Aggregate the data across rows (e.g., group it according to some criteria) |

> Note: The function `sort()` will sort a vector, but not a data frame. The function that will sort a data frame is called `arrange()`




