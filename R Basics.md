## Getting Started

### Load Package and Dataset

| **Command** | **Functions** |
| --- | --- |
| ``insatll.packages ("dplyr")`| Download and install **dplyr** package from CRAN | 
| `library(dplyr)` | Load the **dplyr** package into the session, making all its functions available to use |
|  ``dplyr::select`  | Use a particular function from a package (i.e. **select** function for **dplyr** package |
|  `data(dataset name)` | Load a built-in dataset into the environment| `data(iris)`|


### Set Working Directory (where inputs are found and outputs are sent)

| **Command** | **Functions** |
| --- | --- |
| `getwd()`| Find the current working directory|
| `setwd("C:/Users/Documents/R")`| Change the current directory to C:/Users/Documents/R|`|
|`set("..")`| Move one directory up|
|`dir.create("C:/Users/Documents/R/New_Project")`| To create new folder "New_Project" to store project data |
|`file.exists("C:/Users/Documents/R/Project_Name")`| To make sure if the folder exists|

Note: Use the `if (codition){do something} else{do soemthing different}` function to create and set WD to save time

``` js
if(file.exists("C:/Users/Documents/R")){
  setwd("C:/Users/Documents/R")
}else{
dir.create("C:/Users/Documents/R")
  setwd("C:/Users/Documents/R")
}
```

