[How to make a great R reproducible example](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example)
# R Tips

### Load RData
```
load("df")
```
### Get a list of datasets in a particular package
[Source](https://stackoverflow.com/questions/27709936/get-a-list-of-the-data-sets-in-a-particular-package)
```
data(package = "package_name")
```
### Print version information about R, the OS and attached or loaded packages.
```
print(sessionInfo())
```
### Specify width and height of plot
```
options(repr.plot.width=6, repr.plot.height=4)
```
### Check if the package is installed

```
if(!require("tidyverse")){
  # If the package is not in the system then it will be installed
  install.packages("tidyverse", dependencies = TRUE)
  # Load the package
  library("tidyverse")
}
```
