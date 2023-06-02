# Python & R issues in Google Colab
- [Python](#python)
  * [Mount Google Drive](#mount-google-drive)
  * [Data Table Display](#data-table-display)
  * [Run SQL Query](#run-sql-query)
- [R](#r)
  * [Access Google Drive](#access-google-drive)
  * [Mount single file](#mount-single-file)
  * [Non-zero exit Status warning](#non-zero-exit-status-warning)
  * [Zip a folder](#zip-a-folder)
  * [Create a new folder](#create-a-new-folder)
  * [Library Installation](#library-installation)
    + [ggmap installation](#ggmap-installation)
    + [sf installation](#sf-installation)
    + [raster installation](#raster-installation)
    + [skimr installation](#skimr-installation)
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
### Run SQL Query
```
from google.colab import drive
drive.mount('/content/drive')

import pandas as pd
import sqlite3

df = pd.read_csv('file_path')

conn = sqlite3.connect('database.db')

df.to_sql('df', conn, if_exists='replace')

query = '''
SELECT * FROM df;
'''
df_df = pd.read_sql_query(query, conn)
print(df_df.head())
```

## R

### Access Google Drive
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

drive_auth(use_oob = TRUE, cache = TRUE)
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
### Zip a folder
```
system("zip -r /content.zip  /content", TRUE)
```

### Create a new folder
[Source](http://rfunction.com/archives/2432)
```
dir.create(path) 

list.files(path) # see all the files in the folder
```
### Library Installation

#### ggmap installation
```
system('sudo apt-get install r-cran-rcpp', intern=TRUE)
install.packages("Rcpp")
install.packages("plyr")
install.packages("ggmap", dependencies = TRUE)

library(ggmap)
# API key: 
register_google(key="")
```

#### sf installation
```
remotes::install_github("r-quantities/units")
install.packages("sf", dependencies = F)
library(sf)
```
#### raster installation
```
install.packages('raster', repos='https://rspatial.r-universe.dev')
```

#### skimr installation
```
devtools::install_github("ropensci/skimr", force = TRUE)
```

