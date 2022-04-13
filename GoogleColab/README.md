### Data Table Display
[Source](https://colab.research.google.com/notebooks/data_table.ipynb#scrollTo=JgBtx0xFFv_i)
```
from google.colab import data_table
data_table.enable_dataframe_formatter()
data_table.DataTable(df, include_index=False, num_rows_per_page=10)
```

### Mount Google Drive
[Source](https://colab.research.google.com/notebooks/io.ipynb#scrollTo=RWSJpsyKqHjH)
```
from google.colab import drive
drive.mount('/content/drive')
```
