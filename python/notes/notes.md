# Python
## Code
### Converting/encoding for csv
```python
import pandas as pd
def convert(path_in, path_out):
    data = pd.read_csv(path_in, delimiter=',', encoding='windows-1251')
    data.to_csv(path_out, sep=';', encoding='utf-8', index=False)
```
