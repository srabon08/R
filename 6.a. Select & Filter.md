Note: 
* df= dataframe
* n= new
* sm= small

---


### Select
#
Syntax of select():

```js
df_n <- select (df, variables_to_select)
```
OR 

```js
df_n <- df %>%
select(variables_to_select)
```
# 

> Select specific column(s)

```js
library(tidyverse)
data(mtcars)
mtcars_n <- mtcars %>%
select (mpg, cyl, hp)
head (mtcars_n)
```

> Select all but specific column(s)

 ```js
library(tidyverse)
data(mtcars)
mtcars_n <- mtcars %>%
select(-mpg, -cyl, -hp)
```

> # Select columns by list of index or position
df %>% select(c(2,3))

df2 <- df[,-2:-4]

Select columns by index range
df %>% select(2:3)


Select columns except name & gender
df %>% select(-c('name','gender'))



Select columns between name and state
df %>% select('name':'state')


Select columns starts with a string
df %>% select(starts_with('gen'))


Select columns that ends with a string
df %>% select(ends_with('e'))


Select columns that contains
df %>% select(contains('a'))


Select all numeric columns
df %>% select_if(is.numeric)




