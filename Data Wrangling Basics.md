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
| purr        | Functional programming |
| forcats     | Factor manipulation |
| readr       | Data import |
| tibble      | Data frame creation |

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
Note: It is not necessary to wrap the column names in quotation marks. However, try using pipe-forwarding nesting to make it more readable. 

OR

dataframe %>% select(condition)

```js
select(mtcars, mpg, cyl, hp)
```

OR 
select speficic column(s)

```js
mtcars %>%
select(mpg, cyl, hp)
```
# 
 select all but specific columns

 ```js
mtcars %>%
select(-mpg, -cyl, -hp)
```

#

 > `filter()`

the first argument to filter() is a `data frame`, and subsequent arguments are `logical conditions` that are evaluated on any **involved columns**. 
Note: == is a test for equality. However, try using pipe-forwarding nesting to make it more readable. 

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
---

> `mutate()`

`mutate()` creates new columns that are functions of existing variables. 

The first argument to mutate() is a `data frame`, and subsequent arguments are `logical conditions` that are evaluated on any **involved columns**. 
However, try using pipe-forwarding nesting to make it more readable. 

Note: 
* It can modify (if the name is the same as an existing column) and delete columns (by setting their value to NULL). So, in order to keep both column make sure to give the new column a unique name. This can be helpful to modify existing column.

* To preserve the existing dataframe, save the result of `mutate()` as a new object. 

```js
mtcars_new <- mutate(mtcars, kpl = mpg *0.425) #mpg to km/L
```

OR

```js
mtcars_new <- mtcars %>% 
mutate(kpl = mpg *0.425) #mpg to km/L
```
#
multiple criteria

```js
mtcars_new <- mtcars %>% 
mutate(kpl = mpg *0.425, kw= hp *1.341) #mpg to km/L and HP to KW
```
#

use ifelse case#1

* Here, a new column called **engine** will be added to the mtcars data frame, with the value “small” if the cyl is 4, “medium” if the cyl is 6, and “large” otherwise.

```js
mtcars_new <- mtcars %>% 
mutate(engine = ifelse(cyl == 4, "small", ifelse(cyl == 6, "medium", "large")))
```

# 

use ifelse case#2

Here, a new column called **engine_N** will be added to the mtcars_new data frame, with the value “medium” if the cyl is 4-6, otherwise it will remain same as the engine column. 

```js
mtcars_new <- mtcars_new %>% 
  mutate(engine_N = ifelse((cyl %in% c(4,6)), "medium", engine))
```
#

use case_when

```js
mtcars_new <- mtcars %>%
  mutate(performance = case_when(
    hp > 200 & wt < 3 ~ "high",
    hp >= 100 & hp <= 200 & wt >= 3 & wt <= 4 ~ "medium",
    TRUE ~ "low"
  ))
```

---

> `rename()`

```js
mtcars_new <- mtcars %>%
rename( new_mpg= mpg)
```
---

> `arrange()`

The fucntion `sort()` will sort vector, but no a data frame. The function that will sort a data frame is called `arrange()`


Ascending

```js
mtcars_new <- mtcars %>%
arrange( gear)
```
#
Descending

```js
mtcars_new <- mtcars %>%
arrange( desc (gear))
```
OR
```js
mtcars_new <- mtcars %>%
arrange(-gear))
```
#
Combination

```js
mtcars_new <- mtcars %>%
  arrange(desc(gear), cyl, carb)
```
---

> `summarize()` with `group_by()
