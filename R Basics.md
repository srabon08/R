## Getting Started

### Load Package and Dataset

| **Command** | **Functions** |
| --- | --- |
| ``insatll.packages ("dplyr")`| Download and install **dplyr** package from CRAN | 
| `library(dplyr)` | Load the **dplyr** package into the session, making all its functions available to use |
|  ``dplyr::select`  | Use a particular function from a package (i.e. **select** function for **dplyr** package |
|  `data(dataset name)` | Load a built-in dataset into the environment| `data(iris)`|

---

### Set Working Directory (where inputs are found and outputs are sent)

| **Command** | **Functions** |
| --- | --- |
| getwd()`| Find the current working directory |
| `setwd("C:/Users/Documents/R")`| Change the current directory to C:/Users/Documents/R|` |
| `set("..")`| Move one directory up |
| `dir.create("C:/Users/Documents/R/New_Project")` | To create new folder "New_Project" to store project data |
| `file.exists("C:/Users/Documents/R/Project_Name")` | To make sure if the folder exists |

```js
getwd() #get the location of the current WD
dir.create("C:/Users/Documents/R") #create new WD
  setwd("C:/Users/Documents/R") #set the location of WD
```

Note: Use the `if (codition){do something} else{do soemthing different}` function to create and set WD to save time

``` js
if(file.exists("C:/Users/Documents/R")){
  setwd("C:/Users/Documents/R")
}else{
dir.create("C:/Users/Documents/R")
  setwd("C:/Users/Documents/R")
}
```
---

### Read data

#### Excel: Use any of the following depending on file type

> Note: Always assign a name to the dataframe [i.e. df <- read.csv(file.csv)]

``` js
df <- read.csv(“type_filename_here”) # Importing csv file`
```
OR
``` js
df <- read.csv(“type_filename_here.csv”) # Importing csv file 
```
OR
``` js
df <- read_excel(“type_filename_here.xls”) # To import xls files 
```
OR
``` js
df <- read_excel(“type_filename_here.xlsx”) # To import xlsx files 
```
OR
``` js
df <- read_excel(“type_filename_here”, sheet = 2) # To import an xls file stored in a particular sheet number (for example, sheet number 2)
```
OR
``` js
df <- read_excel(“type_filename_here”, sheet = students) # To import an xlsx file stored in a particular sheet name (for example, sheet named students)
```

#

#### Load data from R data file

```js
load(“type_filename_here.RData”) # read R data files` 
```
#### Load data from R packages

```js
load(file
```js
library(ggplot2) #load ggplot2 library
ls(package:ggplot2) #list all packages under ggplot2
mpg #load mpg dataset from ggplot2 package/make sure library is loaded
view(mpg) # To open the dataset/Table in a separate page in tabular format
```
OR 
```js
data() # opens a tab/window listing all the built-in datasets
data(package= "ggplot2") # opens a tab/window listing all avaialable datasets in ggplot2 package
data("mtcars") # load specific dataset i.e. mtcars dataset
```
OR

```js
load ("data_name.RData") #importing R data files. Prior to loading, clear all objects currently within the workspace to avoid overwrite.
```

#### Load data from Text file

```js
df <- read_table (“type_filename_here.txt”) # To import table ffrom text files
```
---

### Convert Datafram  to Tibble:;

```js
as_tibble(iris)  #conver iris dataset into a Tibble
```
### Convert tibble to datafram

```js
as.data.frame(table1)
```
Note: Be careful to use as.data.frame() and not as_data_frame(), which is an alias for as_tibble().




### Save Data




