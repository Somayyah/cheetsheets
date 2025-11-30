
# Panda library functions

## Reading files

```
import panda as pd

df = pd.read_csv(<PATH>[, <sheet name>])
```

replace csv with other formats if needed, for example:

```
df = pd.read_excel()
```

## Lookup

```
DataFrame.loc[row_labels, column_labels]
DataFrame.loci[row_labels, column_labels]
```


