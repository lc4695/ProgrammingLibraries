# Python & R issues in Google Colab
- [Python](#python)
  * [Mount Google Drive](#mount-google-drive)
  * [Data Table Display](#data-table-display)
- [R](#r)
  * [Mount single file](#mount-single-file)
  * [Non-zero exit Status warning](#non-zero-exit-status-warning)
  * [ggmap installation](#ggmap-installation)
  * [sf installation](#sf-installation)
  * [raster installation](#raster-installation)
  * [skimr installation](#skimr-installation) 
---


## Python

### Mount Google Drive
[Source](https://colab.research.google.com/notebooks/io.ipynb#scrollTo=RWSJpsyKqHjH)
```
from google.colab import drive
drive.mount('/content/drive')
```

### Data Table Display
[Source](https://colab.research.google.com/notebooks/data_table.ipynb#scrollTo=JgBtx0xFFv_i)
```
from google.colab import data_table
data_table.enable_dataframe_formatter()
data_table.DataTable(df, include_index=False, num_rows_per_page=10)
```
## R

### Mount Google Drive
[Source](https://stackoverflow.com/questions/56679549/how-to-mount-google-drive-to-r-notebook-in-colab)
```
install.packages("googledrive")
library("googledrive")

if (file.exists("/usr/local/lib/python3.6/dist-packages/google/colab_ipython.py")){
  install.packages("R.utils")
  library("R.utils")
  library("httr")
  my_check <- function() {return(TRUE)}
  reassignInPackage("is_interactive", pkgName = "httr", my_check)
  options(rlang_interactive=TRUE)
}           
```

### Mount single file
[Soruce](https://stackoverflow.com/questions/59746036/how-to-read-data-from-google-drive-using-r-in-colab)
```
system("ls", TRUE)
1. system("ls", TRUE) # optional
---
### Find the file in google drive and copy the share link
# Link: https://drive.google.com/open?id=12uRyLU-aAdInBtkVubhI4l3PmbYIo5aE
### Change id
2. system("gdown --id 12uRyLU-aAdInBtkVubhI4l3PmbYIo5aE")
```
### Non-zero exit Status warning
```
system('sudo apt-get install r-cran-library_name', intern=TRUE)
```
### ggmap installation
```
system('sudo apt-get install r-cran-rcpp', intern=TRUE)
install.packages("Rcpp")
install.packages("plyr")
install.packages("ggmap", dependencies = TRUE)

library(ggmap)
# API key: 
register_google(key="")
```

### sf installation
```
remotes::install_github("r-quantities/units")
install.packages("sf", dependencies = F)
library(sf)
```
### raster installation
```
install.packages('raster', repos='https://rspatial.r-universe.dev')
```

### skimr installation
```
devtools::install_github("ropensci/skimr", force = TRUE)
```

