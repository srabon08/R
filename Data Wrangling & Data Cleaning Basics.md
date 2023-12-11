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

Read [Data wrangling](http://mdsr-book.github.io/excerpts/mdsr-dataI.pdf) for more information: 

| Function | Description |
| --- | --- |
| `select()` | Take a subset of the columns (i.e., features, variables) |
| `filter()` | Take a subset of the rows (i.e., observations) |
| `mutate()` | Add or modify existing columns |
| `arrange()` | Sort the rows |
| `summarize()` | Aggregate the data across rows (e.g., group it according to some criteria) |

> Note: The function `sort()` will sort a vector, but not a data frame. The function that will sort a data frame is called `arrange()`


#### Examples: 

Let's use the **mtcars** dataset from the tidyverse package

```js
load(tidyverse) #load tidyverse package
data("mtcars") # load mtcars dataset from the tidyverse package
```

 > `select()`

The first argument to the `select()` function is the `data frame`, followed by an arbitrarily long list of `column names`, separated by commas. 
Note: It is not necessary to wrap the column names in quotation marks.

OR

dataframe %>% select(condition)

```js
select(mtcars, mpg, cyl, hp)
```

OR 

```js
mtcars %>%
select(mpg, cyl, hp)
```
#

 > `filter()`

the first argument to filter() is a `data frame`, and subsequent arguments are `logical conditions` that are evaluated on any **involved columns**. 
Note that the == is a test for equality. 

```js
filter (mtcars, mpg > 19 & cyl == "6")
```

OR

```js
mtcars %>%
filter(mpg > 19 & cyl == "6")
```

#
> Combine use of `selct() & filter ()`

```js
select(filter(mtcars, mpg > 19 & cyl == "6"), hp)
```

OR

```js
mtcars %>% 
filter(mpg>19 & cyl == "6") %>%
select(hp)
```
