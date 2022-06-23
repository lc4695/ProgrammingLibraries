# Python & R issues in Google Colab

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
### Mount single file
```
system("ls", TRUE)
1. system("ls", TRUE)
---
# Find the file in google drive and copy the share link
# Link: https://drive.google.com/open?id=12uRyLU-aAdInBtkVubhI4l3PmbYIo5aE
# Change id
2. system("gdown --id 12uRyLU-aAdInBtkVubhI4l3PmbYIo5aE")
```
### "Non-zero exit Status" warning
```
system('sudo apt-get install r-cran-library_name', intern=TRUE)
```
### `ggmap` installation
```
system('sudo apt-get install r-cran-rcpp', intern=TRUE)
install.packages("Rcpp")
install.packages("plyr")
install.packages("ggmap", dependencies = TRUE)

library(ggmap)
# API key: 
register_google(key="")
```
### Load RData
```
load("df")
```
### Get a list of datasets in a particular package
[Source](https://stackoverflow.com/questions/27709936/get-a-list-of-the-data-sets-in-a-particular-package)
```
data(package = "package_name")
```
