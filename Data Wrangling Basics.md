## Data Wrangling

| **Package** | **Functions** |
|-------------|---------------|
| Tidyverse   | Data manipulation, visualization, and data cleaning |
| dplyr       | Data manipulation |
| tidyr       | Data reshaping |
| data.table  | Fast and memory-efficient data manipulation |
| plyr        | Data manipulation |
| janitor     | Data cleaning |
| stringr     | String manipulation |
| lubridate   | Date and time manipulation |

> Note: If you are working with tabular data and need to manipulate it, dplyr is the way to go. On the other hand, if you need to reshape your data, tidyr is the package you should use.

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

